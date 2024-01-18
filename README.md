# Token Contract 

## Overview

This Solidity smart contract represents a basic ERC-20 token named "Token" with the symbol "Tkn". The contract includes functionality for token initialization, minting, burning, transferring, and checking account balances. Additionally, it introduces features like disabling token transfers and specifying originator and founder addresses.

## Contract Details

- **SPDX-License-Identifier:** MIT
- **Solidity Version:** ^0.8.17
- **Dependencies:** OpenZeppelin ERC20.sol

## Contract Structure

### State Variables

- **originator:** The address that deployed the contract and has special privileges.
- **founder:** Another privileged address with specific functions.
- **isTokenEnabled:** A flag indicating whether the token has been initialized.
- **transferAmount:** A flag to enable or disable token transfers.

### Modifiers

- **onlyOriginator:** Restricts functions to be callable only by the originator.
- **onlyFounder:** Restricts functions to be callable only by the founder.

### Constructor

- Initializes the contract with default values, sets the originator and founder addresses, and disables token transfers.

### Functions

1. **initializeToken():** Enables token transfers and mints 100 tokens to the originator's account.

2. **mintTokens(address receiver, uint256 sendSum):** Mint tokens to the specified receiver's address. Only callable by the originator.

3. **burnTokens(uint256 burnedSum):** Burns a specified amount of tokens from the sender's account.

4. **transferTokens(address recipient, uint256 transferredSum):** Transfers a specified amount of tokens from the sender to the recipient.

5. **getBalanceOfAccount(address account):** Retrieves the token balance of a specified account.

6. **disableAmountTransfer():** Disables token transfers. Only callable by the originator.

## Usage

1. **Deploy the Contract:** Deploy the contract to the Ethereum blockchain.

2. **Initialization:** Call the `initializeToken` function to enable token transfers and mint initial tokens.

3. **Minting Tokens:** The originator can mint additional tokens using the `mintTokens` function.

4. **Burning Tokens:** Use the `burnTokens` function to burn a specified amount of tokens.

5. **Transferring Tokens:** Transfer tokens between accounts using the `transferTokens` function.

6. **Check Balance:** Utilize the `getBalanceOfAccount` function to check the token balance of a specific account.

7. **Disable Token Transfers:** Call the `disableAmountTransfer` function to disable further token transfers.

