# Bot kit README's Networks table and quick start omit the Hideki perps network entirely

Severity: major
Area: SDK

## Steps to reproduce

1. Clone the official bot kit (https://github.com/somnia-chain/dreamdex-bot-kit) — the repo the bounty page lists as a resource ("dreamDEX bot kit: perps bot examples and strategies").
2. Follow the README's "Quick start" and "Networks" sections to configure a `perp-*` strategy.
3. Compare with the README's own strategy table and with `docs/perps.md` in the same repo.

## Expected

The README's Networks section lists every network the kit's strategies run on — including the Hideki perps testnet (chain 50383) — and the quick start tells perp builders which `NETWORK` value to use.

## Actual

The README's strategy table says the perp strategies run on a third network — "Perpetual futures on the Hideki testnet" — but the README's **Networks** table lists only Mainnet (5031) and Shannon testnet (50312), with spot REST/WebSocket endpoints. Hideki's chain ID, RPC, and `NETWORK=hideki` value appear nowhere in the README; the quick start actively points the other way ("add your PRIVATE_KEY, keep NETWORK=testnet"; "Start on Shannon testnet (NETWORK=testnet, chain 50312)"). The correct configuration exists only in `docs/perps.md`, which the README's perps row links for strategy details but the Networks/quick-start path never mentions.

## Evidence

README (https://github.com/somnia-chain/dreamdex-bot-kit):

> Strategy table: "`strategies/perp-*` | **Perpetual futures** on the Hideki testnet: perp-starter, perp-maker, perp-funding, perp-guard."

> Networks table headings: "|  | Mainnet | Shannon testnet |" with Chain IDs `5031` / `50312` — no Hideki column or row.

> Quick start: "cp .env.example .env # add your PRIVATE_KEY, keep NETWORK=testnet" and "Start on **Shannon testnet** (`NETWORK=testnet`, chain `50312`)…"

docs/perps.md (same repo):

> "The `perp-*` strategies trade DreamDEX perpetual futures. They run on the **Hideki testnet** (chain 50383)…" and its env block uses "NETWORK=hideki".

## Environment

Bot kit repo at commit 4e75896896e024c03e2033d5920514f249998cd6 (main, read 2026-10-30), network: Somnia Tokyo testnet, wallet address: N/A — documentation/API issue reproducible from public docs

## Notes

The bot kit is the bounty's flagship on-ramp for the MVP and feedback tracks; a participant who follows the README (the documented entry point) configures Shannon and cannot reach a single perp market, with no hint in the README that a third network exists.
