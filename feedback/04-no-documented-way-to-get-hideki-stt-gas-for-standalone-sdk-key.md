# No documented way to get Hideki STT gas for a standalone SDK key

Severity: major
Area: docs

## Steps to reproduce

1. Follow "Perps on Testnet for Developers" (https://app.dreamdex.io/docs/developers/perps-testnet) as a headless SDK user: create a fresh key, install `@somnia-chain/markets-sdk`, and look for how to fund that key with STT gas on chain 50383.
2. Read the page's "Get test funds" section in full.
3. Cross-check the bot kit: README's testnet-funds link, and `docs/perps.md`'s own-account mode ("Leave `OWNER_ADDRESS` blank to trade the key's own perps account").

## Expected

A documented funding route for an arbitrary Hideki address — a faucet link for chain 50383, or explicit steps that work for a key that is not linked to an app wallet.

## Actual

The developer guide's only STT route runs through the consumer app: sign in at app.testnet.dreamdex.io, use **Link a Bot** with your key's address, then "Send it … for gas" or "Top up" — i.e., the key must first be linked as a bot to an app (Somnia Account) wallet. The bot kit README sends readers to testnet.somnia.network for testnet funds, which is the Shannon faucet (chain 50312 — the README itself pairs that link with Shannon setup). And the bot kit's own-account mode states the requirement without a source: "That key then needs USDso in its own MarginBank and STT for gas." No page in the developer docs, bot kit README, or bot kit perps doc names a faucet or funding flow for chain 50383.

## Evidence

Developer guide (https://app.dreamdex.io/docs/developers/perps-testnet):

> "**STT for gas.** The simplest route is through the app: sign in at app.testnet.dreamdex.io, then Link a Bot with your key's address and use **Send it … for gas** or **Top up**."

Bot kit README (https://github.com/somnia-chain/dreamdex-bot-kit):

> "Start on **Shannon testnet** (`NETWORK=testnet`, chain `50312`) with small size before you touch mainnet (`5031`). Get testnet funds at testnet.somnia.network."

Bot kit docs/perps.md (https://github.com/somnia-chain/dreamdex-bot-kit/blob/main/docs/perps.md):

> "Leave `OWNER_ADDRESS` blank to trade the key's own perps account instead. That key then needs USDso in its own MarginBank and STT for gas."

## Environment

SDK @somnia-chain/markets-sdk 0.32.1, network: Somnia Tokyo testnet (chain 50383), wallet address: N/A — documentation/API issue reproducible from public docs

## Notes

The bounty is explicitly about stress-testing the API and SDK, whose users are headless by default; the documented gas path forces a detour through the consumer app's bot-linking flow, and a builder who misses that detour is fully blocked (every perp transaction needs STT: orders cost 0.0003–0.003 STT each, stop orders lock 0.15 STT). If a Hideki faucet does exist, the fix is one link; if it doesn't, the gap is bigger than docs.
