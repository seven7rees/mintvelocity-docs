# Hooks

A hook is an on-chain program that sets swap fees and routes fee cuts. Anyone can write one.

## Hook and companion: a Pair

A hook can ship with a companion program, deployed together as a Pair. The hook sets fees and routes cuts; the companion acts as the launch's creator, so its fees can buy back, reward holders or vest, with no keeper.

## Launch rules

The launch rules kit is itself a token hook: holder rewards, max wallet, wallet locks. Launchers pick rules at launch; the rules run on-chain from the first trade.

## No in-place upgrades

A hook cannot be upgraded in place. A new version is a new program address, and coins already launched stay on the old one. This is deliberate: the rules a coin launched with cannot be changed under its holders.

## Open by default

On the original platform, every listed hook showed its builder wallet and full source. Mintvelocity keeps that rule.
