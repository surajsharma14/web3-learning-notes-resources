# The Complete Lifecycle of an Ethereum Transaction

## Core Concept

**Transaction** = Signed message instructing network to perform action that alters blockchain **state** (complete record of all account balances and smart contract data).

**Example**: Ciara sends 1 ETH to Patrick → State changes from Ciara: 1 ETH, Patrick: 0 ETH to Ciara: 0 ETH, Patrick: 1 ETH

## Transaction Lifecycle Steps

### Step 1: Creating the Transaction

Wallet assembles transaction object with:

- **Chain ID**: Identifies target blockchain, prevents replay attacks
- **Nonce**: Transaction counter (starts at 0), ensures sequential processing
- **Gas Parameters**: Max priority fee (tip), max fee per gas, gas limit
- **Transaction Details**: Recipient address, ETH value, data (for smart contracts), access list

### Step 2: Signing the Transaction

1. Transaction data serialized and **hashed** → creates unique **Transaction Hash**
2. Sign hash with **private key** → creates **digital signature** (proof of authorization)

### Step 3: Broadcasting

Wallet sends signed transaction to Ethereum node via **RPC endpoint**

### Step 4: Mempool

- Node validates signature and sufficient balance
- If valid, added to **Mempool** ("waiting room" for pending transactions)
- Broadcast to peers across network

### Step 5: Block Selection

**Every 12 seconds** (one "slot"):
- One validator selected as block producer
- Selects transactions from mempool (prioritizes highest tips)
- Executes transactions, updates state, creates new block
- Signs and broadcasts proposed block

### Step 6: Attestation & Finalization

**Attestation**: Committee of validators re-executes transactions, verifies correctness, votes

**Inclusion**: If ≥2/3 of committee's staked ETH attests → block added to chain (**confirmed**, ~12 seconds)

**Finalization**: Once ≥2/3 of all active validators attest (after ~2 epochs/6.4 minutes) → block is **irreversible** (~12.8 minutes total)

## Transaction Statuses

- **Pending**: In mempool waiting
- **Confirmed**: Included in block added to chain (~12 seconds)
- **Finalized**: Block is irreversible (~12.8 minutes)
- **Reverted**: Execution failed, state rolled back, gas still consumed
- **Dropped**: Removed from mempool before inclusion

## Key Takeaway

Every step (signature → attestation) ensures blockchain state changes are **authorized, valid and permanent** for Externally Owned Accounts (EOAs).
