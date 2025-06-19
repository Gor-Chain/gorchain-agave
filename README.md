# GorChain - Gorbagana ($GOR)

**A high-performance Solana fork optimized for the Gorbagana ecosystem with $GOR as the native gas token.**

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)](https://github.com/gorbagana/gorchain)
[![Version](https://img.shields.io/badge/version-v3.0.0-blue.svg)](https://github.com/gorbagana/gorchain/releases)

---

## Overview

GorChain is a specialized blockchain fork of Solana Agave, designed specifically for the Gorbagana ecosystem. It features $GOR as the native gas token, providing a cost-effective and efficient platform for decentralized applications.

### Key Features

- **High Performance**: Built on Solana's proven architecture
- **$GOR Native Token**: Optimized gas economics with GOR token
- **Developer Friendly**: Full Solana tooling compatibility
- **Production Ready**: Battle-tested codebase with GorChain optimizations
- **Low Fees**: Reduced transaction costs compared to mainnet
- **Secure**: Inherits Solana's security model with custom enhancements

---

## Token Information

| Network | Token Address | Symbol |
|---------|---------------|--------|
| **Solana Mainnet** | `h2h3tNnocBwoEd8SGgzZxHuKYkXQE7TFbSoygkUpump` | $GOR |
| **GorChain** | `kLGKcrKaSHyiHTs2XnBZz4ejoVw6Cg77F4TQ2D8HuFa` | $GOR (Native) |

---

## Architecture

GorChain maintains full compatibility with the Solana ecosystem while introducing key modifications:

### Core Modifications

- **Native Token**: $GOR replaces SOL as the native gas token
- **Token Display**: All CLI tools and interfaces display GOR instead of SOL
- **Genesis Configuration**: Custom genesis with GOR token parameters
- **Runtime Optimizations**: Enhanced for Gorbagana use cases

### Technical Specifications

| Specification | Value |
|---------------|-------|
| **Native Token** | $GOR |
| **Decimals** | 9 |
| **Block Time** | ~400ms |
| **TPS** | 65,000+ |
| **Consensus** | Proof of History + Proof of Stake |
| **RPC Endpoint** | `https://rpc.gorchain.xyz` |

---

## Quick Start

### Prerequisites

- Rust 1.75.0+
- Node.js 18+
- Git

### Building from Source

```bash
# Clone the repository
git clone https://github.com/gorbagana/gorchain.git
cd gorchain

# Build the validator
cd gorchain-agave
cargo build --release

# Run tests
cargo test
```

### Running a Validator

```bash
# Start the validator
./target/release/solana-validator \
  --identity validator-keypair.json \
  --vote-account vote-keypair.json \
  --ledger ledger/ \
  --rpc-port 8899 \
  --entrypoint entrypoint.gorchain.xyz:8001 \
  --expected-genesis-hash <genesis-hash> \
  --wal-recovery-mode skip_any_corrupted_record \
  --limit-ledger-size
```

### CLI Usage

The GorChain CLI is fully compatible with Solana CLI commands, but displays amounts in GOR:

```bash
# Check balance (displays in GOR)
./target/release/solana balance

# Transfer GOR tokens
./target/release/solana transfer <recipient> <amount>

# Create account
./target/release/solana create-account

# Deploy program
./target/release/solana program deploy <program.so>
```

---

## Network Information

### Mainnet
- **RPC Endpoint**: `https://rpc.gorchain.xyz`
- **WebSocket**: `wss://rpc.gorchain.xyz`
- **Explorer**: `https://explorer.gorchain.xyz`

### Testnet
- **RPC Endpoint**: `https://testnet-rpc.gorchain.xyz`
- **WebSocket**: `wss://testnet-rpc.gorchain.xyz`
- **Faucet**: `https://faucet.gorchain.xyz`

---

## Modified Components

This fork includes modifications to the following Solana components:

### Core Runtime
- `gorchain-agave/runtime/` - Modified to use GOR as native token
- `gorchain-agave/gorchain-native-token/` - GOR token implementation
- `gorchain-agave/gorchain-sdk-ids/` - Custom SDK identifiers

### CLI Tools
- `gorchain-agave/cli/` - Updated to display GOR instead of SOL
- `gorchain-agave/cli-output/` - Modified output formatting
- `gorchain-agave/tokens/` - Token display logic

### Key Files Modified
- `runtime/src/bank.rs` - Core banking logic with GOR support
- `runtime/src/genesis_utils.rs` - Genesis configuration
- `runtime/src/static_ids.rs` - Static identifier definitions
- `cli/src/cli.rs` - Command-line interface
- `cli-output/src/display.rs` - Output display formatting

---

## Development

### Project Structure

```
gorchain/
├── gorchain-agave/              # Modified Solana Agave codebase
│   ├── runtime/                 # Core runtime with GOR modifications
│   ├── cli/                     # Command-line tools
│   ├── gorchain-native-token/   # GOR token implementation
│   └── gorchain-sdk-ids/        # Custom SDK identifiers
├── README.md                    # This file
└── GORCHAIN_DEPLOYMENT_GUIDE.md # Deployment documentation
```

### Building Components

```bash
# Build specific components
cargo build --release --bin solana-validator
cargo build --release --bin solana
cargo build --release --bin solana-keygen

# Build all binaries
cargo build --release
```

### Testing

```bash
# Run all tests
cargo test

# Run specific test suite
cargo test --package solana-runtime
cargo test --package solana-cli
```

---

## Contributing

We welcome contributions to GorChain! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Workflow

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Ensure all tests pass
6. Submit a pull request

### Code Style

- Follow Rust standard formatting (`cargo fmt`)
- Ensure clippy passes (`cargo clippy`)
- Add documentation for public APIs
- Include tests for new features

---

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- **Solana Labs** - For the original Solana codebase
- **Anza** - For the Agave validator implementation
- **Gorbagana Community** - For supporting the GorChain ecosystem

---

## Support

- **Documentation**: [docs.gorchain.xyz](https://docs.gorchain.xyz)
- **Discord**: [discord.gg/gorbagana](https://discord.gg/gorbagana)
- **Twitter**: [@GorChainXYZ](https://twitter.com/GorChainXYZ)
- **GitHub Issues**: [github.com/gorbagana/gorchain/issues](https://github.com/gorbagana/gorchain/issues)

---

**Built with ❤️ for the Gorbagana ecosystem**

*Last updated: June 19, 2025*
