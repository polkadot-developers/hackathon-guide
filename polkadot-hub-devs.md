## 🚀 Smart Contract Development

Polkadot enables **smart contract deployment** via **PolkaVM**. This allows using familiar **Ethereum tools** and **libraries** while leveraging Polkadot’s robust ecosystem. **PolkaVM** is live on the Polkadot testnet Westend. ✅

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

- 🎥 [**Deploy Rust and Solidity contracts**](https://youtu.be/TGgpG1jPxeE) – a workshop showcasing how to deploy and interact with Solidity and Rust contracts on the Polkadot Hub
  - [46:27](https://youtu.be/TGgpG1jPxeE?t=2848): Deploy Solidity contract using Remix
  - [48:10](https://youtu.be/TGgpG1jPxeE?t=2890): Call Rust contract from Solidity contract (on a local testnet)
  - [48:27](https://youtu.be/TGgpG1jPxeE?t=2907): Run node with RPC exposed
  - [49:11](https://youtu.be/TGgpG1jPxeE?t=2951): Inspect Solidity contract
  - [50:26](https://youtu.be/TGgpG1jPxeE?t=3026): Run the commands `make` [..etc] to deploy the Rust contract
  - [52:26](https://youtu.be/TGgpG1jPxeE?t=3146): Run the commands to build and deploy the Solidity contract
  - [53:58](https://youtu.be/TGgpG1jPxeE?t=3238): See the gas estimates of both
  - [54:53](https://youtu.be/TGgpG1jPxeE?t=3293): Call Solidity contract that calls the Rust contract
  - [57:45](https://youtu.be/TGgpG1jPxeE?t=3465): Use polkatool to dissassemble the contract

### 🔑 How to Connect to Polkadot Hub

You can use any **Ethereum-compatible wallet** wallet to connect to Polkadot Hub.

For example, you can use [MetaMask](https://metamask.io/) and connect it to Polkadot Hub by following the [Connect your Wallet](https://papermoonio.github.io/polkadot-mkdocs/develop/smart-contracts/connect-to-polkadot/) guide.

### 💧 Polkadot Faucet

Need **testnet tokens**? Get some from the [**Polkadot Faucet**](https://faucet.polkadot.io/westend?parachain=1000) 💧

> **Note:** Use **Westend** network & select **AssetHub** chain!

### 🔎 Hub Explorer

[Blockscout Explorer for Westend Hub](https://blockscout-asset-hub.parity-chains-scw.parity.io/)

### 🏆 Starter Templates

Jumpstart your **smart contract dApp** with these templates:

- [**create-polkadot-dapp**](https://www.npmjs.com/package/create-polkadot-dapp?activeTab=readme) - a scaffolding tool to generate project boilerplates. Explore the `react-solidity` template located in the `templates` folder which comes pre-configured with **React, Tailwind CSS, and Ethers.js** for frontend interaction with your smart contracts

- [**hardhat-polkadot-example**](https://github.com/UtkarshBhardwaj007/hardhat-polkadot-example) - a demo for how to use Hardhat with Polkadot.

### 🧙 Alternative Smart Contract Languages

Besides **Solidity**, you can also use **Rust** to write smart contracts for Polkadot. The **ink!** library is a popular choice for Rust-based smart contract development.

- 🔗 [**ink! Docs**](https://use.ink/6.x) (compatible with Westend/Kusama Asset Hub from v6 )
