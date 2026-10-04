# Agent Prompt (sanitized)

> Scheduled: `CRON_TZ=America/Los_Angeles 52 8 15 2 *` (Feb 15, yearly). Placeholders in `<angle brackets>`.

```text
Annual pre-tax cleanup for <ENTITY_NAME> (California S-corp, Form 1120-S, due March 15).
The tax year to clean up is the calendar year that just ended.

Goal: reconcile QuickBooks Online (via the QuickBooks connector) to the bank statements,
and have the books ready to file.

Data sources:
- Statements are PDFs in the cloud folder "<BANK> <year>". Parse with pdftotext -layout.
- Business accounts:
  - ****1111: main checking
  - ****2222: second checking
  - ****3333: savings
- Personal accounts are visible through the finance-aggregator connection. Use them ONLY
  to trace owner transfers and customer payments that landed personally.

Steps:
1. Match every bank line to QuickBooks by exact amount within 0, 3, 7, then 15 days.
   List bank-only and QuickBooks-only items.
2. Remove duplicates only when they are the same amount on the same or a near date.
   Reverse them with journal entries (doc numbers CLN-<year>-NN), because deleting
   Purchases through the API fails.
3. Apply the owner's rules (see rules.example.yaml).
   Anything unexplained goes to Uncategorized Asset, unreconciled, and on a review list.
4. Confirm the QuickBooks balance of each account equals the 12/31 statement balance.
5. Flag for the owner: payroll liabilities balance, A/P owed to the owner,
   net income, total sales, and officer W-2 wages for the year.
6. Report: the JEs posted, the Uncategorized items needing input,
   any statements missing from the folder, and a reminder that the 1120-S
   (with K-1 and CA Form 100S) is due March 15.

Do not delete anything, send anything, or file anything.
```
