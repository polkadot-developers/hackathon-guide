## Hackathon Quickstarters

Whether you're creating web applications, CLI tools, analytics dashboards, or entirely new blockchains, this section aims to provide the essential SDKs, templates, and examples to get you started quickly.

- **TypeScript dApps** - Build web applications with libraries like [PAPI](#building-with-typescript-dapps) and [DeDot](#building-with-typescript-dapps).
- **Rust Applications** - Create high-performance tools and backends with [`subxt`](#building-with-rust)
- **Create your protocol** - Create quality blockchains (either standlone or parachains) using the [`polkadot-sdk`](#building-with-rust)
- **Data & Analytics** - Access blockchain data through REST APIs like [Substrate Sidecar](#rest--data--indexing) and build powerful dashboards with tools like [Dotlake](#rest--data--indexing).
- **Ready-to-use Templates** - [Boilerplates](#boilerplates--examples) and working examples to jumpstart development for the above!

Each section includes documentation links, starter templates, working examples, and notes on when to use each tool. Start with the technology stack that matches your project needs and experience level.


### Building with Typescript (dApps)

**Building decentralized applications (dApps) on Polkadot using TypeScript.** dApps on Polkadot are web applications that interact with parachains and/or a relay chain through client libraries. Each chain has a set of custom modules, called **pallets**, each of which has prebuilt functionality you can take advantage of. For more information on what pallets you can use and for what, feel free to [visit the solutions matrix.](./solution-matrix.md)

They typically feature wallet integration, real-time chain data display, and transaction submission.

| SDK | What it's for | When should I use this? | Docs (URL) | Starter / Template (URL) | Working Example(s)  | Tutorial(s)  |
|---|---|---|---|---|---|---|
| **Polkadot-API (PAPI)** | TypeScript library for making dApps or CLI tools | Building web apps with wallet integration and need full type safety | https://papi.how/ | `npx create-dot-app` (choose PAPI) or [Polkadot API TS Boilerplate](https://github.com/polkadot-developers/polkadot-api-ts-boilerplate) | [EduNews (Vue + PAPI)](https://github.com/CrackTheCode016/edunews), [Sample CLI ("You Got Mail!")](https://github.com/polkadot-developers/polkadot-api-example-cli) | [PAPI Account Watcher](https://docs.polkadot.com/tutorials/dapps/remark-tutorial/) |
| **DeDot** | Lightweight TypeScript library for Polkadot chains | Need minimal bundle size and only basic chain interactions | [DeDot Developer Docs](https://docs.dedot.dev/)| `npx create-dot-app` (choose DeDot) | [Working Examples using DeDot](https://docs.dedot.dev/help-and-faq/built-with-dedot) | [Develop ink! dApp using Typink](https://docs.dedot.dev/help-and-faq/tutorials/develop-ink-dapp-using-typink) |
| **Polkadot UI (beta)** | React component library for Polkadot dApps | Building polished UIs with pre-built wallet integration and chain components | https://polkadot-ui.com/docs | `npx polkadot-ui@latest list` |  | [Getting Started Guide](https://polkadot-ui.com/docs/getting-started) |
| **ParaSpell (XCM SDK)** | Cross-chain transfer library | Building cross-chain features without complex XCM setup | https://paraspell.github.io/docs/ | *(use within PAPI app / boilerplate)* |  |  |
| **create-dot-app** | Project scaffolding tool | Quick project setup with modern frameworks and best practices | https://github.com/preschian/create-dot-app | `npx create-dot-app` (choose PAPI/DeDot) | *(n/a)* | *(n/a)* |

### Building with Rust

**Rust is the native language for Polkadot development.** Use Rust to build high-performance applications, CLI tools, backend services, or entirely new blockchain runtimes. Rust offers compile-time safety, zero-cost abstractions, and direct access to Polkadot's native APIs and primitive types.

| SDK | What it's for | When should I use this? | Docs (URL) | Starter / Template (URL) | Working Example(s)  | Tutorial(s)  |
|---|---|---|---|---|---|---|
| **Subxt** | Rust library for Polkadot chains | Building CLI tools, backends, or performance-critical applications | https://docs.rs/subxt/latest/subxt/book | [SubXT Boilerplate](https://github.com/CrackTheCode016/polkadot-subxt-boilerplate) | [EduNews SubXT](https://github.com/CrackTheCode016/edunews-subxt) |  |
| **Polkadot SDK** | Framework for building blockchains | Creating your own blockchain, custom runtime logic, or parachain | https://docs.polkadot.com/ | [Parachain Template](https://github.com/paritytech/polkadot-sdk/tree/master/templates/parachain) | [EduChain](https://github.com/w3f/educhain) |  |

### REST / Data / Indexing

**Access blockchain data through REST APIs and build analytics dashboards.** These tools provide alternative ways to interact with Polkadot networks without running full nodes, and enable building data-driven applications with historical analysis capabilities.

| SDK | What it's for | When should I use this? | Docs (URL) | Starter / Template (URL) | Working Example(s)  | Tutorial(s)  |
|---|---|---|---|---|---|---|
| **Sidecar** | REST API for blockchain data | Need HTTP API access or integrating with non-blockchain systems | https://github.com/paritytech/substrate-api-sidecar | `docker compose` from repo | Use any starter, like Next.js, and make REST calls | [Sidecar Block Explorer Example ](https://github.com/w3f/sidecar-example) |
| **DotLake (Community)** | Data analytics platform | Building dashboards and need historical data analysis | https://github.com/paritytech/dotlake-community |`docker compose` from repo| https://data.parity.io | *(n/a)* |
| **SubQuery** | Blockchain indexer with GraphQL | Building activity feeds, notifications, or complex data queries | https://academy.subquery.network | use the [SubQuery starter project](https://github.com/polkadot-developers/subquery-starter-example), or use the `npx @subql/cli init test --networkFamily Polkadot` command to bootstrap a project | [Running the Polkadot Multi chain Starter Project using SubQuery](https://www.youtube.com/watch?v=as2aUJLMlos)| [Polkadot SubQuery Quickstart](https://subquery.network/doc/indexer/quickstart/quickstart_chains/polkadot.html) |

### Infrastructure / Local chain deployments

**Tools for local development and testing environments.** Set up local networks for rapid prototyping, testing parachain features, or developing custom blockchain logic before deploying to testnets or mainnet.

| Tool | What it's for | When should I use this? | Docs (URL) | Starter / Template (URL) | Working Example(s)  | Tutorial(s)  |
|---|---|---|---|---|---|---|
| **Pop! CLI** | Local blockchain development tool | Developing custom parachains or testing parachain features locally | https://onpop.io/ | [Use the pop! CLI to get started](https://github.com/r0gue-io/pop-cli) | [EduChain](https://github.com/w3f/educhain) | [Create a new parachain - pop! Tutorial](https://learn.onpop.io/chains/guides/create-a-new-parachain) |

### Boilerplates & Examples

**Ready-to-use code templates and working examples to jumpstart your development.** These repositories provide battle-tested starting points for different types of Polkadot applications. Clone, modify, and build upon these foundations rather than starting from scratch.

#### Templates

| Resource | Language | Purpose | Repo URL |
|---|---|---|---|
| [Polkadot API TS Boilerplate](https://github.com/CrackTheCode016/polkadot-api-ts-boilerplate) | TypeScript | Base PAPI Typescript repo | https://github.com/CrackTheCode016/polkadot-api-ts-boilerplate |
| [SubXT Template](https://github.com/CrackTheCode016/polkadot-subxt-boilerplate) | Rust | Consolidated Subxt client template with signing examples | https://github.com/CrackTheCode016/polkadot-subxt-boilerplate |

#### Examples

| Resource | Language | Purpose | Repo URL |
|---|---|---|---|
| [Polkadot API Example CLI](https://github.com/CrackTheCode016/polkadot-api-example-cli) | TypeScript | Sample CLI ("You Got Mail!") using PAPI boilerplate | https://github.com/CrackTheCode016/polkadot-api-example-cli |
| [EduNews (PAPI + Vue)](https://github.com/CrackTheCode016/edunews) | TypeScript | Working web app using PAPI for chain reads | https://github.com/CrackTheCode016/edunews |
| [EduNews SubXT](https://github.com/CrackTheCode016/edunews-subxt) | Rust | Working example using Subxt, using the subxt boilerplate. | https://github.com/CrackTheCode016/edunews-subxt |
| [EduChain (Polkadot SDK)](https://github.com/w3f/educhain) | Rust (SDK) | Example parachain with custom pallets | https://github.com/w3f/educhain |
