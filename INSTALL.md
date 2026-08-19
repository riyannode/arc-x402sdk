# Install

These projects are installed or checked out from GitHub. Every command below pins a specific source commit.

## x402-batch-codec — TypeScript batch evidence

```bash
npm install github:riyannode/x402-batch-codec#223adf204bfb77c6fcea515881f785aed2f773ee
```

[Source and usage guide](https://github.com/riyannode/x402-batch-codec)

## x402-batch-codec-py — Python batch evidence utilities

```bash
python -m pip install \
  "x402-batch-codec-py[rpc] @ git+https://github.com/riyannode/x402-batch-codec-py.git@7cfe04b2e81a2fe2bf9bc095bc00b3f831745232"
```

[Source and usage guide](https://github.com/riyannode/x402-batch-codec-py)

## arc-dcw-gateway-kit — Durable Circle DCW + Gateway wallet infrastructure

```bash
git clone https://github.com/riyannode/arc-dcw-gateway-kit.git
cd arc-dcw-gateway-kit
git checkout 3445f730a6a7d5a3365341a967e05aad5e3a33f5
bun install --frozen-lockfile
bun run build
```

[Source and usage guide](https://github.com/riyannode/arc-dcw-gateway-kit)


## x402-header-agent — Circle DCW x402 buyer/seller

```bash
# TypeScript
npm install github:riyannode/x402-header-agent#1d7223ffa3573d974efe22fafc6a99e4991e0d4e

# Native Python
pip install "git+https://github.com/riyannode/x402-header-agent.git@1d7223ffa3573d974efe22fafc6a99e4991e0d4e#subdirectory=python"
```

[Source and usage guide](https://github.com/riyannode/x402-header-agent)

## deepagent-x402-kit — ERC-8004 + Deep Agent

```bash
pip install "git+https://github.com/riyannode/deepagent-x402-kit.git@96944aa9d8ffa8359c1ce1648a57ab411e1d26f1"
```

[Source and usage guide](https://github.com/riyannode/deepagent-x402-kit)
