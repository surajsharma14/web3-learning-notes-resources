## What is the Consensus Problem?

In a blockchain thousands of computers (nodes) run independently with **no central authority.**
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
## 1. Sybil Attacks (Sybil Resistance)

A Sybil attack happens when one person creates many fake identities (nodes) to gain control.

- In blockchains, nodes act like voters

- Fake nodes could approve fraud or censor transactions

- Similar to stuffing a ballot box with fake voters

Solution: Make participation expensive, so fake identities are useless.

## Sybil Resistance Mechanisms
**Proof of Work (PoW) — Bitcoin**

- Requires massive computing power and electricity

- Miners solve hard math problems

- Attacks are expensive due to hardware + energy costs

**Proof of Stake (PoS) — Ethereum**

- Requires locking up large amounts of crypto as stake

- Validators risk losing funds if they act dishonestly (slashing)

- Attacks require huge financial capital

⚠️ Important:
PoW and PoS are **not full consensus mechanisms.**
They are **Sybil resistance tools** that control who can participate.

## 2. Finality

Finality means a transaction is permanent and cannot be reversed.

- Banks can reverse transactions because they control the system

- Blockchains must decide finality without a central authority

Finality answers one question:
👉 When is a transaction 100% locked forever?

Different blockchains reach finality at different speeds.
