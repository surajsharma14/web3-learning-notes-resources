# Blockchain Vulnerabilities

## Core Principle
Blockchain security doesn't make attacks impossible—it makes them **economically irrational**. Major networks like Bitcoin and Ethereum are designed so honest participation is always more profitable than attacking.

## Major Attack Types   

### 1. Sybil Attacks
- **What it is**: Single entity creates many fake identities/nodes to gain majority control
- **Goal**: Outvote honest participants ("one person pretending to be many")
- **Potential damage**: Approve fraud, double-spend, censor transactions, rewrite history
- **Defense mechanisms**:
  - **PoW (Bitcoin)**: Requires real computational power (hash rate), not just fake nodes. Attackers must spend massive energy/capital on mining hardware
  - **PoS (Ethereum)**: Requires real economic stake (locked ETH). Can't fake cryptocurrency ownership

### 2. 51% Attack (Majority Attack)
- **PoW version**: Control 51%+ of network hash rate to create alternate chain faster than honest nodes
- **PoS version**: Control 51%+ of staked ETH to manipulate fork choice; need 67%+ for complete control (finality)
- **Example**: Spend Bitcoin for a car, then rewrite history so transaction never happened—keep both car and Bitcoin
- **Why it fails**:
  - Costs tens of billions of dollars
  - Social layer defense: Community would reject malicious chain via hard fork, making investment worthless

### 3. Blockchain Reorganization (Re-orgs)
- **Natural re-orgs**: Small, harmless re-orgs occur in PoW when two miners find blocks simultaneously
- **Why confirmations matter**: More blocks on top = deeper burial = safer from re-orgs
- **PoS difference**: Finality mechanism makes malicious re-orgs much harder

### 4. MEV & Sandwich Attacks
- **MEV**: Maximal Extractable Value—profit from controlling transaction order in blocks
- **Sandwich attack process**:
  1. User submits large buy order → enters mempool
  2. Bot detects it and **front-runs** with higher gas fee, buying first (price rises slightly)
  3. User's order executes at higher price (pushes price up more)
  4. Bot **back-runs** by immediately selling at peak for guaranteed profit
- **Result**: User pays more (slippage), bot profits risk-free
- **Status**: Seen as unfair but currently permitted

### 5. Software Bugs
- **Example**: 2010 Bitcoin bug created 184 billion BTC (violating 21 million cap) due to integer overflow
- **Solution**: Community fixed bug and hard forked to pre-attack state
- **Lesson**: Code auditing and testing are critical

### 6. Replay Attacks
- **What it is**: Valid transaction from one chain replayed on compatible chain (like cashing a photocopied check twice)
- **Protections**:
  - **Chain ID**: Unique identifier per blockchain—transaction signed for one chain is invalid on others
  - **Nonce**: Transaction counter per account (0, 1, 2...) ensures each transaction processes only once

## Key Takeaways
- Most attacks are **economically infeasible** on major blockchains
- Smaller blockchains with fewer participants/less stake are more vulnerable
- Security comes from economic incentives, not technical impossibility
- Social consensus serves as final defense layer
