# Arc x402 SDKs

A small home for reusable Arc, Circle Gateway, and x402 primitives. Each SDK remains in its own source repository; this repo only helps builders find and install the right one.

## Gateway batch terminology

Circle Gateway exposes both a REST batching API and an onchain batch settlement function:

* `POST /v1/batch/submit` submits an individual EIP-3009 authorization to Circle Gateway for batching.
* `GatewayWallet.submitBatch(bytes,bytes)` is the onchain transaction used to settle a batch.

The `x402-batch-codec` packages decode and validate the onchain `GatewayWallet.submitBatch(bytes,bytes)` transaction. They do not decode the REST `/v1/batch/submit` request.

## Pick a primitive

| Need | SDK | Source |
|---|---|---|
| Decode onchain `GatewayWallet.submitBatch(bytes,bytes)` settlement data and address participation evidence | `x402-batch-codec` (TypeScript) | [GitHub](https://github.com/riyannode/x402-batch-codec) |
| Python implementation of the batch decoder and evidence utilities | `x402-batch-codec-py` | [GitHub](https://github.com/riyannode/x402-batch-codec-py) |
| Build an x402 buyer, seller, or dual-role service with Circle DCW | `x402-header-agent` (TypeScript + Python) | [GitHub](https://github.com/riyannode/x402-header-agent) |
| Build a LangChain Deep Agent with ERC-8004 identity and optional x402 tools | `deepagent-x402-kit` (Python) | [GitHub](https://github.com/riyannode/deepagent-x402-kit) |
| Build durable per-user Circle DCW + Gateway wallet infrastructure with resumable deposits, withdrawals, and recovery | `arc-dcw-gateway-kit` (TypeScript) | [GitHub](https://github.com/riyannode/arc-dcw-gateway-kit) |

`x402-batch-codec-py` provides an independently implemented Python batch decoder and portable evidence utilities targeting behavioral parity with the TypeScript codec.

## Installation

Use the full commit SHA for reproducible installs. See [INSTALL.md](INSTALL.md).

## Batch evidence limitations

* Circle x402 transfer responses include an EIP-3009 `nonce` and a nullable batch-level `txHash`.
* `txHash` remains `null` until the transfer is included in a batch with a settlement transaction hash.
* Multiple x402 transfers included in the same batch may share the same `txHash`.
* The Circle transfer-to-`txHash` mapping comes from an off-chain HTTP API and is not a signed Circle attestation.
* The SDK validates the referenced Arc transaction, receipt, GatewayWallet target, and batch calldata off-chain through RPC, but does not provide a Solidity/onchain verifier contract.
* Gateway batch settlement may use net signed balance deltas. Buyer/seller address participation does not prove a unique one-to-one x402 transfer.
* Exact payment amount attribution cannot be derived from net batch deltas alone.
* Timestamp-based explorer matching is legacy heuristic candidate discovery only and is not an official Circle mapping.
* Portable encoded evidence objects are unsigned metadata, not cryptographic attestations.

## Scope

- SDK source, API guides, and releases stay in the linked repositories.
- This hub does not contain SDK code, secrets, raw payment headers, signatures, or wallet execution.
- For usage details, follow the README of the selected primitive.

## License

MIT
