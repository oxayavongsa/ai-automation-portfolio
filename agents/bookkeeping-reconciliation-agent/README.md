# Scheduled Bookkeeping Reconciliation Agent

An autonomous AI agent that runs on a schedule, reconciles a small business's QuickBooks Online ledger against its bank statements, applies the owner's accounting rules, and hands back a tax-ready review packet. It never deletes, sends, or files anything on its own.

## Problem

Small S-corps and LLCs close the year with months of unmatched bank lines, duplicate entries, and owner transfers booked inconsistently. A bookkeeper charges hundreds of dollars to clean it up every February.

## What the agent does

| Step | Action |
|---|---|
| 1. Ingest | Parses bank statement PDFs (`pdftotext -layout`) from a cloud folder; pulls ledger transactions through a QuickBooks API connector |
| 2. Match | Matches every bank line to the ledger by exact amount within widening date windows (0 → 3 → 7 → 15 days) |
| 3. Diff | Produces *bank-only* and *ledger-only* exception lists |
| 4. De-dupe | Reverses true duplicates (same amount, same/near date) with numbered journal entries instead of deletes, keeping a full audit trail |
| 5. Apply rules | Classifies owner contributions/distributions, recurring home-office reimbursements, and cash customer payments using owner-defined rules (see [`rules.example.yaml`](rules.example.yaml)) |
| 6. Quarantine | Anything unexplained goes to an *Uncategorized* holding account and a human review list. It never guesses |
| 7. Verify | Confirms each account's ledger balance equals the 12/31 statement balance |
| 8. Report | Posts JEs created, the review list, missing statements, key year-end figures, and the filing deadline reminder |

## Design decisions

- **Cron-scheduled, unattended.** Runs once a year, two weeks before the tax deadline, with no human in the loop until the report.
- **Hard guardrails.** The agent's instructions forbid delete, send, and file actions. Corrections happen through reversible journal entries.
- **Rules as data.** Business logic lives in a rules file, not the prompt, so the same agent can serve multiple entities.
- **Multi-source tracing.** Read-only access to personal-account aggregator data is used *only* to trace owner transfers and customer payments that landed outside the business account.

## Stack

Claude (agentic scheduled task) · QuickBooks Online API (via Composio) · PDF parsing (poppler `pdftotext`) · Personal-finance aggregator API (read-only) · Cron scheduling

## Files

- [`agent-prompt.md`](agent-prompt.md): the full scheduled-agent instruction set (sanitized)
- [`rules.example.yaml`](rules.example.yaml): owner rules expressed as config

> All entity names, account numbers, and IDs in this folder are placeholders.
