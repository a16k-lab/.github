![a16k lab banner](./assets/a16k-banner.png)

<div align="center">
  <p>Languages, knowledge systems, developer infrastructure, verifiable archives, and market mechanisms for an open Ethereum ecosystem.</p>
  <p>
    <a href="https://a16k.org">Website</a>
    &nbsp;&middot;&nbsp;
    <a href="https://github.com/a16k-lab">GitHub</a>
    &nbsp;&middot;&nbsp;
    <a href="https://x.com/a16k_lab">X</a>
    &nbsp;&middot;&nbsp;
    <a href="mailto:info@a16k.org">Contact</a>
  </p>
</div>

---

## Building the open Ethereum stack

a16k lab builds focused, open-source systems across the Ethereum development lifecycle. Our work spans contract authoring, protocol knowledge, application connectivity, verifiable data preservation, and market design.

| Surface | Project | What it enables |
|:--|:--|:--|
| **Build** | [JETH](https://github.com/a16k-lab/jeth) | Write EVM smart contracts with a strict TypeScript-shaped syntax. |
| **Explore** | [EPGE](https://github.com/a16k-lab/epge) | Navigate EIPs, ERCs, authors, relationships, and learning paths as interactive graphs. |
| **Connect** | [HANA](https://github.com/a16k-lab/hana) | Build against Ethereum through a hardened abstraction that works across Web3 libraries. |
| **Preserve** | [ARCA](https://github.com/a16k-lab/arca) | Verify and archive Circle attestations and Gateway data on decentralized storage. |
| **Price risk** | [Spry](https://github.com/SpryFinance) | Set Uniswap V4 swap fees dynamically from trade-level and block-level price movement. |

## Projects

### 01 / JETH

> A smart-contract language with strict TypeScript-shaped syntax and Solidity-compatible EVM semantics.

[JETH](https://github.com/a16k-lab/jeth) gives Ethereum developers a familiar, disciplined language surface without departing from the EVM execution model. Its compiler lowers JETH source through a typed intermediate representation and Yul, then uses `solc` to produce deployable artifacts.

```text
JETH source -> typed IR -> Yul -> solc -> ABI metadata + EVM bytecode
```

**Designed for:**

- Strict, predictable TypeScript-shaped contract syntax
- Solidity-compatible EVM semantics
- Typed intermediate representation for inspectable compilation
- Yul output for the established Solidity toolchain
- ABI metadata and deployable EVM bytecode

[Explore JETH](https://github.com/a16k-lab/jeth)

### 02 / EPGE

> An interactive graph explorer for Ethereum Improvement Proposals.

[EPGE](https://github.com/a16k-lab/epge) turns EIPs and ERCs into a navigable knowledge system. Instead of treating standards as isolated documents, it exposes the connections between proposals, authors, dependencies, and learning sequences.

| Graph | Purpose |
|:--|:--|
| **Proposals Graph** | Explore relationships across EIPs and ERCs. |
| **Authors Graph** | Follow contributors and the proposals they shape. |
| **Learn Graph** | Move through Ethereum standards as a structured learning tree. |

Every graph supports search and filters. EPGE also includes a specification reader and a question interface for investigating the material in context.

[Explore EPGE](https://github.com/a16k-lab/epge)

### 03 / HANA

> A hardened, adapter-agnostic network abstraction for effortless Ethereum development.

[HANA](https://github.com/a16k-lab/hana) sits above the Web3 library you already use. It provides one dependable application-facing layer while keeping the underlying provider or client replaceable.

```text
Application -> HANA -> adapter -> preferred Web3 library -> Ethereum
```

**Core capabilities:**

- Adapter-agnostic integration across Web3 libraries
- Built-in caching for efficient repeated reads
- Type-safe contract APIs
- Easy-to-use testing mocks
- A hardened boundary between application code and network dependencies

[Explore HANA](https://github.com/a16k-lab/hana)

### 04 / ARCA

> Verifiable, decentralized archival infrastructure for Circle CCTP attestations and Circle Gateway.

[ARCA](https://github.com/a16k-lab/arca) is an open-source, self-hostable system that continuously mirrors Circle data, verifies each item cryptographically before archiving it, and preserves the verified result across IPFS and Arweave.

```text
Circle CCTP + Gateway -> cryptographic verification -> IPFS + Arweave
                                                    -> Iris API-compatible endpoint
                                                    -> fallback client library
```

ARCA serves archived data through an Iris API-compatible endpoint and includes a fallback client library, allowing applications to remain resilient when their primary data path is unavailable.

[Explore ARCA](https://github.com/a16k-lab/arca)

### 05 / Spry

> A Uniswap V4 hook that prices each swap according to the movement it creates.

[Spry](https://github.com/SpryFinance) is a small contract consulted by Uniswap V4's singleton `PoolManager` on every swap. Instead of applying one flat fee, a Spry pool adjusts the fee using:

- How much the current trade moves the price
- How much the entire block has already moved the price

```text
swap -> trade movement + block movement -> dynamic fee -> V4 fee channel -> LPs
```

This lets ordinary trades remain close to a low base rate while larger, arbitrage-sized, or MEV-sized swaps pay more in proportion to the price movement they create.

Spry Finance is maintained as a separate organization at [github.com/SpryFinance](https://github.com/SpryFinance), but it is built by a16k lab.

[Spry Finance](https://spry.fi) &nbsp;&middot;&nbsp; [Contracts](https://github.com/SpryFinance/spry-contracts) &nbsp;&middot;&nbsp; [Interface](https://github.com/SpryFinance/spry-interface) &nbsp;&middot;&nbsp; [Subgraph](https://github.com/SpryFinance/spry-subgraph)

## How the work connects

Each project owns a distinct layer, but they share a common direction: make Ethereum easier to build on, easier to understand, and more resilient.

```text
Author contracts      JETH      Language and compiler
Understand standards  EPGE      Protocol knowledge graph
Connect applications  HANA      Network and contract abstraction
Preserve evidence     ARCA      Verified decentralized archives
Price market impact   Spry      Dynamic Uniswap V4 fees
```

## Engineering principles

Across the lab, we optimize for:

- **Open infrastructure:** public systems that can be inspected, extended, and self-hosted where applicable.
- **Ethereum compatibility:** tools that work with established semantics, standards, and execution paths.
- **Verifiable behavior:** typed pipelines, cryptographic checks, and explicit system boundaries.
- **Composable architecture:** focused components that integrate without forcing a single vendor or library.
- **Practical developer experience:** strong types, useful defaults, clear APIs, and testing support.

## Repository guide

| Repository | Primary focus |
|:--|:--|
| [`a16k-lab/jeth`](https://github.com/a16k-lab/jeth) | Smart-contract language, compiler pipeline, ABI metadata, and EVM output |
| [`a16k-lab/epge`](https://github.com/a16k-lab/epge) | EIP and ERC graph exploration, specification reading, search, and learning |
| [`a16k-lab/hana`](https://github.com/a16k-lab/hana) | Adapter-agnostic Ethereum networking, caching, typed contracts, and mocks |
| [`a16k-lab/arca`](https://github.com/a16k-lab/arca) | Circle data verification, decentralized archival, API compatibility, and fallback access |
| [`SpryFinance`](https://github.com/SpryFinance) | Dynamic-fee Uniswap V4 contracts, interface, subgraph, and research |

## Contributing

Contributions that improve correctness, interoperability, documentation, testing, and developer experience are welcome.

1. Choose the project closest to the problem you want to solve.
2. Read that repository's documentation and contribution guidance.
3. Open a focused issue before beginning a large or architectural change.
4. Keep pull requests narrow, tested, and explicit about tradeoffs.
5. Include documentation when behavior or public APIs change.

Project repositories are the source of truth for setup instructions, maturity, supported environments, deployment details, and licenses.

## Security

Please do not disclose vulnerabilities in a public issue. Use the security guidance in the relevant repository when available, or contact [info@a16k.org](mailto:info@a16k.org) with a clear description and reproduction details.

## Connect

- Website: [a16k.org](https://a16k.org)
- GitHub: [github.com/a16k-lab](https://github.com/a16k-lab)
- X: [@a16k_lab](https://x.com/a16k_lab)
- Email: [info@a16k.org](mailto:info@a16k.org)

---

<div align="center">
  <img src="./assets/a16k-logo-256.png" width="64" alt="a16k lab" />
  <p><strong>Built in the open for Ethereum.</strong></p>
</div>
