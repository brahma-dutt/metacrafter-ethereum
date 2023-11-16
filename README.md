 MyToken Smart Contract

This Solidity smart contract, named MyToken, is a basic implementation of an ERC-20 token. It includes features such as minting and burning tokens. Below are details about the contract.

## Overview

- *Token Name:* meta
- *Token Abbreviation:* mta
- *Total Supply:* 0

## Functions

### Mint Function

The `mint` function allows the creation of new tokens. It increases the total supply and adds the specified number of tokens to the balance of a given address.

```solidity
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balance[_address] += _value;
}
Burn Function
The burn function enables the destruction of existing tokens. It checks if the address has a sufficient balance before reducing the total supply and then performs action.
