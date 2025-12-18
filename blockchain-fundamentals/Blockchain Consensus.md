## What is the Consensus Problem?

In a blockchain, thousands of computers (nodes) run independently with **no central authority.**
The big challenge is: **how do all of them agree on the same truth?**

Consensus is the process that helps all nodes:

- Agree on transaction history

- Maintain one shared, verified record

- Trust the system without trusting each other

## Why Consensus Is Needed (Simple Example)

If everyone sees the same transaction at the same time, agreement is easy.
But when participants are spread across the world, messages can be delayed or missed.

Consensus mechanisms exist to solve this coordination problem and keep one correct version of history.

## Three Core Problems Consensus Must Solve
### 1. Sybil Attacks (Sybil Resistance)

A Sybil attack happens when one person creates many fake identities (nodes) to gain control.

In blockchains, nodes act like voters

Fake nodes could approve fraud or censor transactions

Similar to stuffing a ballot box with fake voters

Solution: Make participation expensive, so fake identities are useless.
