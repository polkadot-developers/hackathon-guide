## 🚀 Smart Contract Development

Polkadot enables **smart contract deployment** via **PolkaVM**. This allows using familiar **Ethereum tools** and **libraries** while leveraging Polkadot’s robust ecosystem. **PolkaVM** is live on Passet Hub, the Polkadot community testnet. ✅

*Refer to the [**known issues**](https://docs.google.com/document/d/1j5hnQZRqlbVagW28dC24OVAF8uRih5jWubBxy5PlMYc/edit?usp=sharing) document if you're running into issues deploying contracts or using any of the tools below. If you have a new bug or problem, please raise an issue in the [Contracts Bug tracker](https://github.com/paritytech/contract-issues) on Github.*

### 📚 Development Environments

There are multiple development environments already available for Polkadot smart contract development. Here are some of the most popular ones:

- 🖥️ [**Polkadot Remix IDE**](https://papermoonio.github.io/polkadot-mkdocs/develop/smart-contracts/dev-environments/remix/) - a web-based IDE that allows you to write, test, and deploy smart contracts directly in your browser. It's integrated with compatible chains: you can deploy right from the browser

- ⚒️ [**Hardhat**](https://papermoonio.github.io/polkadot-mkdocs/develop/smart-contracts/dev-environments/hardhat/) - a popular Ethereum development environment that can be used for Polkadot smart contract development with the help of custom plugins

### 👨‍💻 Contract Interaction Libraries

Several libraries can be used to interact with smart contracts deployed on Polkadot:

- 🔵 [**Ethers.js**](https://papermoonio.github.io/polkadot-mkdocs/develop/smart-contracts/libraries/ethers-js/)

- ⚡ [**viem**](https://papermoonio.github.io/polkadot-mkdocs/develop/smart-contracts/libraries/viem/)

- 🌐 [**Web3.js**](https://papermoonio.github.io/polkadot-mkdocs/develop/smart-contracts/libraries/web3-js/)

- 🐍 [**Web3.py**](https://papermoonio.github.io/polkadot-mkdocs/develop/smart-contracts/libraries/web3-py/)

- 🧙 [**Wagmi**](https://papermoonio.github.io/polkadot-mkdocs/develop/smart-contracts/libraries/wagmi/)

### 📚 Tutorials and Guides

Here you can find some useful tutorials and resources to help you get started with smart contract development on Polkadot:

- ✍️ [**Create a Smart Contract**](https://papermoonio.github.io/polkadot-mkdocs/tutorials/smart-contracts/launch-your-first-project/create-contracts/) - a step-by-step guide to creating your first smart contract on Polkadot

- ⚙️ [**Test and Deploy with Hardhat**](https://papermoonio.github.io/polkadot-mkdocs/tutorials/smart-contracts/launch-your-first-project/test-and-deploy-with-hardhat/) - a guide to testing and deploying your smart contract using Hardhat

- 🎨 [**Deploy a NFT**](https://papermoonio.github.io/polkadot-mkdocs/tutorials/smart-contracts/deploy-nft/) - a tutorial on deploying an NFT smart contract on Polkadot

- 💰 [**Deploy an ERC-20**](https://papermoonio.github.io/polkadot-mkdocs/tutorials/smart-contracts/deploy-erc20/) - a tutorial on deploying an ERC-20 token smart contract on Polkadot

- 🛠️ [**Create a dApp with Viem**](https://papermoonio.github.io/polkadot-mkdocs/tutorials/smart-contracts/launch-your-first-project/create-dapp-viem/) - a tutorial on creating a simple dApp using the Viem library

- 🛠️ [**Create a dApp with Ethers.js**](https://papermoonio.github.io/polkadot-mkdocs/tutorials/smart-contracts/launch-your-first-project/create-dapp-ethers-js/) - a tutorial on creating a simple dApp using the Ethers.js library

- 🎥 [**Deploy Rust and Solidity contracts**](https://youtu.be/TGgpG1jPxeE) – a workshop showcasing how to deploy and interact with Solidity and Rust contracts on the Polkadot Hub.

### 🔑 How to Connect to Polkadot Hub Testnet

You can use any **Ethereum-compatible wallet** wallet to connect to Polkadot Hub Testnet. Follow the [Connect your Wallet](https://papermoonio.github.io/polkadot-mkdocs/develop/smart-contracts/connect-to-polkadot#connect-your-wallet) guide to connect using MetaMask. We also recommend using [Talisman](https://talisman.xyz/), which is built for both Polkadot and Ethereum.

> Testnet details:
> * Network name: Passet Hub
> * Chain ID: 420420421
> * RPC URL: https://testnet-passet-hub-eth-rpc.polkadot.io
> * Block Explorer URL: https://blockscout-passet-hub.parity-testnet.parity.io/ 


### 💧 Polkadot Faucet

Need **testnet tokens**? Get some from the [**Testnet Faucet**](https://faucet.polkadot.io/?parachain=1111) 💧

> **Note:** Make sure you've selected the **Passet Hub** chain on the **Paseo** network!


### 🏆 Starter Templates

Jumpstart your **smart contract dApp** with these templates:

- [**create-polkadot-dapp**](https://www.npmjs.com/package/create-polkadot-dapp?activeTab=readme) - a scaffolding tool to generate project boilerplates. Explore the `react-solidity` template located in the `templates` folder which comes pre-configured with **React, Tailwind CSS, and Ethers.js** for frontend interaction with your smart contracts

- [**hardhat-polkadot-example**](https://github.com/UtkarshBhardwaj007/hardhat-polkadot-example) - a demo for how to use Hardhat with Polkadot.

### 🧙 Alternative Smart Contract Languages

Besides **Solidity**, you can also write smart contracts in Rust using **ink!** &mdash; the go-to language for Rust-based smart contract development on Polkadot. Check out the [**ink! Docs**](https://use.ink/6.x) (compatible with PolkaVM from v6 ) to get started.
