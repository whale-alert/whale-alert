# Whale Alert

[![Documentation](https://img.shields.io/badge/docs-whale--alert.io-blue.svg?style=flat-square)](https://docs.whale-alert.io)
[![Supported Chains & Symbols](https://img.shields.io/badge/status-supported%20chains%20%26%20symbols-brightgreen.svg?style=flat-square)](https://leviathan.whale-alert.io/status?format=true)
[![Code Examples](https://img.shields.io/badge/examples-github-orange.svg?style=flat-square)](https://github.com/whale-alert/whale-alert-examples)

Whale Alert APIs provide real-time blockchain transaction data, including entity attribution and price data for use as potential market signals across major blockchain networks.

[Developer Portal](https://developer.whale-alert.io/api-account/login) | [Documentation](https://docs.whale-alert.io) | [Live Supported Chains & Symbols](https://leviathan.whale-alert.io/status?format=true) | [Examples Repository](https://github.com/whale-alert/whale-alert-examples)

---

## Overview

Tracking transactions across multiple networks using raw blockchain nodes requires maintaining separate indexers, address tagging datasets and analytics, and specialized contract tracing.

Whale Alert standardizes transaction data across all supported networks into a single clean format with built-in entity attribution and price data.

### Core Features

* **Complete Transfer Coverage (No Extra Parsing)**: Captures all transfers out of the box, including internal contract calls, multi-calls, batch transfers, and router contract executions (such as on Ethereum/EVM) that are invisible to basic RPC event listeners. No specialized tracing or contract decoding required.
* **Unified Multi-Chain Schema**: Standardized JSON data format (Parquet format available for Enterprise+ subscriptions) across Bitcoin, Ethereum, Solana, Ripple, Tron, and other supported networks. Ideal for tracking assets like USDT or USDC across blockchains.
* **Live Per-Block Entity Attribution**: Attribution analytics run dynamically on every newly confirmed block as it becomes available. New addresses and wallet clusters are analyzed and tagged in real time, delivering up-to-the-minute entity intelligence rather than delayed batch updates.
* **Exact Post-Transaction Balances**: Each transaction includes resulting balances for all participating addresses at transaction completion, guaranteed 100% accurate down to the satoshi or base decimal equivalent.
* **Multi-Source USD Spot Pricing**: Transfer valuations are calculated at the transaction timestamp using aggregated price feeds from multiple sources.
* **Verified Asset Whitelist (Zero Token Spoofing)**: Every tracked asset is strictly authenticated against official token contracts, meaning zero risk of ingesting fake, spam, or copycat tokens pretending to be legitimate coins.
* **Low-Latency Delivery**: WebSocket streams and REST endpoints for algorithmic systems, data ingestion, and alerting infrastructure.
* **Live Network Status**: View actively supported blockchains, assets, and tracked symbols in real time at [leviathan.whale-alert.io/status?format=true](https://leviathan.whale-alert.io/status?format=true).

---

## API Plans

| Plan | WebSocket | Historical Lookback | Rate Limit | Primary Use Case |
| :--- | :--- | :--- | :--- | :--- |
| **WebSocket API** | Live alerts | Real-time only | Alerts: 100/hour  | Real-time bots, webhook dispatchers, live alert feeds. |
| **Enterprise API** | Live alerts | 90 days rolling | Alerts: 2,000/h <br />API Calls: 1,000 CPM | Quantitative trading, data pipelines, short-term backfills. |
| **Enterprise Plus API** | Live alerts | Full history (Genesis to present*) | Alerts: 2,000/h <br />API Calls: 2,000 CPM  | Macro research, long-term backtesting, institutional compliance. |

\* *Partial histories are available for Ripple and Solana.*

> **Custom Plans**: Tailored solutions are also available with dedicated machines and higher rate limits. Contact our team to discuss custom requirements.

---

## Examples & Integration Guides

Working examples in Go and Python are available in the [`whale-alert-examples`](https://github.com/whale-alert/whale-alert-examples) repository:

| Guide | Description | Go | Python | Target Plan |
| :--- | :--- | :---: | :---: | :--- |
| **01. WebSocket Live Stream** | Connect, authenticate, handle heartbeats, and read live events. | [Go](https://github.com/whale-alert/whale-alert-examples/tree/main/go/01_websocket_live_stream) | [Python](https://github.com/whale-alert/whale-alert-examples/tree/main/python/01_websocket_live_stream) | All Plans |
| **02. Wallet Watcher** | Track specific addresses. | [Go](https://github.com/whale-alert/whale-alert-examples/tree/main/go/02_wallet_watcher) | [Python](https://github.com/whale-alert/whale-alert-examples/tree/main/python/02_wallet_watcher) | Enterprise / Enterprise Plus |
| **03. Stablecoin Mints, Burns, Freezes & Locks** | Track real-time stablecoin issuance (mints), burns, (un)freezes, and (un)locks. | [Go](https://github.com/whale-alert/whale-alert-examples/tree/main/go/03_stablecoin_mints_burns) | [Python](https://github.com/whale-alert/whale-alert-examples/tree/main/python/03_stablecoin_mints_burns) | Enterprise / Enterprise Plus |
| **04. Historical Query** | Query past transactions with cursor pagination and volume aggregation. | [Go](https://github.com/whale-alert/whale-alert-examples/tree/main/go/04_historical_query) | [Python](https://github.com/whale-alert/whale-alert-examples/tree/main/python/04_historical_query) | Enterprise / Enterprise Plus |
| **05. Historical Balance** | Look up the exact cryptocurrency balance at a specific time. | [Go](https://github.com/whale-alert/whale-alert-examples/tree/main/go/05_historical_balance) | [Python](https://github.com/whale-alert/whale-alert-examples/tree/main/python/05_historical_balance) | Enterprise / Enterprise Plus |
| **06. Chain Reorganization & Orphan Detector** | Real-time reorg detection, sliding block cache, and orphan depth calculation. | [Go](https://github.com/whale-alert/whale-alert-examples/tree/main/go/06_reorg_detector) | [Python](https://github.com/whale-alert/whale-alert-examples/tree/main/python/05_historical_balance) | Enterprise / Enterprise Plus |

---

## Quick Start

1. Get an API key at [developer.whale-alert.io/api-account/login](https://developer.whale-alert.io/api-account/login).
2. Set the environment variable:
   ```bash
   export WHALE_ALERT_API_KEY="your_api_key_here"
   ```
3. Run the Go WebSocket quickstart:
   ```bash
   git clone https://github.com/whale-alert/whale-alert-examples.git
   cd whale-alert-examples/go/01_websocket_live_stream
   go run main.go
   ```

---

## Technical Resources

* Documentation: [docs.whale-alert.io](https://docs.whale-alert.io)
* Supported Chains & Symbols: [leviathan.whale-alert.io/status?format=true](https://leviathan.whale-alert.io/status?format=true)
* Developer Portal: [developer.whale-alert.io/api-account/login](https://developer.whale-alert.io/api-account/login)
* Contact: [developers@whale-alert.io](mailto:developers@whale-alert.io) | [enterprise@whale-alert.io](mailto:enterprise@whale-alert.io)
