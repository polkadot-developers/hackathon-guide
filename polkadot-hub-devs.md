## 🚀 Smart Contract Development on Polkadot

Polkadot enables **smart contract deployment** via **PolkaVM**. This allows using familiar **Ethereum tools** and **libraries** while leveraging Polkadot’s robust ecosystem. **PolkaVM** is live on Passet Hub, the Polkadot community testnet. ✅

Please provide **feedback** on your experience deploying smart contracts on Polkadot using this [feedback form](https://forms.gle/BhL5ZCaFMUvSipos8). 

*Refer to the [**known issues**](https://docs.google.com/document/d/1j5hnQZRqlbVagW28dC24OVAF8uRih5jWubBxy5PlMYc/edit?usp=sharing) document if you're running into issues deploying contracts or using any of the tools below. If you have a new bug or problem, please raise an issue in the [Contracts Bug tracker](https://github.com/paritytech/contract-issues) on Github.*

### 🚀 Quick Start with DevContainers

- To speed things up and have your "batteries included" dev environment, you can use [DevContainers](https://code.visualstudio.com/docs/devcontainers/containers). They are regularly maintained and tested by the ecosystem professionals. You can find the configuration for Polkadot smart contract development in the [smart-contracts-devcontainer](https://github.com/paritytech/smart-contracts-devcontainer) repository.
- To use it, you need to have [Docker](https://www.docker.com/products/docker-desktop) or [Podman](https://podman.io/docs/installation) installed and running on your machine. You also need the Vscode extension for DevContainers. You can install it from the [VSCode Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers).
- Once Docker is running and the DevContainers extension is installed, simply create a new folder and run the following command to get started:

```bash
curl -fsSL https://raw.githubusercontent.com/paritytech/smart-contracts-devcontainer/main/.devcontainer/fetch-devcontainer.sh | bash -s --
```

### 📚 Solidity Development Environments

There are multiple development environments already available for Polkadot smart contract development. Here are some of the most popular ones:

- 🖥️ [**Polkadot Remix IDE**](https://docs.polkadot.com/develop/smart-contracts/dev-environments/remix/) - a web-based IDE that allows you to write, test, and deploy smart contracts directly in your browser. It's integrated with compatible chains: you can deploy right from the browser

- ⚒️ [**Hardhat**](https://docs.polkadot.com/develop/smart-contracts/dev-environments/hardhat/) - a popular Ethereum development environment that can be used for Polkadot smart contract development with the help of custom plugins
- 🤠 [**Foundry**](https://docs.polkadot.com/develop/smart-contracts/dev-environments/foundry/) - a smart contract development toolchain that manages your dependencies, compiles your project, runs tests, deploys, and lets you interact with thec ontracts.

### 🦀 Rust Contracts

Besides **Solidity**, you can also write smart contracts in Rust using **ink!** &mdash; the go-to language for Rust-based smart contract development on Polkadot. Check out the [**ink! Docs**](https://use.ink/6.x) (compatible with PolkaVM from v6 ) to get started.

### 👨‍💻 Contract Interaction Libraries

Several libraries can be used to interact with smart contracts deployed on Polkadot for both Solidity and Rust.

**Solidity**

- 🔵 [**Ethers.js**](https://docs.polkadot.com/develop/smart-contracts/libraries/ethers-js/)

- ⚡ [**viem**](https://docs.polkadot.com/develop/smart-contracts/libraries/viem/)

- 🌐 [**Web3.js**](https://docs.polkadot.com/develop/smart-contracts/libraries/web3-js/)

- 🐍 [**Web3.py**](https://docs.polkadot.com/develop/smart-contracts/libraries/web3-py/)

- 🧙 [**Wagmi**](https://docs.polkadot.com/develop/smart-contracts/libraries/wagmi/)

**ink!**

- 🥸 [**PAPI**](https://papi.how/ink)

### 📚 Tutorials and Guides

Here you can find some useful tutorials and resources to help you get started with smart contract development on Polkadot:

- ✍️ [**Create a Smart Contract**](https://docs.polkadot.com/tutorials/smart-contracts/launch-your-first-project/create-contracts/) - a step-by-step guide to creating your first smart contract on Polkadot

- ⚙️ [**Test and Deploy with Hardhat**](https://docs.polkadot.com/tutorials/smart-contracts/launch-your-first-project/test-and-deploy-with-hardhat/) - a guide to testing and deploying your smart contract using Hardhat

- 🎨 [**Deploy a NFT**](https://docs.polkadot.com/tutorials/smart-contracts/deploy-nft/) - a tutorial on deploying an NFT smart contract on Polkadot

- 💰 [**Deploy an ERC-20**](https://docs.polkadot.com/tutorials/smart-contracts/deploy-erc20/) - a tutorial on deploying an ERC-20 token smart contract on Polkadot

- 🛠️ [**Create a dApp with Viem**](https://docs.polkadot.com/develop/smart-contracts/libraries/viem/) - a tutorial on creating a simple dApp using the Viem library

- 🛠️ [**Create a dApp with Ethers.js**](https://docs.polkadot.com/develop/smart-contracts/libraries/ethers-js/) - a tutorial on creating a simple dApp using the Ethers.js library

- 🎥 [**Deploy Rust and Solidity contracts**](https://youtu.be/TGgpG1jPxeE) – a workshop showcasing how to deploy and interact with Solidity and Rust contracts on the Polkadot Hub.

### 🔑 How to Connect to Polkadot Hub Testnet

You can use any **Ethereum-compatible wallet** wallet to connect to Polkadot Hub Testnet. Follow the [Connect your Wallet](https://docs.polkadot.com/develop/smart-contracts/connect-to-polkadot/) guide to connect using MetaMask. We also recommend using [Talisman](https://talisman.xyz/), which is built for both Polkadot and Ethereum.

```
Testnet details:
* Network name: Passet Hub
* Chain ID: 420420421
* RPC URL: https://testnet-passet-hub-eth-rpc.polkadot.io
* Block Explorer URL: https://blockscout-passet-hub.parity-testnet.parity.io/
```


### 💧 Polkadot Faucet

Need **testnet tokens**? Get some from the [**Testnet Faucet**](https://faucet.polkadot.io/?parachain=1111) 💧

> **Note:** Make sure you've selected the **Passet Hub** chain on the **Paseo** network!


### 🏆 Starter Templates

Jumpstart your **smart contract dApp** with these templates:

- [**create-polkadot-dapp**](https://www.npmjs.com/package/create-polkadot-dapp?activeTab=readme) - a scaffolding tool to generate project boilerplates. Explore the `react-solidity` template located in the `templates` folder which comes pre-configured with **React, Tailwind CSS, and Ethers.js** for frontend interaction with your smart contracts

- [**hardhat-polkadot-example**](https://github.com/UtkarshBhardwaj007/hardhat-polkadot-example) - a demo for how to use Hardhat with Polkadot.


### Vibe coding with AI: LLM configuration helper

- If using AI tools like LLMs, remember to direct them to use the most [up-to-date documentation](https://docs.polkadot.com/).

- Especially if you are using Claude, [this document](https://www.kusamahub.com/downloads/LLMCONTRACTS.md) contains configuration settings for using the testnet to deploy smart contracts, and we recommend informing your LLM to refer to it.  
