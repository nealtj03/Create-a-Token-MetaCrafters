# Create-a-Token-MetaCrafters
Getting Started with Solidity - Project: Create a Token
# MyToken Smart Contract

## Overview

**MyToken** is a basic implementation of a fungible token on the Ethereum blockchain, similar to an ERC20 token. It allows for minting and burning of tokens, with the ability to track balances of multiple addresses. This smart contract was built using Solidity version 0.8.18.

## Contract Details

### Token Properties:
- **Token Name**: `Tiktok`
- **Token Abbreviation**: `TKTK`
- **Total Supply**: Initially set to 0, but will increase as tokens are minted.

### Features:
1. **Minting**: Tokens can be minted (created) and assigned to any specified address.
2. **Burning**: Tokens can be burned (destroyed) from a specified address, reducing the total supply.
3. **Balance Tracking**: The contract tracks how many tokens each address holds.

## Variables

1. **tokenName**: A string representing the name of the token (in this case, `Tiktok`).
2. **tokenAbbrv**: A string representing the token abbreviation (in this case, `TKTK`).
3. **totalSupply**: A public uint that stores the total supply of the token.
4. **balances**: A mapping from addresses to their respective token balances (`address => uint`).

## Functions

### 1. `mint(address _address, uint _value)`

This function is used to mint (create) new tokens and assign them to a specified address. The total supply of the token is increased by the minted amount, and the balance of the recipient is updated.

- **Parameters**:
  - `_address`: The address where the newly minted tokens will be sent.
  - `_value`: The amount of tokens to mint.

- **Key Points**:
  - The total supply is increased by the minted amount.
  - The balance of the provided address is updated.
  - Emits a `Mint` event.

### 2. `burn(address _address, uint _value)`

This function is used to burn (destroy) tokens from a specified address. The total supply of the token is decreased by the burned amount, and the balance of the specified address is reduced.

- **Parameters**:
  - `_address`: The address from which tokens will be burned.
  - `_value`: The amount of tokens to burn.

- **Key Points**:
  - The function checks if the address has enough tokens to burn.
  - The total supply is decreased by the burned amount.
  - The balance of the provided address is reduced.
  - Emits a `Burn` event.

## Events

- **Mint**: Emitted when tokens are minted.
- **Burn**: Emitted when tokens are burned.

## Example Usage

### Minting Tokens:
```solidity
// Mint 1000 tokens to a specific address
myToken.mint(0xAbc..., 1000);
