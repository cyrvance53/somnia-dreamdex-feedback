# The bounty calls the network "Somnia Tokyo testnet"; the developer docs never use that name for it

Severity: major
Area: docs

## Steps to reproduce

1. Read the bounty page (https://dorahacks.io/hackathon/dreamdex-perps-bounty/detail): the program is for "dreamDEX perps on **Somnia Tokyo testnet**," and the Feedback template's Environment field reads "network (Somnia Tokyo testnet)."
2. Open the official perps developer guide (https://app.dreamdex.io/docs/developers/perps-testnet) and look for the chain configuration for a "Tokyo" testnet.
3. Search the guide for the word "Tokyo."

## Expected

One canonical network name, used consistently across the bounty page, the submission template, and the developer docs, so a builder can configure the right chain (name + chain ID) from the materials given.

## Actual

The developer guide never presents a "Tokyo" network. It says testnet perps run on the **Hideki** testnet chain (chain ID `50383`, RPC `https://api.hideki2.infra.testnet.somnia.network`), "which the app shows as the **DreamDEX** region." The word "Tokyo" appears in the guide exactly once — inside the block-explorer URL path (`explorer.testnet.somnia.network/tokyo`). Three different names (Tokyo / Hideki / DreamDEX region) are in play for one chain, and the bounty materials use the one name the technical docs don't.

## Evidence

Bounty page (https://dorahacks.io/hackathon/dreamdex-perps-bounty/detail):

> "The Perps Builder Bounty is a developer program for dreamDEX perps on **Somnia Tokyo testnet**."

> Template: "SDK version, network (Somnia Tokyo testnet), wallet address"

Developer guide (https://app.dreamdex.io/docs/developers/perps-testnet):

> "Testnet perps run on the **Hideki** testnet chain, which the app shows as the **DreamDEX** region."

> Network table: Chain ID `50383` · RPC `https://api.hideki2.infra.testnet.somnia.network` · Explorer `explorer.testnet.somnia.network/tokyo`

## Environment

SDK @somnia-chain/markets-sdk 0.32.1, network: Somnia Tokyo testnet, wallet address: N/A — documentation/API issue reproducible from public docs

## Notes

Setup is the first thing every bounty participant does; a builder who follows the bounty page's own network name finds no matching chain in the developer docs and can waste the short bounty window (Oct 19 – Nov 1) configuring the wrong network (e.g. Shannon, chain 50312, which is what "Somnia testnet" means everywhere else in the docs and bot kit).
