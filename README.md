# Arc x402 SDKs

A small home for reusable Arc, Circle Gateway, and x402 primitives. Each SDK remains in its own source repository; this repo only helps builders find and install the right one.

## Pick a primitive

| Need | SDK | Source |
|---|---|---|
| Decode Circle Gateway `submitBatch` transactions and show safe buyer/seller proof | `x402-batch-codec` (TypeScript) | [GitHub](https://github.com/riyannode/x402-batch-codec) |
| Same batch proof flow in Python | `x402-batch-codec-py` | [GitHub](https://github.com/riyannode/x402-batch-codec-py) |
| Build an x402 buyer, seller, or dual-role service with Circle DCW | `x402-header-agent` (TypeScript + Python) | [GitHub](https://github.com/riyannode/x402-header-agent) |
| Build a LangChain Deep Agent with ERC-8004 identity and optional x402 tools | `deepagent-x402-kit` (Python) | [GitHub](https://github.com/riyannode/deepagent-x402-kit) |

## Installation

Use the full commit SHA for reproducible installs. See [INSTALL.md](INSTALL.md).

## Scope

- SDK source, API guides, and releases stay in the linked repositories.
- This hub does not contain SDK code, secrets, raw payment headers, signatures, or wallet execution.
- For usage details, follow the README of the selected primitive.

## License

MIT
