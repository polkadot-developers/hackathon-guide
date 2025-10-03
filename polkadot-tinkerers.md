The **Tinkerers Track** is for developers with little or no prior blockchain/Polkadot experience who want to experiment, explore, and build something fun during the hackathon.

> 👉 This track is about **creativity, exploration, and fun** — just tinker and build!  

You can build:  

- 🌉 Cross-chain apps  
- 📊 Data crunching & visualizations  
- 🎨 UX improvements  
- 🧪 Proof of Concepts  
- ✨ Vibe-coded projects  

> For more on the specifics of Polkadot, visit the official [Polkadot Documentation](https://docs.polkadot.com/polkadot-protocol/).

## 🛠️ Getting Started  

## Quick Primer: What is Polkadot?

> If you're already famililar with Polkadot, feel free to skip to the [solutions matrix](#polkadot-solutionstooling-matrix) or [APIs and SDKs](#primary-apis--sdks).

Polkadot is designed to enable scalable, secure, and interoperable networks to thrive, reflecting the following principles:

1. **Less trust, more truth** — Enable self-verification instead of trusting intermediaries
2. **Many chains, not one** — Specialized blockchains working together beats a single chain trying to do everything
3. **Evolution over perfection** — Systems must adapt as technology advances, which Polkadot embraces with its modular forkless upgrades

**The Architecture at a glance:**

- **Relay Chain**: Main hub providing shared security and cross-chain messaging
- **Parachains**: Specialized blockchains for different use cases (IoT, identity, healthcare etc.)
- **XCM**: Cross-chain messaging that lets parachains talk to each other

**For Tinkerers:** Build apps that work across multiple blockchains, access rich data from dozens of live chains, and experiment with smart contracts, custom blockchains, or both!

### Primary APIs & SDKs  

- [Polkadot API (PAPI)](https://papi.how/) — modern TypeScript API for Polkadot.  
- *DeDot](https://docs.polkadot.com/develop/toolkit/api-libraries/dedot) — lightweight, reactive TypeScript library for Polkadot SDK chains.
- [Sidecar](https://github.com/paritytech/substrate-api-sidecar) — REST service for blockchain data.  
- [Subxt](https://github.com/paritytech/subxt) — Rust library to interact Polkadot SDK–based chains.
- [Paraspell](https://paraspell.github.io/docs/)  - Library which makes working with XCM and interoperability on Polkadot easy.
- [create-dot-app](https://github.com/preschian/create-dot-app) — CLI to scaffold Polkadot dApps with multiple frameworks option and PAPI/DeDot. 

### Polkadot Solutions/Tooling Matrix

Have an idea in mind? Cross-chain tool, a voting system or a verification solution? Check out our [solution matrix](./tinkerer-materials/solution-matrix.md) to find which tools/modules are available for your case!

### Hackathon Quickstarters

Want a quickstart to your project? Look no further than our [hackathon quickstarter guide](./tinkerer-materials/quickstarters.md), where you will find templates, tutorials, and documentation for the above SDKs.

### Data & Indexing  

- [SubQuery](https://subquery.network/) — index and query blockchain data.  
- [DotLake](https://github.com/paritytech/dotlake-community) — a data ingestion pipeline for Substrate-based blockchains (like Polkadot), view it in action [here](https://data.parity.io).

### Wallets

- [Talisman Wallet](https://www.talisman.xyz/)  
- [SubWallet](https://subwallet.app/)
- [Polkadot.js Extension](https://polkadot.js.org/extension/)
- [Nova Wallet](https://novawallet.io/)
- [Polkadot Vault](https://vault.novasama.io/)  

### Infrastructure  

- [**Pop! CLI**](https://onpop.io/) — is a developer platform for Polkadot that makes it easy to **build, test, and deploy** smart contracts or appchains with a streamlined CLI.

### UI Helpers  

- [**Polkadot Telemetry**](https://telemetry.polkadot.io/) — real-time visualization of multiple networks.

### 🤖 Using AI for Efficient Tinkering  

You don’t need to know everything — let AI do some heavy lifting:  

- **GitHub Copilot for repos**: Open a repo like [Polkadot SDK](https://github.com/paritytech/polkadot-sdk), and ask Copilot to explain code, functions, or modules. Great for finding answers to “obscure” questions.  

- **Query docs with AI**: Use an AI assistant to query [docs.polkadot.com](https://docs.polkadot.com/) directly — it saves time vs. searching manually.  


## 🎥 Video Resources

**Polkadot Deep Dives** is a playlist of in-depth explorations into different FRAME pallets. These videos are brought to you by Parity’s Delivery Services team, where they dive deep into all things Polkadot development and ecosystem.

- [Polkadot Developer Playlist: Deep Dives into FRAME Pallets, XCM, and Governance](https://www.youtube.com/playlist?list=PLOyWqupZ-WGsfnlpkk0KWX3uS4yg6ZztG)

## 💻 Tinkering with Replit  

If you’re new to coding, or just want to get a proof of concept running fast, [**Replit**](https://replit.com/) is a great place to tinker with creating applications on Polkadot. You don’t need to install anything locally: just open your browser, prompt replit (or use a template), and start experimenting.  

You can use Replit to:  
- Prototype UIs (React, Vue, or plain JS/HTML).  
- Experiment with Polkadot APIs like **PAPI**, **DeDot**, or other libraries / tools that are mentioned.
- Fetch and visualize on-chain data without worrying about setup.  

 Replit has built-in **AI prompting**. You can paste in code snippets or ask it to use libraries like **PAPI**, **DeDot**, **Subxt**, **SubQuery**, or **Sidecar** directly in your project. This makes it much easier to get started, even if you don’t know the exact function calls.  

👉 In other words: Replit is your **sandbox for Polkadot tinkering** — experiment quickly, share instantly, and learn by doing.    

## 🚀 Approaches for Tinkerers  

- **Start with APIs** — fetch balances, transfers, staking info, and display them in a presentable way.
- **Visualize data** — build dashboards, graphs, creative art from chain telemetry and data.
- **Improve UX** — prototype wallet flows, simplify onboarding, or provide unique recovery methods for wallets.  
- **Hack with vibes** — memes, mashups, or unique experiments welcome!  
- **Spin up an appchain** — use Tanssi to launch a chain tied to your own app.  

## 🌐 Deployed Examples

This section highlights **working examples** you can fork, get inspiration from, build on right away. Each entry links to a repo and (where available) a quick summary/tutorial to help you get started fast.  

- [**EduChain**](https://github.com/w3f/educhain) — An example parachain developed by the TechEd team at W3F for education and credentialing, showing how the Polkadot SDK can power real-world solutions.

- [**create-polkadot-dapp**](https://github.com/paritytech/create-polkadot-dapp) — A starter template for quickly scaffolding Polkadot dApps with minimal setup.