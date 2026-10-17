## Legend
- **FRAME pallets**: [native Polkadot SDK components](https://docs.polkadot.com/parachains/customize-runtime/) you compose into a blockchain runtime, defining your logic and custom functionality.
- **Tools & Services**: dev tooling, APIs, indexers, wallets, infra.
- [**Parachains**](https://docs.polkadot.com/polkadot-protocol/parachain-basics/): ready and live chains which you can integrate and/or extend instead of building everything yourself.

## Matrix (Use cases → Pallets / Tools / Parachains)

The following table showcases how different pallets, which may be deployed on different networks in the Polkadot ecosystem, may be used for building your dapp, or for including in your custom protocol.

| Use case | Polkadot SDK building blocks | Tools & services (dev, infra, UX) | Parachains / products (examples) | Notes |
|---|---|---|---|---|
| **Payments & P2P transfers** | `pallet-balances`, `pallet-assets` | Polkadot.js API & Extension, Nova/SubWallet, Subscan/Statescan | **Asset Hub**, **Hydration** (DEX) | Prefer multi‑asset via `pallet-assets` for fungibles; use Asset Hub for canonical issuance + XCM distribution. |
| **Tenders/Grants transparency** | `pallet-assets`, `pallet-collective`, `pallet-treasury`, `pallet-proxy` | Multix, Staking & OpenGov dashboards | **Asset Hub**, **Collectives chain** |  |
| **Supply chain / provenance** | `pallet-nft`, `pallet-assets` |  | **Asset Hub**, **People Chain** |  |
| **Cross‑chain asset routing** | XCM v5 (`pallet-xcm`), `xcm-executor`, `pallet-xtokens` (ORML) | Paraspell SDK, Paraspell API, Paraspell XCM playground, Polkadot.js, PAPI | **Bridge Hub**, **Asset Hub**, **Moonbeam** (XC‑20)| Use buy‑execution/fee payment assets carefully; prefer assets registered on Asset Hub for widespread acceptance. |
| **Ethereum ↔ Polkadot bridging** | `snowbridge-pallet-system`, `snowbridge-pallet-ethereum-client`, `snowbridge-pallet-outbound-queue`, `snowbridge-pallet-inbound-queue` |  [Snowbridge App](https://app.snowbridge.network/) | [Snowbridge](https://docs.snowbridge.network/) (ETH↔Polkadot), **Bridge Hub** |  |
| **Universal interoperability / Multi-chain bridging** | `pallet-ismp` (Interoperable State Machine Protocol) | [Hyperbridge SDK](https://docs.hyperbridge.network/developers/sdk/overview/), cross-chain messaging APIs | [**Hyperbridge**](https://docs.hyperbridge.network/) (universal interoperability hub), **Bridge Hub** | Hyperbridge enables trustless communication between any blockchain networks, not limited to Ethereum-Polkadot |
| **Identity & KYC / credentials** | `pallet-identity`, `pallet-membership`, `pallet-registrar` | [w3n.id web3name directory](https://github.com/KILT-Foundation/w3n.id), off‑chain verifiers | **People chain** (DIDs & verifiable credentials), **KILT** | Keep PII off‑chain; store hashes/attestations on‑chain, present credentials off‑chain when possible. |
| **DAO / Governance (OpenGov)** | `pallet-collective`, `pallet-treasury`, `pallet-conviction-voting`, `pallet-proxy` | Polkassembly, Subsquare, Referenda dashboards | **Collectives**, OpenGov |  |
| **Smart contracts (Rust)** | `pallet-revive` (ink!), weights/benchmarking | ink! toolchain, POP CLI, create-polkadot-app | **Astar** (Wasm), **Phala** (off‑chain compute for contracts), **Aleph Zero** |  |
| **Smart contracts (Solidity)** | pallet-revive | Hardhat/Foundry Polkadot plugins, RPC providers | **AssetHub** (Kusama, Paseo), **Moonbeam**, **Astar** (EVM) |  |
| **NFTs & marketplaces** | `pallet-nft`, `pallet-uniques` (NFTs), `pallet-assets` (fungible), metadata pallets | system.rmrk, IPFS/Crust | **Unique Network**, **Asset Hub** (NFTs), **Astar**/**Moonbeam** (EVM NFTs) | Use `pallet-nft` for native NFTs; RMRK adds composability on compatible chains. |
| **Gaming / Metaverse** | `pallet-uniques`, custom logic pallets, on‑chain randomness (`pallet-randomness`/VRF) | Wallet SDKs, indexers, oracles | **Unique Network**, **Astar**, **Crust** (storage) | Keep heavy assets off‑chain; commit proofs/hashes on‑chain. |
| **Privacy / ZK use cases** | `pallet-mmr` |  | **Phala** (TEE off‑chain compute) | Combine on‑chain verifiers with off‑chain proving for UX. |
| **RWA** | `pallet-assets`, identity/membership pallets, freeze/thaw controls | People Chain, credentials, custodial integrations | **Peaq Network**, **Centrifuge** (RWA) |  |
| **🔒 Off‑chain compute / confidential jobs** | Off‑chain workers, `pallet-acurast` (data attestation), `pallet-acurast-compute` (compute resource management), `pallet-marketplace` (job marketplace) | [Acurast SDK](https://docs.acurast.com/), Phala SDK | **Acurast Network** (decentralized cloud), **Phala Network** | Acurast provides verifiable off-chain compute with TEE attestations; route compute jobs to decentralized processors with staking mechanisms. |
| **Data Oracles / External Data** | `pallet-acurast` (secure data ingestion), `pallet-hyperdrive` (state synchronization), off-chain workers | [Acurast Console](https://docs.acurast.com/), oracle APIs, data feeds | **Acurast Network** (data oracles), **Phala Network** | Use Acurast for tamper-proof external data feeds with processor attestations; hyperdrive pallet enables secure cross-chain data synchronization. |


## Some Ideas to try!

> **Disclaimer:** *Below is merely a suggestion to set you in the right direction, and is not a definitive solution.*

> **More Ideas:** Check out the [Polkadot Builder Party Hackathon Idea List](https://forum.polkadot.network/t/polkadot-builder-party-hackathon-idea-list/14653) for additional project inspiration and community-suggested ideas.

### 🏥 Health Data Consent & E-Prescriptions

- **Core Pallets**: `pallet-identity` (patient verification), `pallet-assets` (prescription tokens with minimal metadata), `pallet-proxy` (delegate access to family/caregivers)
- **Implementation**: **Privacy-first approach** - Deploy on a private/permissioned parachain or solo chain restricted to healthcare network participants. Patient identities are hashed references, not personal data. Prescriptions as transferable tokens contain only essential non-sensitive metadata (prescription ID, expiry). All sensitive medical data stored off-chain with encrypted storage, only access permissions and hashes stored on-chain.
- **Tools**: KILT for verifiable credentials (off-chain presentation), encrypted IPFS or private cloud storage for medical records
- **Chains**: **Private parachain deployment** (hospital network only), **KILT** (credential verification), or **Phala Network** (TEE-based privacy)

### 🎫 Ticketing, Passes & Access Control

- **Core Pallets**: `pallet-nft` (unique tickets with metadata, or VIP tier tickets NFTs),`pallet-collective` (event organizer DAOs)
- **Implementation**: Each ticket as NFT with embedded QR codes and event metadata. VIP tiers represented as special NFTs with different attributes/metadata granting special privileges. Event organizers use collective pallets for multi-signature event management and revenue sharing.
- **Tools**: QR code generation libraries, mobile wallet integration, IPFS for event media
- **Chains**: **Asset Hub** (ticket NFTs), **Unique Network** (advanced NFT features like nested NFTs for combo tickets)
