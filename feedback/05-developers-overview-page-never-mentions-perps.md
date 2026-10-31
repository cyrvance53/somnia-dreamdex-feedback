# Developers overview page never mentions perps (no guide link, no Hideki RPC row)

Severity: normal
Area: docs

## Steps to reproduce

1. Open the Developers overview (https://app.dreamdex.io/docs/developers) — the front door of the developer documentation.
2. Look for any reference to perps, the perps SDK surface, or the "Perps on Testnet for Developers" guide.
3. Check the page's "Backup RPCs" table for the perps testnet chain.

## Expected

The overview that "covers everything you need to integrate with dreamDEX programmatically" includes the perps developer guide alongside Contracts / HTTP API / WebSocket API / Libraries, and its reliability table covers the Hideki chain (50383) that perps run on.

## Actual

The overview's four bullets are Contracts, HTTP API, WebSocket API, and Libraries (CCXT) — perps and the markets SDK are never mentioned, and there is no link to the perps developer guide anywhere on the page. The Backup RPCs table has two columns only — "Mainnet (5031)" and "Testnet Shannon (50312)" — so the page's own reliability guidance (keep more than one RPC configured, fail over on error) gives a perps builder no Hideki endpoint at all. (The perps guide is reachable from the docs table of contents, but not from the developer section's own overview.)

## Evidence

Developers overview (https://app.dreamdex.io/docs/developers):

> "This section covers everything you need to integrate with dreamDEX programmatically."

> Bullets: "**Contracts**", "**HTTP API**", "**WebSocket API**", "**Libraries**" — no perps entry.

> Backup RPC table header: "|  | Mainnet (`5031`) | Testnet Shannon (`50312`) |"

## Environment

SDK @somnia-chain/markets-sdk 0.32.1, network: Somnia Tokyo testnet, wallet address: N/A — documentation/API issue reproducible from public docs

## Notes

A navigation/completeness gap rather than wrong information; the perps guide exists and is linked from the global contents, but the developer section's own overview and its RPC reliability table silently exclude the entire perps surface the bounty is about.
