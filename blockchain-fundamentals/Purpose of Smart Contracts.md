# Solidity Types

## Elementary Data Types

Solidity supports various elementary types that can be combined to create more complex ones. 

### Basic Types 

- **Boolean (bool)**: `true` or `false` 
- **Unsigned Integer (uint)**: Unsigned whole number (positive only)
- **Integer (int)**: Signed whole number (positive and negative)
- **Address (address)**: 20-byte value (e.g., Ethereum wallet address)
- **Bytes (bytes)**: Low-level raw byte data 

## Variables Definition

**Variable** = Placeholder for a **value** of a specific **data type**.

### Example
```solidity
bool hasFavoriteNumber = true; // Variable holds value `true`
```

### Bit Specification

- Can specify number of bits for `uint` and `int`
- `uint256` = 256 bits
- `uint` = shorthand for `uint256`

> **Note:** Always be **explicit** with data type length for better code clarity.

### Semicolons

The semicolon (`;`) at the end of each line signifies that a statement is complete.

### Complete Example
```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.19;

contract SimpleStorage {
    // Basic types
    bool hasFavoriteNumber = true;
    uint256 favoriteNumber = 88;
    string favoriteNumberInText = "eighty-eight";
    int256 favoriteInt = -88;
    address myAddress = 0xaB1B7206AA6840C795aB7A6AE8b15417b7E63a8d;
    bytes32 favoriteBytes32 = "cat";
}
```

## Bytes and Strings

### Bytes

**Bytes** = Collection of characters in hexadecimal representation

#### Types

- **Fixed-size**: `bytes1` to `bytes32`
- **Dynamic-size**: `bytes`
```solidity
bytes1 minBytes = "I am a fixed size byte array of 1 byte";
bytes32 maxBytes = "I am a fixed size byte array of 32 bytes";
bytes dynamicBytes = "I am a dynamic array, so you can manipulate my size";
```

### Strings

**Strings** are internally represented as dynamic byte arrays (`bytes` type), designed specifically for text. Strings can easily be converted to bytes.

## Default Values

> **Important:** Every variable in Solidity has a default value if not initialized.

| Type | Default Value |
|------|---------------|
| `bool` | `false` |
| `uint256` | `0` |
| `int256` | `0` |
| `string` | `""` (empty string) |
| `address` | `0x0000000000000000000000000000000000000000` |
| `bytes` | `""` (empty) |
| `bytes32` | `0x0000000000000000000000000000000000000000000000000000000000000000` |

### Example
```solidity
uint256 favoriteNumber; // Defaults to 0
```

## Practice Exercises

### 1. What's the difference between a variable and a value?

**Answer:**
- **Value**: The actual data stored (e.g., `88`, `true`, `"hello"`)
- **Variable**: A named placeholder/container that holds a value and has a specific data type

Example: In `uint256 favoriteNumber = 88;`, `favoriteNumber` is the variable and `88` is the value.

### 2. Describe the default value of the following types

| Type | Default Value |
|------|---------------|
| `bool` | `false` |
| `uint` | `0` |
| `int256` | `0` |
| `string` | `""` (empty string) |
| `address` | `0x0000000000000000000000000000000000000000` |
| `bytes` | `""` (empty bytes) |
| `bytes32` | `0x0000000000000000000000000000000000000000000000000000000000000000` |

### 3. How does uint differ from bytes?

**Answer:**
- **uint**: Represents unsigned integer numbers (whole numbers only, no decimals). Used for mathematical operations and counting.
- **bytes**: Represents raw byte data in hexadecimal. Used for storing arbitrary data, text (when converted) or binary information.

**Key difference:** `uint` is for numerical operations, `bytes` is for data storage and manipulation.

### 4. Smart contract with five storage variables
```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.19;

contract MyContract {
    bool isActive = true;
    uint256 totalSupply = 1000000;
    address owner = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4;
    string projectName = "My DeFi Protocol";
    bytes32 secretCode = "blockchain";
    int256 temperature = -15;
}
```

## Resources

- [Solidity Documentation - Types](https://docs.soliditylang.org/en/v0.8.20/types.html#types)
- [Bits and Bytes Overview](https://www.youtube.com/watch?v=Dnd28lQHquU)
