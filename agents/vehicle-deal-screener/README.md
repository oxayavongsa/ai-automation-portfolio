# Used-Vehicle Deal Screener Agent

An AI pipeline that watches used-car marketplaces, screens every new listing against resale-profit criteria, and texts only the deals worth acting on.

**Status:** v1 (no-code alert bot) in use · v2 (multi-platform scanner app) in design

## Problem

Good private-party deals sell within hours. Manually scrolling Craigslist, OfferUp, and Nextdoor all day isn't realistic, and most listings are overpriced, salvage-titled, or scams.

## v1 architecture: Zapier + Claude

```
Saved-search email alerts ──► Zapier (parse listing) ──► Claude (screen) ──► SMS alert
   (Craigslist, OfferUp, …)                                 │
                                                            └─► "None" → discard
```

Claude returns exactly one of two outputs, which keeps the downstream automation trivial:

- `None`: listing fails criteria, dropped silently
- `Worth a look: <one-line reason>`: forwarded as a text message

See [`screening-prompt.md`](screening-prompt.md).

## v2 roadmap: scanner app

| Capability | Approach |
|---|---|
| Multi-source ingestion | Marketplace feeds + dealer-lot inventory pages |
| Title check | Filter rebuilt/salvage keywords; VIN decode + history lookup |
| Scam detection | Price-vs-market outliers, stock-photo reuse, off-platform payment language |
| Deal scoring | Est. resale value − asking price − recon cost ≥ profit floor |
| Negotiation | Drafts a polite, data-backed lower-offer message |

## Skills shown

LLM-as-classifier design · constrained output formats · no-code orchestration (Zapier) · product scoping from MVP to app
