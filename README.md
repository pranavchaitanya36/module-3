# Bullet Token (BTK) Smart Contract

## Overview

Bullet Token (BTK) is an ERC-20 token implemented on the Ethereum blockchain. This contract allows for the creation, minting, burning, and transferring of BTK tokens. Additionally, it includes special functions to mint tokens (Mint_TK) and burn tokens (Burn_TK) with specific permissions.

## Features

- **Minting:** The contract creator can mint a predefined amount of BTK during deployment.
- **Custom Minting:** The addressee can mint additional BTK tokens by calling the `Mint_TK` function.
- **Burning:** Token holders can burn their BTK tokens using the `Burn_TK` function.
- **Transfers:** Standard ERC-20 token transfer functionality using the `transfer_TK` function.

## Getting Started

Example usage:

```solidity
// Deploy contract
const bulletToken = await BulletToken.deploy("Bullet Token", "BTK", 18, 1000000);

// Mint additional tokens
await bulletToken.Mint_TK(someAddress, 100000);

// Burn tokens
await bulletToken.Burn_TK(50000);

// Transfer tokens
await bulletToken.transfer_TK(anotherAddress, 20000);
```

## Functions

### `Mint_TK`

```solidity
function Mint_TK(address Addressee, uint256 count) public
```

Mints a specified number of BTK tokens and assigns them to the specified address. Only the addressee (initial deployer) has permission to call this function.

### `Burn_TK`

```solidity
function Burn_TK(uint256 count) public
```

Burns a specified number of BTK tokens from the caller's balance.

### `transfer_TK`

```solidity
function transfer_TK(address donee, uint256 count) public returns (bool)
```

Transfers a specified number of BTK tokens from the caller's address to the specified donee's address.


## Acknowledgments

- OpenZeppelin for the ERC-20 token implementation.

