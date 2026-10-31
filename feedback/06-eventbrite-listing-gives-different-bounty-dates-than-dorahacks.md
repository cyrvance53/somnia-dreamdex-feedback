# The official Eventbrite listing gives different bounty dates than DoraHacks (and disagrees with itself)

Severity: normal
Area: docs

## Steps to reproduce

1. Read the submission deadline on DoraHacks (https://dorahacks.io/hackathon/dreamdex-perps-bounty/detail), "Timeline" table.
2. Read the organizers' Eventbrite listing for the same program (https://www.eventbrite.com/e/dreamdex-perps-builder-bounty-tickets-2003605109819).
3. Compare start and end dates across the two, and within the Eventbrite page itself.

## Expected

Every official listing for the bounty states the same window: opens October 19, submissions close November 1, 23:59 UTC.

## Actual

DoraHacks: bounty opens October 19; "November 1, 23:59 UTC — Submissions close." Eventbrite's title line says "Tuesday, October 20–Monday, November 2 • 5 AM–4 PM UTC," while its own body text says "Monday, October 19–Monday, November 2 • 10 PM–8 AM PDT" — a different start day from its own title, and an end a full day after submissions actually close. A builder who trusts the Eventbrite dates plans for a November 2 deadline that does not exist.

## Evidence

DoraHacks (https://dorahacks.io/hackathon/dreamdex-perps-bounty/detail):

> "| October 19 | Bounty opens" … "| November 1, 23:59 UTC | Submissions close |"

Eventbrite (https://www.eventbrite.com/e/dreamdex-perps-builder-bounty-tickets-2003605109819):

> "dreamDEX Perps Builder Bounty Tickets, Tuesday, October 20-Monday, November 2 • 5 AM-4 PM UTC"

> "When: 2026-10-19T22:00:00-07:00 to 2026-11-02T08:00:00-08:00"

## Environment

SDK: N/A (program listing), network: Somnia Tokyo testnet, wallet address: N/A — documentation/API issue reproducible from public docs

## Notes

DoraHacks is the venue of record, so this is a conflicting-listing problem rather than a wrong deadline at the source; but the conflicting listing is an official organizer page, and the failure mode is total (a missed deadline loses the whole submission).
