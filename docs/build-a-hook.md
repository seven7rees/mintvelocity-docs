# Build a hook

Any developer can write hook logic and earn builder fees when launches use it.

## The path

1. **Start at the hook protocol crate.** It defines the callback args, the return deltas (the hook's answers) and the extra-accounts registry.
2. **Build and test with the TypeScript SDK.** It builds every instruction of the token program, the DEX, the bridge and the launchpad, decodes every account and event, and resolves a hook's accounts. Devnet testing is free.
3. **Submit.** The platform reviews the source and deploys; the builder never holds the deploy key. On the original platform this cost a 0.1 SOL submit fee plus deploy rent of about 1.1 SOL for a single hook or 1.6 SOL for a Pair. Mintvelocity's submit flow and costs will be published before launch.
4. **Earn.** Every launch that picks your hook pays your builder share per trade, on-chain, to your builder wallet.

## Safety bounds

A hook never takes the user's signature and never takes more than the amount moved. The token program or the DEX checks every answer before applying it.
