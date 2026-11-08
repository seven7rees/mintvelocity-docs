# What is Mintvelocity

Hooks that answer, not only approve: Uniswap v4's hook idea, on Solana, at the token level.

## Why a new standard

Token-2022 made transfer hooks safe by making them powerless: over a transfer, a hook can only let it stand or make it fail. A Mintvelocity hook keeps the safety rule (never the user's signature) and answers instead; the token program or the DEX applies the answer.

Venues treat Token-2022 hooks as a risk. Meteora's DBC revokes a token's hook when it graduates, and DAMM v2 accepts a hook mint only once its hook is revoked. Orca lists hook mints case by case, and its criteria forbid hooks that charge fees or move tokens. Raydium's CPMM and CLMM refuse hook mints unless an admin registers them.

Mintvelocity is built the other way: the token standard, the DEX and the launchpad are designed around hooks, so hook coins are first-class citizens.

## What a hook does

- **Runs:** token hooks on transfers, mints and burns; pool hooks on pool creation, liquidity and every swap.
- **Sees:** the whole operation. A pool hook sees the trade: direction, amounts in and out, reserves, both tokens, the trader and who receives.
- **Answers:** up to three cuts from the amount, each to an account it names. A pool hook can also burn part of a swap and set its LP fee.
- **Keeps:** 64 bytes of state per holder, inside the holding. No extra account per holder.
- **Bounds:** never the user's signature, never more than the amount moved. The token program or the DEX checks every answer before applying it.

## The stack

Three layers, inherited from the forked code:

- **Token standard:** mints, holdings, hooks with return deltas
- **DEX:** constant-product pools with v4-style hooks, virtual reserves
- **Launchpad:** launches, a fee schedule and launch rules as hooks, graduation

A bridge moves SPL, Token-2022 and SOL in and out of the standard, one for one. (Native SOL launches, which remove the bridge step, are a planned rebuild. See the roadmap.)

## The original deployment, verifiable on-chain

The stack ran on Solana mainnet under Bordrless from October 7, 2026 until the shutdown. These are Bordrless's program addresses; Mintvelocity will deploy the same code under its own keys at launch.

| Program | Address | Role |
| --- | --- | --- |
| Token standard | 2XoEWp8cF3kRXg74eVwPAyTFhVCAztn3V88komxAvr22 | Mints, holdings, hooks with return deltas |
| DEX | GyzKSnnEu2uN5bBRecE4XYY2enbfR2D2MtxnbJPGy7hk | Constant-product pools, v4-style hooks |
| Bridge | CtLkuFVitoXHTa86Hfp8KmfSDfqJaMYFWr6EGmQVsKb7 | SPL / Token-2022 / SOL in and out, one for one |
| Launchpad | 1jcBymHxBjniZDhNPy51Vgm5Nz7pLUdxa9UBHc4TavC | Launches, fee schedule and rules, graduation |
| Launch rules kit | 14RJQXPdJfkehit6ezktjd3xujamf8nVSKw2shKamaEH | Holder rewards, max wallet, wallet locks |
| Companion | 6ZUM1gWBH9hBBNoJoaVAGwSftyZ6CUda6vUZTW9MsJuo | A launch's creator as a program |

Mintvelocity's fork is a snapshot of the Apache-2.0 source as of October 8, 2026.
