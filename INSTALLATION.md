# Installation Guide

This guide explains the installation steps for the LasMeta Soulbound Token (SBT) project.

## System Requirements

- Node.js (v16 or higher)
- npm or yarn
- MetaMask or compatible Web3 wallet
- Hardhat development environment

## Installation Steps

1. Clone the repository:
```bash
git clone https://github.com/lasmetaio/unique-id-sbt.git
cd unique-id-sbt
```

2. Install dependencies:
```bash
npm install
# or
yarn install
```

3. Set up environment variables:
```bash
cp .env.example .env
```
Update the .env file with your values:
- PRIVATE_KEY: Your wallet private key
- ETHERSCAN_API_KEY: Your Etherscan API key
- ALCHEMY_API_KEY: Your Alchemy API key

4. Compile the smart contract:
```bash
npx hardhat compile
```

5. Run tests:
```bash
npx hardhat test
```

## Contract Deployment

To deploy the SBT contract:

1. Configure your network in hardhat.config.js
2. Run deployment script:
```bash
npx hardhat run scripts/deploy.js --network <network-name>
```

## Verification

After deployment, verify your contract on Etherscan:
```bash
npx hardhat verify --network <network-name> <contract-address>
```

## Troubleshooting

If you encounter issues during installation:

1. Check your Node.js version
2. Clear npm cache: `npm cache clean --force`
3. Delete node_modules folder and reinstall
4. Visit our GitHub Issues page

## Support

For technical support:
- Discord: [LasMeta Discord](https://discord.gg/lasmeta)
- Email: support@lasmeta.io
- Docs: https://docs.lasmeta.io 