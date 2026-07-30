# UTYA Price Bot

A Telegram service for UTYA market publishing and resilient multi-destination trade alerts.

<!-- Add a freshly captured, redacted UTYA post here. -->

| | |
|---|---|
| Live bot | [UTYA Prices on Telegram](https://t.me/utyapricesbot) |
| Audience | UTYA community operators and followers |
| Role | Designed, implemented, deployed, and maintained by Nic |
| Status | Active deployment |
| Implementation | Proprietary |

## Product experience

UTYA Price Bot publishes a concise recurring price while its private control plane manages formatting, cadence, alert thresholds, and destinations. Buy/sell notifications can be delivered to several Telegram targets with progress-aware retries.

## Core features

- Validated UTYA market snapshots
- Scheduled Telegram price posts
- Provider fallback, cache reuse, and backoff
- TON decentralized-exchange trade monitoring
- Multiple alert destinations
- Destination validation and duplicate removal
- Retry continuation from the first unfinished destination
- Private menu, activity summary, and health information

## Architecture

Price publishing and event monitoring share validated market context but maintain separate failure state. Alert delivery records progress for each configured target.

Read [Architecture](docs/architecture.md).

## Technology

Python standard library, Telegram Bot API, CoinGecko, DexScreener, TON providers, private local state, and systemd.

## Engineering highlights

- Consistent UTYA identity across provider results
- Safe fallback under provider throttling
- Cross-venue buy/sell classification
- Progress-aware multi-destination alert retries
- Persistent deduplication and cursor recovery

## Current status

The service reports active. Tests cover multi-destination validation, retry resumption, provider validation, trade classification, outbox safety, and menu controls.

This is a non-runnable showcase. It contains no source, addresses, credentials, controllers, provider paths, state, or deployment configuration.

[Roadmap](docs/roadmap.md) · [License](LICENSE) · Created by **Nic** ([GitHub](https://github.com/dev-nic-codes))
