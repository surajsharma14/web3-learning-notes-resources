## Proof of Work Blockchains
**Core Concept** <br>
Proof of Work (PoW) is the consensus mechanism that secures blockchains like Bitcoin through computational puzzles and decentralized validation.<br>
**Cryptographic Foundation: Hashing** <br> <br>

What is a Hash?
A unique, fixed-length string generated from any data using a hash function (e.g., SHA256 for Bitcoin, Keccak256 for Ethereum).
Two Critical Properties:
 
Fixed Length: Any input size → same output length (SHA256 = 64 hex characters)
Determinism: Same input = same hash; tiny change = completely different hash

Hashes act as digital fingerprints for data.
Mining and Proof of Work
Block Structure
Contains:

Block number
Data (transactions)
Nonce (special number)
Previous block's hash  
