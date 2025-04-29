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

- [**FRAME pallets**](https://github.com/paritytech/polkadot-sdk/tree/master/substrate/frame)

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
