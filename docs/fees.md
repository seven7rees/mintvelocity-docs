# Fees and earnings

Two levels: protocol fees and hook fees.

## Protocol fees

The stack's shipped defaults, inherited from the forked code. Mintvelocity's final fee schedule is set at launch; the plan is to match these, not undercut them.

- 0.30% LP fee on launch pools
- 25% of rule fees (creator, holder and hook cuts; burns excluded)
- 0.01 SOL per launch
- The first 30 seconds of a launch carry a platform fee decaying from 80%, with optional early lock and max wallet

## Hook fees

Each hook sets its own fees and decides where they go. A launcher's creator fee is set at launch and routed by the hook's rules. Example: the FUEL hook takes 0% on trades and routes the creator fee 50% to its pot, 25% to the launcher, 25% to the builder. See the case study.

## Who earns

- **Token creators:** the creator fee, set at launch, routed per the hook's rules.
- **Hook builders:** the builder share of every launch that uses their hook, paid per trade, on-chain. On the original platform, 31 SOL was paid to 8 builders over 9 days across 30 coins (platform-reported, October 17, 2026).
- **Holders:** whatever a hook routes to them, such as the kit's holder rewards.
