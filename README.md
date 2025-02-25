# MyNFT - ERC721 NFT Contract

## Overview
MyNFT is an ERC721-compliant smart contract that enables the creation of unique NFTs. The contract is designed to generate on-chain metadata and SVG images dynamically.

## Features
- Implements ERC721 standard using OpenZeppelin.
- Generates NFTs with on-chain metadata.
- Encodes metadata and SVG images in Base64 format.
- Uses a gradient-based dynamic SVG image.

## Technologies Used
- Solidity `^0.8.28`
- OpenZeppelin Contracts
- Base64 Encoding
- SVG for On-Chain Graphics

## Contract Details
### Deployment
The contract must be deployed on an Ethereum-compatible blockchain.

### Constructor
```solidity
constructor() ERC721("SAMUEL NFT", "SONFT") Ownable(msg.sender)
```
- Sets the token name and symbol.
- Initializes ownership to the deployer.

### Functions
#### `createNFT()`
```solidity
function createNFT() public onlyOwner returns (uint256)
```
- Mints a new NFT to the contract owner.
- Increments the token count.
- Returns the token ID.

#### `tokenURI(uint256 tokenId)`
```solidity
function tokenURI(uint256 tokenId) public view override returns (string memory)
```
- Returns a Base64-encoded JSON containing metadata.
- Includes the NFT name, description, and an SVG image.

#### `generateSVG(uint256 n)`
```solidity
function generateSVG(uint256 n) internal pure returns (string memory)
```
- Dynamically generates an SVG image based on token ID.
- Uses gradients to create a unique background for each NFT.

## Installation and Usage
1. Install dependencies:
   ```sh
   npm install @openzeppelin/contracts
   ```
2. Deploy the contract:
   ```solidity
   MyNFT myNft = new MyNFT();
   ```
3. Mint an NFT:
   ```solidity
   uint256 tokenId = myNft.createNFT();
   ```
4. Retrieve Metadata:
   ```solidity
   string memory uri = myNft.tokenURI(tokenId);
   ```

## License
This project is licensed under UNLICENSED.

