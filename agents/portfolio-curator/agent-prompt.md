# Agent prompt (sanitized) · cron `50 8 1 * *` (America/Los_Angeles)

```text
Monthly update of the owner's public GitHub portfolio:
https://github.com/<owner>/ai-automation-portfolio (live site on GitHub Pages).
Keep the final report to a few short lines.

Goal: find new projects from the last month that fit the portfolio (AI agents,
scheduled workflows/automations, web apps/tools, websites, product specs) and add
them, so the portfolio stays current for recruiters.

Where to look for new work:
1. The owner's Claude artifacts updated in the last ~35 days.
2. The owner's scheduled tasks created in the last ~35 days — these are agents/workflows.
3. New or recently updated public repos on the owner's GitHub account.

GitHub access: the GitHub connector. Commit with COMMIT_MULTIPLE_FILES to branch main.

Repo structure to follow: agents/<slug>/README.md (+ sanitized prompt/config files),
apps/<slug>/index.html + README.md, websites/<slug>/index.html (+ websites/README.md
table), product-specs/<slug>/index.html + README.md. Then update the root README.md
(shields.io badges, 2-column project cards for agents, tables with "▶ Live" badges
linking to the Pages URL, collapsible mermaid diagrams) and the root index.html
landing page cards to include each new project.

Strict confidentiality rules — never publish: employer name or payroll/employee data;
bank names, account numbers, balances, EINs, accounting-system IDs; client, tenant,
or customer names; personal addresses; leases/legal agreements; anything from
projects marked confidential; tax or financial figures. Replace with placeholders
(e.g. ****1111, Example Services). Public business info for the owner's own
business is OK. When unsure, leave it out and mention it in the report.

Before finishing: verify every new link works (GitHub links via the API; Pages URLs
may take a few minutes after commit). Do not delete anything, do not change repo
visibility, do not touch other repos.

If nothing new qualifies, make no commits and report "No new portfolio projects
this month." Otherwise report what was added with links.
```
