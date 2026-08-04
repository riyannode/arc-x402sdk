# Arc x402 SDKs

A small home for reusable Arc, Circle Gateway, and x402 primitives. Each SDK remains in its own source repository; this repo only helps builders find and install the right one.

## Pick a primitive

| Need | SDK | Source |
|---|---|---|
| Decode Circle Gateway `submitBatch` transactions and show decoded batch and buyer/seller address participation evidence | `x402-batch-codec` (TypeScript) | [GitHub](https://github.com/riyannode/x402-batch-codec) |
| Decode Circle Gateway `submitBatch` data and work with batch evidence in Python | `x402-batch-codec-py` | [GitHub](https://github.com/riyannode/x402-batch-codec-py) |
| Build an x402 buyer, seller, or dual-role service with Circle DCW | `x402-header-agent` (TypeScript + Python) | [GitHub](https://github.com/riyannode/x402-header-agent) |
| Build a LangChain Deep Agent with ERC-8004 identity and optional x402 tools | `deepagent-x402-kit` (Python) | [GitHub](https://github.com/riyannode/deepagent-x402-kit) |

The Python package provides an independently implemented Python submitBatch decoder and portable batch evidence utilities targeting behavioral parity with the hardened TypeScript v0.2.0 implementation.

## Installation

Use the full commit SHA for reproducible installs. See [INSTALL.md](INSTALL.md).

## Batch evidence limitations

- Timestamp matching is candidate discovery only.
- Buyer/seller delta presence does not prove a unique one-to-one x402 transfer.
- Gateway settlement may use net balance deltas.
- Exact payment amount attribution is not currently provided.
- Portable encoded evidence objects are unsigned metadata, not cryptographic attestations.
- Direct smart-contract verification is not included.
- Circle Gateway provides an official batch-level txHash for each x402 transfer once available. Multiple transfers in the same batch may share the same txHash. This is an off-chain API mapping, not a Solidity-verifiable attestation.

## Scope

- SDK source, API guides, and releases stay in the linked repositories.
- This hub does not contain SDK code, secrets, raw payment headers, signatures, or wallet execution.
- For usage details, follow the README of the selected primitive.

## License

MIT
