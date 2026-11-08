# FUEL: a live hook on this stack

FUEL is a buy-and-burn hook built by Mintvelocity's founder. It ran on the original platform's mainnet deployment - the same stack Mintvelocity is forked from - and its fee routing was verified on-chain during its first launch on October 19, 2026.

## The rules

From its public listing, verbatim:

> Takes nothing from trades. When the coin's price is 3% or more under FUEL's mark, the pot buys and burns the coin with 1/240 of what it holds, up to 4 times that on a 12% drop, at most once per 5 minutes.

Fee routing: 0% hook fee on trades. The creator fee splits 50% to the pot, 25% to the launcher, 25% to the builder.

## Verified on-chain

During the first launch the hook took 0% of trades, the 2% creator fee added up exactly (0.31 SOL over 24 trades) and split across pot, launcher and builder.

Listing counters as of November 7, 2026:

- Collected: 0.1543 SOL
- To the builder: 0.0154 SOL
- Bought and burned: 0 SOL

No dip buy has fired yet. The rule triggers only when price trades 3% or more under its tracked mark, and the first launch's pool went quiet before that happened. We state that plainly because the mechanic should be judged on what it has done, not on what it is designed to do.

## Check it yourself

Builder wallet, public on the listing:

AxoN4hpQJWKFkSimhqnA7dUsqf5VGojA5RhhZTiP4KFm

Viewable on Solscan: https://solscan.io/account/AxoN4hpQJWKFkSimhqnA7dUsqf5VGojA5RhhZTiP4KFm

Note: the original platform's site went offline after its November 4, 2026 shutdown. The programs and the on-chain record remain on Solana mainnet.
