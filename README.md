# dreamDEX Perps Builder Bounty — Feedback Submission

Feedback on the dreamDEX perps developer experience (docs, SDK, and API references), prepared for the **dreamDEX Perps Builder Bounty** on DoraHacks (https://dorahacks.io/hackathon/dreamdex-perps-bounty/detail). Each item below was verified on 2026-10-30 against the live documentation pages and the official bot kit repository, and is quoted verbatim with its source URL in the linked file — every issue is reproducible from the public docs alone, with no wallet or testnet access required. The findings concentrate on the perps onboarding path: builders following the official guides hit a missing perp errors reference, three different names for the same testnet chain, a bot kit README that omits the perps network, no documented gas-funding route for a standalone SDK key, a developer overview that never mentions perps, and an official event listing whose dates conflict with the submission deadline.

Prepared by **Lux Automations** for the dreamDEX Perps Builder Bounty (Feedback track).

## Feedback files

| File | Severity | Area |
|---|---|---|
| [01 — Perp pool errors are missing from the Errors reference the perps guide points to](feedback/01-perp-pool-errors-missing-from-errors-reference.md) | major | contracts |
| [02 — The bounty calls the network "Somnia Tokyo testnet"; the developer docs never use that name for it](feedback/02-bounty-calls-network-somnia-tokyo-docs-say-hideki.md) | major | docs |
| [03 — Bot kit README's Networks table and quick start omit the Hideki perps network entirely](feedback/03-bot-kit-readme-omits-hideki-perps-network.md) | major | SDK |
| [04 — No documented way to get Hideki STT gas for a standalone SDK key](feedback/04-no-documented-way-to-get-hideki-stt-gas-for-standalone-sdk-key.md) | major | docs |
| [05 — Developers overview page never mentions perps (no guide link, no Hideki RPC row)](feedback/05-developers-overview-page-never-mentions-perps.md) | normal | docs |
| [06 — The official Eventbrite listing gives different bounty dates than DoraHacks (and disagrees with itself)](feedback/06-eventbrite-listing-gives-different-bounty-dates-than-dorahacks.md) | normal | docs |

## Further checks in progress

- CCXT examples use `SOMI/USDC`, a market the API docs say does not exist
- Docs pin SDK version 0.32.1; current published version unverified
- Perp market count: Somnia Markets explorer says 24, dreamDEX docs table lists 21
- Paper USDso claim route described three different ways across official texts
- Bot kit quick start, followed literally (README + perps doc)
- Bot kit's perp order gas limit vs the guide's "10,000,000" claim
