# 🌟 Polkadot Hackathon Survival Guide 🌟

## 👋 Introduction

Welcome to the **Polkadot Hackathon Survival Guide**! This resource is your go-to companion for navigating the world of **Polkadot development** during the hackathon. 

Whether you're a **blockchain pro** or just starting with **Polkadot**, this guide has all the essential info, tips, and resources to help you shine. ✨

From setting up your **development environment** to **presenting your project**, we’ve got you covered. The focus of this guide is **smart contract development** and bootstrapping Polkadot Hub launch, but it also provides guidance for **parachain runtime development**. 

Good luck, and **happy hacking!** 🚀

## 🌟 Development Pathways

Developers can follow different paths to build applications and core blockchain functionality. Each pathway fits different **project types** and **skill levels**, all contributing to the **broader Polkadot ecosystem**. 

The Polkadot ecosystem provides multiple development pathways:

<img width="1109" alt="image" src="https://github.com/user-attachments/assets/5c5bf50a-1906-4f04-9478-0d3bcc70649b" />

## 🚀 Smart Contract Development

Polkadot will enable **smart contract deployment** via **PolkaVM**. This allows devs to use familiar **Ethereum tools** and **libraries** while leveraging Polkadot’s robust ecosystem. **PolkaVM** is live on the Polkadot testnet Westend. ✅

### 📚 Development Environments

There are multiple development environments already available for Polkadot smart contract development. Here are some of the most popular ones:

- 🖥️ [**Polkadot Remix IDE**](https://papermoonio.github.io/polkadot-mkdocs/develop/smart-contracts/dev-environments/remix/) - a web-based IDE that allows you to write, test, and deploy smart contracts directly in your browser

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

### 🔑 How to Connect to Polkadot Hub

You can use any **Ethereum-compatible wallet** wallet to connect to Polkadot Hub.

For example, you can use [MetaMask](https://metamask.io/) and connect it to Polkadot Hub by following the [Connect your Wallet](https://papermoonio.github.io/polkadot-mkdocs/develop/smart-contracts/connect-to-asset-hub/#connect-your-wallet) guide.

### 💧 Polkadot Faucet

Need **testnet tokens**? Get some from the [**Polkadot Faucet**](https://faucet.polkadot.io/westend?parachain=1000) 💧

> **Note:** Use **Westend** network & select **AssetHub** chain!

### 🔎 Hub Explorer

[Blockscout Explorer for Westend Hub](https://blockscout-asset-hub.parity-chains-scw.parity.io/)

### 🏆 Starter Templates

Jumpstart your **smart contract dApp** with these templates:

- [**create-polkadot-dapp**](https://www.npmjs.com/package/create-polkadot-dapp?activeTab=readme) - a scaffolding tool to generate project boilerplates. Explore the `react-solidity` template located in the `templates` folder which comes pre-configured with **React, Tailwind CSS, and Ethers.js** for frontend interaction with your smart contracts

### 🧙 Alternative Smart Contract Languages

Besides **Solidity**, you can also use **Rust** to write smart contracts for Polkadot. The **ink!** library is a popular choice for Rust-based smart contract development.

- 🔗 [**ink! Docs**](https://use.ink/6.x) (compatible with Westend/Kusama Asset Hub from v6 )

## 🌍 Parachain Development

The [**Polkadot SDK**](https://github.com/paritytech/polkadot-sdk/tree/polkadot-stable2412) is a powerful and versatile developer kit designed to facilitate building **custom blockchains**, **parachains**, **generalized rollups**, and **more**.

### 💾 Installation

Follow the [**Install Polkadot SDK Dependencies**](https://docs.polkadot.com/develop/parachains/install-polkadot-sdk/) guide.

### 📚 Getting Started

The Parachain **Zero To Hero Tutorials** provide developers with a series of step-by-step guides to **building, testing, and deploying** custom pallets and runtimes using the Polkadot SDK. These tutorials are designed to help you gain hands-on experience and understand the core concepts of parachain development.

- 🚀 [**Parachain Zero To Hero Tutorials**](https://docs.polkadot.com/tutorials/polkadot-sdk/parachains/zero-to-hero/)

### 🌟 Parachain Templates

Using **pre-built templates** is an efficient way to begin building a custom blockchain. Templates provide a foundational setup with pre-configured modules, letting developers avoid starting from scratch and instead focus on customization.

Within the Polkadot SDK, the following **templates** are available to get you started:

- [**`minimal-template`**](https://github.com/paritytech/polkadot-sdk/tree/master/templates/minimal) - includes only the essential components necessary for a functioning blockchain. It’s ideal for developers who want to gain familiarity with blockchain basics and test simple customizations before scaling up

- [**`solochain-template`**](https://github.com/paritytech/polkadot-sdk/tree/master/templates/solochain) - provides a foundation for creating standalone blockchains with moderate features, including a simple consensus mechanism and several core FRAME pallets. It’s a solid starting point for developers who want a fully functional chain that doesn’t depend on a relay chain

- [**`parachain-template`**](https://github.com/paritytech/polkadot-sdk/tree/master/templates/parachain) - designed for connecting to relay chains like Polkadot, Kusama, or Paseo, this template enables a chain to operate as a parachain. For projects aiming to integrate with Polkadot’s ecosystem, this template offers a great starting point

In addition, several **external templates** offer unique features and can align with specific use cases or developer familiarity:

- [**`OpenZeppelin`**](https://github.com/OpenZeppelin/polkadot-runtime-templates/tree/main) - offers two flexible starting points:
    - The [`generic-runtime-template`](https://github.com/OpenZeppelin/polkadot-runtime-templates/tree/main/generic-template) provides a minimal setup with essential pallets and secure defaults, creating a reliable foundation for custom blockchain development
    - The [`evm-runtime-template`](https://github.com/OpenZeppelin/polkadot-runtime-templates/tree/main/evm-template) enables EVM compatibility, allowing developers to migrate Solidity contracts and EVM-based dApps. This template is ideal for Ethereum developers looking to leverage Substrate's capabilities

- [**`Tanssi`**](https://github.com/moondance-labs/tanssi/tree/master/container-chains/runtime-templates) - provides developers with pre-built templates that can help accelerate the process of creating appchain

- [**`Pop Network`**](https://learn.onpop.io/appchains/pop-cli/new#templates) - designed with user-friendliness in mind, Pop Network offers an approachable starting point for new developers, with a simple CLI interface for creating appchains 

Choosing a suitable template depends on your project’s **unique requirements, level of customization, and integration needs**. Starting from a template **speeds up development and lets you focus on implementing your chain’s unique features** rather than the foundational blockchain setup.

### ⚙️ How to Build a Custom Parachain

Learn how Polkadot SDK’s FRAME framework simplifies blockchain development with modular pallets and support libraries for efficient runtime design.

- [**FRAME Overview**](https://docs.polkadot.com/develop/parachains/customize-parachain/overview/)

- [**Add Existing Pallets**](https://docs.polkadot.com/develop/parachains/customize-parachain/add-existing-pallets/)

- [**Create a Custom Pallet**](https://docs.polkadot.com/develop/parachains/customize-parachain/make-custom-pallet/)

- [**Parachain Testing**](https://docs.polkadot.com/develop/parachains/testing/)

- [**Parachain Deployment**](https://docs.polkadot.com/develop/parachains/deployment/)

- [**Parachain Maintenance**](https://docs.polkadot.com/develop/parachains/maintenance/)

## 🧰 Polkadot Toolkit

### 💡 API Libraries

To **interact** with Polkadot SDK based blockchains, you can use the following **API libraries**:

- [**Polkadot API**](https://docs.polkadot.com/develop/toolkit/api-libraries/papi/) - a set of libraries built to be modular, composable, and grounded in a “light-client first” approach. Its primary aim is to equip dApp developers with an extensive toolkit for building fully decentralized application
- [**Polkadot.js**](https://docs.polkadot.com/develop/toolkit/api-libraries/polkadot-js-api/) - a JavaScript library for interacting with Polkadot SDK-based chains. It provides a set of tools for building dApps and interacting with the Polkadot network
- [**Python Substrate Interface**](https://docs.polkadot.com/develop/toolkit/api-libraries/py-substrate-interface/) - a Python library for interacting with Polkadot SDK-based chains
- [**Subxt**](https://docs.polkadot.com/develop/toolkit/api-libraries/subxt/) - a Rust library designed to interact with Polkadot SDK-based blockchains. It provides a type-safe interface for submitting transactions, querying on-chain state, and performing other blockchain interactions
- [**Sidecar REST API**](https://docs.polkadot.com/develop/toolkit/api-libraries/sidecar/) -  a service that provides a REST interface for interacting with Polkadot SDK-based blockchains

### 🔌 Integrations

Polkadot’s ecosystem offers a variety of **integrations** designed to enhance **dApp functionality, improve data management, and bridge the gap between on-chain and off-chain systems**.

- [**Wallets**](https://docs.polkadot.com/develop/toolkit/integrations/wallets/)
- [**Indexers**](https://docs.polkadot.com/develop/toolkit/integrations/indexers/)
- [**Oracles**](https://docs.polkadot.com/develop/toolkit/integrations/oracles/)

### 🛠️ Testing

The Polkadot SDK provides several tools and libraries to facilitate testing at various levels:

- 🧟‍♂️ [**Zombienet**](https://docs.polkadot.com/develop/toolkit/parachains/spawn-chains/zombienet/get-started/) - a robust testing framework designed for Polkadot SDK-based blockchain networks. It enables developers to efficiently deploy and test ephemeral blockchain environments. Check the [Spawn a Basic Chain with Zombienet](https://docs.polkadot.com/tutorials/polkadot-sdk/testing/spawn-basic-chain/) tutorial
- 🥢 [**Chopsticks**](https://docs.polkadot.com/develop/toolkit/parachains/fork-chains/chopsticks/get-started/) - a versatile tool tailored for developers working on Polkadot SDK-based blockchains. With Chopsticks, you can fork live chains locally, replay blocks to analyze extrinsics, and simulate complex scenarios like XCM interactions all without deploying to a live network. Check the [Fork a Chain with Chopsticks](https://docs.polkadot.com/tutorials/polkadot-sdk/testing/fork-live-chains/) tutorial

## 🎓 More Resources

Here are some additional resources that can help you during the hackathon:

- [**Polkadot Open Source Stack**](https://wiki.polkadot.network/build/build-open-source/) 🌟 - a list of open-source tools, libraries, and frameworks that were funded by [Web3 Foundation grants program](https://grants.web3.foundation/) and the Polkadot treasury 
- [**Awesome DOT Repository**](https://github.com/haquefardeen/awesome-dot) 📚 - a list of resources and projects of the Polkadot and Kusama ecosystem
- [**FRAME pallets**](https://github.com/paritytech/polkadot-sdk/tree/master/substrate/frame) 🧱 - a collection of pre-built and well-tested modules that can be easily integrated into your custom parachain
