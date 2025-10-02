## Legend
- **FRAME pallets / SDK**: native Substrate modules or Polkadot SDK components you compose into a blockchain runtime (logic).
- **Tools & services**: dev tooling, APIs, indexers, wallets, infra.
- **Parachains / services**: ready and live chains which you can integrate and/or extend instead of building everything yourself.

---

## Matrix (Use cases → Pallets / Tools / Parachains)

| Use case | Polkadot SDK building blocks | Tools & services (dev, infra, UX) | Parachains / products (examples) | Notes |
|---|---|---|---|---|
| **Payments & P2P transfers** | `pallet-balances`, `pallet-assets`, `pallet-transaction-payment`, `pallet-vesting` | Polkadot.js API & Extension, Nova/SubWallet, Subscan/Statescan | **Asset Hub**, **Bifrost** (liquid staking tokens), **Hydration** (DEX) | Prefer multi‑asset via `pallet-assets` for fungibles; use Asset Hub for canonical issuance + XCM distribution. |
| **Tenders/Grants transparency** | `pallet-assets`, `pallet-collective`, `pallet-treasury`, `pallet-vesting`, `pallet-proxy` | Multix, OpenGov dashboards | **Asset Hub**, **Collectives chain** |  |
| **Supply chain / provenance** | `pallet-nft`, `pallet-assets`, `pallet-timestamp` |  | **Asset Hub**, **People Chain** |  |
| **Cross‑chain asset routing** | XCM v5 (`pallet-xcm`), `xcm-executor`, `pallet-xtokens` (ORML) | Paraspell SDK, Paraspell API, Paraspell XCM playground, Polkadot.js, PAPI | **Bridge Hub**, **Asset Hub**, **Moonbeam** (XC‑20), **Bifrost** | Use buy‑execution/fee payment assets carefully; prefer assets registered on Asset Hub for widespread acceptance. |
| **Ethereum ↔ Polkadot bridging** |  |  | **Snowbridge** (ETH↔Polkadot), **Bridge Hub** |  |
| **Identity & KYC / credentials** | `pallet-identity`, `pallet-membership`, `pallet-registrar` | https://w3n.id/, off‑chain verifiers | **People chain** (DIDs & verifiable credentials), **KILT** | Keep PII off‑chain; store hashes/attestations on‑chain, present credentials off‑chain when possible. |
| **DAO / Governance (OpenGov)** | `pallet-democracy`/OpenGov tracks, `pallet-collective`, `pallet-treasury`, `pallet-conviction-voting`, `pallet-proxy` | Polkassembly, Subsquare, Referenda dashboards | **Collectives**, OpenGov |  |
| **Smart contracts (Rust)** | `pallet-revive` (ink!), `pallet-scheduler`, weights/benchmarking | ink! toolchain, POP CLI, create-polkadot-app | **Astar** (Wasm), **Phala** (off‑chain compute for contracts), **Aleph Zero** |  |
| **Smart contracts (Solidity)** | pallet-revive | Hardhat/Foundry Polkadot plugins, RPC providers | **AssetHub** (Kusama, Paseo), **Moonbeam**, **Astar** (EVM) |  |
| **NFTs & marketplaces** | `pallet-nft`, `pallet-uniques` (NFTs), `pallet-assets` (fungible), metadata pallets | system.rmrk, IPFS/Crust | **Unique Network**, **Asset Hub** (NFTs), **Astar**/**Moonbeam** (EVM NFTs) | Use `pallet-nft` for native NFTs; RMRK adds composability on compatible chains. |
| **Gaming / Metaverse** | `pallet-uniques`, custom logic pallets, on‑chain randomness (`pallet-randomness`/VRF) | Wallet SDKs, indexers, oracles | **Unique Network**, **Astar**, **Crust** (storage) | Keep heavy assets off‑chain; commit proofs/hashes on‑chain. |
| **Privacy / ZK use cases** | `pallet-mmr` |  | **Manta Network** (privacy & zk apps), **Phala** (TEE off‑chain compute) | Combine on‑chain verifiers with off‑chain proving for UX. |
| **RWA** | `pallet-assets`, identity/membership pallets, freeze/thaw controls | People Chain, credentials, custodial integrations | **Peaq Network**, **Centrifuge** (RWA), **Pendulum** (forex rails) |  |
| **🔒 Off‑chain compute / confidential jobs** | Off‑chain workers, `pallet-scheduler` | Phala SDK | **Phala Network** | Route sensitive workloads to TEEs; commit results on‑chain. |


## Some Ideas to try!
- Health data consent and e‑prescriptions
- Ticketing, passes and access control 
- Programmable B2B invocing

## Some Ideas to try!
- Health data consent and e‑prescriptions
- Ticketing, passes and access control 
- Programmable B2B invocing

