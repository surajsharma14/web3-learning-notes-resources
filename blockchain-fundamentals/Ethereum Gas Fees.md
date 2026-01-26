# Ethereum Gas Fees: A Deep Dive

## Why Gas Fees Are Necessary

Gas fees serve two critical functions ensuring network health and security:

### 1. Compensation for Validators

**Who:** Validators run software maintaining the network

**What they do:**
- Process transactions
- Execute smart contracts
- Add new blocks to blockchain

**Why gas fees:** Economic incentive to participate honestly and keep network running

### 2. Spam Prevention

**Without gas fees:**
- Malicious actors could flood network with millions of useless transactions
- System congestion
- Legitimate users blocked from processing transactions

**With gas fees:**
- Financial barrier makes spam attacks prohibitively expensive
- Protects network's limited block space

### Supply and Demand

**Block space is finite:**
- More users trying to submit transactions = higher demand
- Higher demand = higher gas fees required for inclusion
- Simple economics: limited supply + high demand = higher prices

## What is Gas?

**Gas** = Unit measuring computational work required to execute operations on Ethereum

**Analogy:** Fuel for the Ethereum Virtual Machine (EVM)
- Car needs gasoline to drive distance
- Transaction needs gas to pay for computational steps

### Example Transaction

**Ciara sends 10 ETH to Patrick:**

Transaction contains:
- **Recipient:** Patrick's wallet address
- **Value:** 10 ETH
- **Action:** Transfer specified value
- **Gas Fees:** Amount willing to pay for processing

**Process:**
1. Signed with Ciara's private key (proves ownership)
2. Broadcast to network
3. Validator includes in block

## Evolution of Gas Fee System

### Type 0: Legacy Transactions (Old Model)

**"First-price auction" model**

**User specifies:**
- `gasPrice`: Price per unit of gas (in Wei)
- `gasLimit`: Maximum gas transaction can consume

**Problems:**
- Had to **guess** what others were bidding
- Often led to:
  - **Overpaying** (to ensure inclusion)
  - **Underpaying** (transactions stuck pending for hours/days)
- Unpredictable during network congestion

### Type 2: EIP-1559 Transactions (Current Model)

**Introduced:** London Hard Fork

**Key Innovation:** Splits fee into two components

#### The Bus Analogy

**Legacy Model (Type 0):**
- Bus with limited seats
- Everyone shouts price they'll pay
- Driver picks highest bidders
- Must guess bid amount without knowing others' offers

**EIP-1559 Model (Type 2):**
- Fixed, non-negotiable ticket price (**base fee**)
- Same for everyone
- Price set by system based on how full previous bus was
- Optional tip (**priority fee**) to driver for faster boarding

#### Two Fee Components

##### 1. Base Fee (Network-Determined)

**What it is:**
- Minimum price per gas unit required for inclusion
- Determined algorithmically by network

**How it works:**
- Protocol targets **50% full blocks**
- Block >50% full → base fee **increases** next block
- Block <50% full → base fee **decreases** next block

**Critical feature:** **Base fee is BURNED**
- Permanently removed from ETH supply
- Creates deflationary pressure on Ethereum

##### 2. Priority Fee / Tip (User-Determined)

**What it is:**
- Optional fee paid directly to validator
- Incentivizes validators to prioritize your transaction

**When to use:**
- Times of high demand
- Need transaction processed urgently

**Result:** Far more predictable fees
- See current base fee
- Only decide on small optional tip if urgent

## ETH Denominations

Gas fees involve very small fractions of ETH, so smaller units are used:

### Wei
- **Smallest possible unit** of ETH

### Gwei (Giga-Wei)
- **Most common unit** for gas prices

**Conversions:**
