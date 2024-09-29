# Deploy contract on Linea

## Setting up the necessary dependencies

A simple guide on how to deploy a smart contract on the Linea mainnet. This repository includes step-by-step instructions for deploying a basic contract using Hardhat and interacting with the Linea Network.

Clone the repository to your desired location and run the npm command to set up the development environment. All dependencies are already defined in the ***package.json*** file.

```bash
npm install
```

Now, run a test in a local Hardhat environment and try deploying the sample contract:

```bash
npx hardhat node
npx hardhat run scripts/deploy.js --network localhost
```
## Deploying to the Linea network

Once the deployment is done in the local Hardhat environment, you can attempt to deploy it directly to the Linea mainnet or to a test network with no gas fees. To do this, configure the test network in the ***hardhat.config.js*** file, which already includes two pre-configured networks: *Ethereum’s Sepolia testnet* and the *Linea network*.

You can add any RPC endpoint of your choice. In this example, we’re using ***INFURA’s RPC***.

To ensure the following commands run correctly, configure the ***.env*** file by adding your ***INFURA_API_KEY*** and your account’s private key ***ACCOUNT_PRIVATE_KEY***. Make sure to add *.env* to your *.gitignore* file to avoid accidentally exposing your private keys in a public repository.

Once you’ve set up the network correctly, you can run the following commands to deploy the contract to your preferred network. For example, to deploy on the Linea mainnet:

```bash
npx hardhat run scripts/deploy.js --network linea-mainnet
```

To verify if everything worked as expected, go to the block explorer of the network where you deployed the contract. Using the *EVM address* of the account that you provided the private key for in the *.env* file, check the block explorer to view your contract deployment.

## Final Considerations

With this project structure, you can deploy any contract on any network by making a few simple adjustments. For instance, to deploy a different contract, just add it to the contracts folder and update the contract name in the *deploy.js* file. To deploy to another network, modify the *hardhat.config.js* file by adding the new network's RPC endpoint and name, following the example of the already configured networks.
