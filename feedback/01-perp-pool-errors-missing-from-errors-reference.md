# Perp pool errors are missing from the Errors reference the perps guide points to

Severity: major
Area: contracts

## Steps to reproduce

1. Open "Perps on Testnet for Developers" (https://app.dreamdex.io/docs/developers/perps-testnet), section "An IOC that fills nothing reverts."
2. Follow its pointer: "The full list of order errors is on the Errors page."
3. On the linked Errors page (https://app.dreamdex.io/docs/developers/contracts/errors), search the page text for the perp errors the guide itself names: `InsufficientCollateral`, `MaxPositionSizeExceeded`, `IsolatedMarketBlocked`, or even the word "Perp."

## Expected

The Errors page (or a linked perps errors page) lists the PerpPool custom errors with selectors and fixes — at minimum the ones the perps guide tells builders they will hit.

## Actual

The Errors page contains only two tables: **SpotPool errors** and **SpotStopOrderRegistry errors**. None of the perp errors appear anywhere on the page (verified by full-text search of the page on 2026-10-30: zero matches for "Perp", "InsufficientCollateral", "MaxPositionSizeExceeded", "IsolatedMarketBlocked"). A builder whose perp order reverts has no official way to decode it.

## Evidence

Perps developer guide (https://app.dreamdex.io/docs/developers/perps-testnet):

> "0.1 SOL written with 18 decimals is 100,000,000 SOL, and `placeOrderFor` reverts with `InsufficientCollateral()` (`0x3a23d825`)."

> "An order that would take the account past it reverts with `MaxPositionSizeExceeded()` (`0x714b36d6`)"

> "Orders anywhere else revert with `IsolatedMarketBlocked`"

> "The full list of order errors is on the Errors page."

Errors page (https://app.dreamdex.io/docs/developers/contracts/errors) — its own scope statement and section headings:

> "The Somnia DEX contracts revert with custom errors… This page maps every selector to its error so integrators can decode a revert instead of guessing."

Sections present: "SpotPool errors" and "SpotStopOrderRegistry errors" only. Note the page claims to map **every** selector, which makes the omission a correctness problem, not just a missing page.

## Environment

SDK @somnia-chain/markets-sdk 0.32.1 (per developer docs), network: Somnia Tokyo testnet (chain 50383 per the developer docs — see the separate feedback item on the network-name problem), wallet address: N/A — documentation/API issue reproducible from public docs

## Notes

Error decoding is the core debugging loop for API/SDK integrators, the missing errors are the most common perps reverts (the guide itself leads with the decimal-scaling → `InsufficientCollateral` trap), and the reference page claims completeness ("maps every selector").
