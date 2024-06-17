# Lasmeta Soulbound Token Smart Contract

## Overview

The `SoulBounds` contract allows minting, burning, and managing non-transferable Soulbound Tokens (SBTs). These tokens represent unique identities that are non-transferable and can have associated metadata. The contract ensures the uniqueness of each soul by validating identities and URLs. It also supports secure withdrawal of tokens and validates contract interactions.

## Tech Stack

- **Solidity**
- **OpenZeppelin Contracts**
  - `SafeERC20`
  - `Pausable`
  - `ERC721Enumerable`
  - `ERC721`
  - `ERC721Holder`
  - `ERC2981`

## Soulbound Tokens (SBTs)

Soulbound Tokens are unique, non-transferable tokens that represent an individual's identity or attributes on the blockchain. Unlike traditional tokens, SBTs cannot be transferred between addresses, ensuring that the identity or attribute they represent remains unique to the owner.

### Features of SBTs

- **Non-Transferable**: SBTs cannot be transferred once minted, ensuring the uniqueness of the identity or attribute.
- **Metadata Management**: Each SBT can have associated metadata that can be updated or deleted by the owner.
- **Validation**: Ensures that each soul (identity) is unique by validating UUIDs and URLs.
- **Royalties**: Supports setting royalties for the tokens using ERC2981.
- **Event Notifications**: Emits events for key actions such as minting, burning, and updating tokens.

## Features

- **Minting and Burning**: Users can mint new SBTs and burn existing ones.
- **Metadata Management**: Owners can add, update, and delete metadata associated with their SBTs.
- **Trading Control**: Admin can enable or disable trading of identities as NFTs.
- **Administrative Control**: Allows the owner to manage various configurations, enable trading, and withdraw tokens.
- **Event Notifications**: Emits events for important actions like minting, burning, updating, and withdrawals.

### Metadata Management

The contract allows the owner to manage metadata associated with each SBT. This includes:

- Adding new metadata keys and values.
- Updating existing metadata.
- Deleting metadata keys.

### Trading Control

The contract provides an admin feature to enable or disable the trading of SBTs. When trading is enabled, SBTs can be transferred between addresses. When trading is disabled, all transfer functions are restricted.

### ERC2981 Royalties

The contract supports ERC2981, allowing the setting of royalty information for SBTs. This includes specifying a royalty receiver and the royalty fee numerator. For more details, refer to the [ERC2981 specification](https://eips.ethereum.org/EIPS/eip-2981).

## Events

- `Mint(address indexed _soul, uint256 _tokenId)`
- `Burn(address indexed _soul, uint256 _tokenId)`
- `Update(address indexed _soul, uint256 _tokenId)`
- `Withdrawal(address indexed _owner, address indexed _destination, uint256 indexed _amount)`
- `NativeTokenReceived(address indexed _sender, uint256 indexed _amount)`
- `PaymentTokenUpdated(address indexed _paymentToken)`
- `MintingPriceUpdated(uint256 indexed _mintingPrice)`
- `TradePeriodUpdated(bool indexed _tradeOnOff)`
- `MintingSessionHasStarted()`
- `MintingSessionHasStopped()`

## Security

- **Pausable Functionality**: Allows pausing of contract operations in case of emergency.
- **Reentrancy Protection**: Prevents reentrancy attacks for secure contract interactions.
- **Royalty Support**: Supports ERC2981 for setting royalties on tokens.

## Resources

- [ERC721](https://eips.ethereum.org/EIPS/eip-721)
- [ERC2981](https://eips.ethereum.org/EIPS/eip-2981)