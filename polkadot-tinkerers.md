The **Tinkerers Track** is for developers with little or no prior blockchain/Polkadot experience who want to experiment, explore, and build something fun during the hackathon.

> 👉 This track is about **creativity, exploration, and fun** — just tinker and build!  

You can build:  

- 🌉 Cross-chain apps  
- 📊 Data crunching & visualizations  
- 🎨 UX improvements  
- 🧪 Proof of Concepts  
- ✨ Vibe-coded projects  

## 🛠️ Getting Started  

### 🤖 Using AI to Tinker Faster  

You don’t need to know everything — let AI do some heavy lifting:  

- **GitHub Copilot for repos**: Open a repo like [Polkadot SDK](https://github.com/paritytech/polkadot-sdk), and ask Copilot to explain code, functions, or modules. Great for finding answers to “obscure” questions.  

- **Query docs with AI**: Use an AI assistant to query [docs.polkadot.com](https://docs.polkadot.com/) directly — it saves time vs. searching manually.  

### Primary APIs & SDKs  

- [**Polkadot API (PAPI)**](https://papi.how/) — modern TypeScript API for Polkadot.  
- [**DeDot**](https://docs.polkadot.com/develop/toolkit/api-libraries/dedot) — lightweight, reactive TypeScript library for Polkadot SDK chains.
- [**Sidecar**](https://github.com/paritytech/substrate-api-sidecar) — REST service for blockchain data.  
- [**Subxt**](https://github.com/paritytech/subxt) — Rust library to interact Polkadot SDK–based chains.
- [**Paraspell**](https://paraspell.github.io/docs/)  - Library which makes working with XCM and interoperability on Polkadot easy.
- [**create-dot-app**](https://github.com/preschian/create-dot-app) — CLI to scaffold Polkadot dApps with multiple frameworks option and PAPI/DeDot. 

### Data & Indexing  

- [**SubQuery**](https://subquery.network/) — index and query blockchain data.  
- [**DotLake**](https://github.com/paritytech/dotlake-community) — a data ingestion pipeline for Substrate-based blockchains (like Polkadot), view it in action [here](https://data.parity.io).

### Wallets

- [**Talisman Wallet**](https://www.talisman.xyz/)  
- [**SubWallet**](https://subwallet.app/)
- [**Polkadot.js Extension**](https://polkadot.js.org/extension/)
- [**Nova Wallet**](https://novawallet.io/)
- [**Polkadot Vault**](https://vault.novasama.io/)  

### Infrastructure  

- [**Pop! CLI**](https://onpop.io/) — is a developer platform for Polkadot that makes it easy to **build, test, and deploy** smart contracts or appchains with a streamlined CLI.

### UI Helpers  

- [**Polkadot Telemetry**](https://telemetry.polkadot.io/) — real-time visualization of multiple networks.

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

## Hackathon Quickstarters

Whether you're creating web applications, CLI tools, analytics dashboards, or entirely new blockchains, this section aims to provide the essential SDKs, templates, and examples to get you started quickly.

- **TypeScript dApps** - Build web applications with libraries like PAPI and DeDot.
- **Rust Applications** - Create high-performance tools, backends, and custom blockchain runtimes 
- **Data & Analytics** - Access blockchain data through REST APIs and build powerful dashboards
- **Ready-to-use Templates** - Boilerplates and working examples to jumpstart development
- **Quick Start Guides** - Get up and running in minutes with step-by-step instructions

Each section includes documentation links, starter templates, working examples, and notes on when to use each tool. Start with the technology stack that matches your project needs and experience level.


### Building with Typescript (dApps)

**Building decentralized applications (dApps) on Polkadot using TypeScript.** dApps on Polkadot are web applications that interact with parachains and/or a relay chain through client libraries. Each chain has a set of custom modules, called **pallets**, which the library can take advantage of (TODO: add link to pallet matrix).

They typically feature wallet integration, real-time chain data display, and transaction submission.

| SDK | What it's for | When should I use this? | Docs (URL) | Starter / Template (URL) | Working Example(s)  | Tutorial(s)  |
|---|---|---|---|---|---|---|
| **Polkadot-API (PAPI)** | TypeScript library for making dApps or CLI tools | Building web apps with wallet integration and need full type safety | https://papi.how/ | `npx create-dot-app` (choose PAPI) or [Polkadot API TS Boilerplate](https://github.com/polkadot-developers/polkadot-api-ts-boilerplate) | [EduNews (Vue + PAPI)](https://github.com/CrackTheCode016/edunews), [Sample CLI ("You Got Mail!")](https://github.com/polkadot-developers/polkadot-api-example-cli) | [PAPI Account Watcher](https://docs.polkadot.com/tutorials/dapps/remark-tutorial/) |
| **DeDot** | Lightweight TypeScript library for Polkadot chains | Need minimal bundle size and only basic chain interactions | [DeDot Developer Docs](https://docs.dedot.dev/)| `npx create-dot-app` (choose DeDot) | [Working Examples using DeDot](https://docs.dedot.dev/help-and-faq/built-with-dedot) | [Develop ink! dApp using Typink](https://docs.dedot.dev/help-and-faq/tutorials/develop-ink-dapp-using-typink) |
| **ParaSpell (XCM SDK)** | Cross-chain transfer library | Building cross-chain features without complex XCM setup | https://paraspell.github.io/docs/ | *(use within PAPI app / boilerplate)* | *TODO: (none in org yet)* | *TODO: (n/a)* |
| **create-dot-app** | Project scaffolding tool | Quick project setup with modern frameworks and best practices | https://github.com/preschian/create-dot-app | `npx create-dot-app` (choose PAPI/DeDot) | *(n/a)* | *(n/a)* |

### Building with Rust

**Rust is the native language for Polkadot development.** Use Rust to build high-performance applications, CLI tools, backend services, or entirely new blockchain runtimes. Rust offers compile-time safety, zero-cost abstractions, and direct access to Polkadot's native APIs and primitive types.

| SDK | What it's for | When should I use this? | Docs (URL) | Starter / Template (URL) | Working Example(s)  | Tutorial(s)  |
|---|---|---|---|---|---|---|
| **Subxt** | Rust library for Polkadot chains | Building CLI tools, backends, or performance-critical applications | https://docs.rs/subxt/latest/subxt/book | [SubXT Boilerplate](https://github.com/CrackTheCode016/polkadot-subxt-boilerplate) | [EduNews SubXT](https://github.com/CrackTheCode016/edunews-subxt) |  |
| **Polkadot SDK** | Framework for building blockchains | Creating your own blockchain, custom runtime logic, or parachain | https://docs.substrate.io/ | [Parachain Template](https://github.com/paritytech/polkadot-sdk/tree/master/templates/parachain) | [EduChain](https://github.com/w3f/educhain) |  |

### REST / Data / Indexing

**Access blockchain data through REST APIs and build analytics dashboards.** These tools provide alternative ways to interact with Polkadot networks without running full nodes, and enable building data-driven applications with historical analysis capabilities.

| SDK | What it's for | When should I use this? | Docs (URL) | Starter / Template (URL) | Working Example(s)  | Tutorial(s)  |
|---|---|---|---|---|---|---|
| **Sidecar** | REST API for blockchain data | Need HTTP API access or integrating with non-blockchain systems | https://github.com/paritytech/substrate-api-sidecar | `docker compose` from repo | *(none yet — use curl scripts in repo)* | *(Add "try these 3 endpoints")* |
| **DotLake (Community)** | Data analytics platform | Building dashboards and need historical data analysis | https://github.com/paritytech/dotlake-community |`docker compose` from repo| https://data.parity.io/home | *(n/a)* |
| **SubQuery** | Blockchain indexer with GraphQL | Building activity feeds, notifications, or complex data queries | https://academy.subquery.network | [Polkadot SubQuery Starter](https://github.com/subquery/subql-starter/tree/main/Polkadot/Polkadot-starter) | [Running the Polkadot Multi chain Starter Project using SubQuery](https://www.youtube.com/watch?v=as2aUJLMlos)| [Polkadot SubQuery Quickstart](https://subquery.network/doc/indexer/quickstart/quickstart_chains/polkadot.html) |

### Infrastructure / Local chain deployments (optional for Tinkerers)

**Tools for local development and testing environments.** Set up local networks for rapid prototyping, testing parachain features, or developing custom blockchain logic before deploying to testnets or mainnet.

| Tool | What it's for | When should I use this? | Docs (URL) | Starter / Template (URL) | Working Example(s)  | Tutorial(s)  |
|---|---|---|---|---|---|---|
| **Pop! CLI** | Local blockchain development tool | Developing custom parachains or testing parachain features locally | https://onpop.io/ | [Use the pop! CLI to get started](https://github.com/r0gue-io/pop-cli) | [EduChain](https://github.com/w3f/educhain) | [Create a new parachain - pop! Tutorial](https://learn.onpop.io/chains/guides/create-a-new-parachain) |

### Boilerplates & Examples

**Ready-to-use code templates and working examples to jumpstart your development.** These repositories provide battle-tested starting points for different types of Polkadot applications. Clone, modify, and build upon these foundations rather than starting from scratch.

| Boilerplate | Language | Purpose | Repo URL |
|---|---|---|---|
| [Polkadot API TS Boilerplate](https://github.com/CrackTheCode016/polkadot-api-ts-boilerplate) | TypeScript | Base PAPI app (balances/tx wiring scaffold) | https://github.com/CrackTheCode016/polkadot-api-ts-boilerplate |
| [Polkadot API Example CLI](https://github.com/CrackTheCode016/polkadot-api-example-cli) | TypeScript | Sample CLI ("You Got Mail!") using PAPI boilerplate | https://github.com/CrackTheCode016/polkadot-api-example-cli |
| [EduNews (PAPI + Vue)](https://github.com/CrackTheCode016/edunews) | TypeScript | Working web app using PAPI for chain reads | https://github.com/CrackTheCode016/edunews |
| [SubXT Boilerplate](https://github.com/CrackTheCode016/polkadot-subxt-boilerplate) | Rust | Consolidated Subxt client template with signing examples | https://github.com/CrackTheCode016/polkadot-subxt-boilerplate |
| [EduNews SubXT](https://github.com/CrackTheCode016/edunews-subxt) | Rust | Working example using Subxt, using the subxt boilerplate. | https://github.com/CrackTheCode016/edunews-subxt |
| [EduChain (Polkadot SDK)](https://github.com/w3f/educhain) | Rust (SDK) | Example parachain with custom pallets | https://github.com/w3f/educhain |