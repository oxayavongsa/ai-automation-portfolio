<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=26&pause=1000&color=14B8A6&center=true&vCenter=true&width=720&lines=AI+Automation+Portfolio;Agents+that+do+real+work;Built+for+real+small+businesses" alt="Typing intro" />

**Outhai (Thai) Xayavongsa** · Applied AI · Agentic Automation · Compliance & Document Intelligence

<a href="https://oxayavongsa.github.io/ai-automation-portfolio/"><img src="https://img.shields.io/badge/▶_Live_Portfolio-14B8A6?style=for-the-badge" alt="Live portfolio" /></a>
<a href="https://github.com/oxayavongsa/ai-agents"><img src="https://img.shields.io/badge/Python_Agents_Repo-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="ai-agents repo" /></a>
<a href="https://www.linkedin.com/in/oxayavongsa"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>

<img src="https://img.shields.io/badge/MS-Applied_AI_(USD)-6D28D9" alt="MS Applied AI" />
<img src="https://img.shields.io/badge/MBA-Business-1E3A8A" alt="MBA" />
<img src="https://img.shields.io/badge/10_yrs-Payroll_%26_Compliance-B45309" alt="10 years payroll and compliance" />
<img src="https://img.shields.io/badge/open_to-remote_AI%2FML_roles-16A34A" alt="Open to remote roles" />

</div>

> I build AI agents and automations that do **real operational work** for small businesses: reconciling books, screening deals, producing marketing content, and shipping the web tools customers use. Everything here was built for businesses I run, then sanitized for public view.

---

## 🧭 At a glance

<table>
<tr>
<td width="50%" valign="top">

### 🤖 Agents & workflows
**4** production agents and pipelines
Scheduled, guardrailed, tool-using

</td>
<td width="50%" valign="top">

### 🌐 Live demos
**5** pages running on GitHub Pages
Click any **▶ Live** badge below to try one

</td>
</tr>
</table>

---

## 🤖 Agents & scheduled workflows

<table>
<tr>
<td width="50%" valign="top">

### 🧾 [Bookkeeping Reconciliation Agent](agents/bookkeeping-reconciliation-agent/)
Cron-scheduled agent that reconciles QuickBooks to bank-statement PDFs, reverses duplicates with journal entries, applies owner rules, and returns a tax-ready review packet.

<img src="https://img.shields.io/badge/Claude-agent-D97757" /> <img src="https://img.shields.io/badge/QuickBooks-API-2CA01C" /> <img src="https://img.shields.io/badge/cron-scheduled-555" />

</td>
<td width="50%" valign="top">

### 🚗 [Vehicle Deal Screener](agents/vehicle-deal-screener/)
Marketplace alerts → LLM classifier → SMS. Texts only listings that clear a resale-profit and clean-title bar.

<img src="https://img.shields.io/badge/Zapier-automation-FF4A00" /> <img src="https://img.shields.io/badge/Claude-classifier-D97757" /> <img src="https://img.shields.io/badge/output-2--state-555" />

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🎬 [Short-Form Video Pipeline](agents/short-form-video-pipeline/)
Topic → script → timed scenes → a real CapCut project file, written directly by the agent through an MCP server.

<img src="https://img.shields.io/badge/MCP-server-000" /> <img src="https://img.shields.io/badge/Node.js-339933?logo=node.js&logoColor=white" /> <img src="https://img.shields.io/badge/CapCut-drafts-555" />

</td>
<td width="50%" valign="top">

### 📣 [AI Video Ad Generator](agents/ai-video-ad-generator/)
Reusable prompt system for realistic 15-second vertical commercials for local businesses.

<img src="https://img.shields.io/badge/Seedance-text--to--video-7C3AED" /> <img src="https://img.shields.io/badge/prompt-engineering-555" />

</td>
</tr>
</table>

<details>
<summary><b>🔍 How the reconciliation agent works</b> (click to expand)</summary>

```mermaid
flowchart LR
    A[📄 Bank statement PDFs] --> B[Parse with pdftotext]
    Q[(QuickBooks API)] --> C
    B --> C{Match by amount<br/>0 → 3 → 7 → 15 days}
    C -->|matched| D[Apply owner rules]
    C -->|bank-only / ledger-only| E[Exception list]
    D --> F{Duplicate?}
    F -->|yes| G[Reversing journal entry]
    F -->|no| H[Book it]
    E --> I[Uncategorized + review list]
    G --> J[✅ Balance check vs 12/31]
    H --> J
    I --> J
    J --> K[📋 Tax-ready report]
```

**Guardrails:** the agent can't delete, send, or file anything. Every correction is a reversible journal entry, and anything unexplained goes to a human review list.
</details>

<details>
<summary><b>🔍 How the deal screener works</b> (click to expand)</summary>

```mermaid
flowchart LR
    A[🔔 Saved-search alerts<br/>Craigslist · OfferUp] --> B[Zapier parses listing]
    B --> C[🤖 Claude screens<br/>title · price · scam signals]
    C -->|None| D[🗑️ Discard]
    C -->|Worth a look| E[📱 SMS alert]
```
</details>

---

## 🛠️ Apps & tools

| | Project | What it does | Try it |
|:-:|---|---|:-:|
| 📵 | [**Junk Text Triage**](apps/junk-text-triage/) | Private, in-browser SMS-backup analyzer. Ranks junk senders and sorts them into scam, marketing, and OTP. Nothing is uploaded | [![Live](https://img.shields.io/badge/▶_Live-14B8A6?style=flat-square)](https://oxayavongsa.github.io/ai-automation-portfolio/apps/junk-text-triage/) |
| ⚡ | [**Dev Cheatsheets**](apps/dev-cheatsheets/) | Side-by-side syntax for Python, JavaScript, SQL, Java, C++, and Bash | [![Live](https://img.shields.io/badge/▶_Live-14B8A6?style=flat-square)](https://oxayavongsa.github.io/ai-automation-portfolio/apps/dev-cheatsheets/) |

## 🌐 Websites

| | Project | Highlights | Try it |
|:-:|---|---|:-:|
| 🖋️ | [**Mobile Notary Services & Pricing**](websites/) | Animated ticker, tiered service roadmap, intro-rate pricing, 5-step booking flow | [![Live](https://img.shields.io/badge/▶_Live-14B8A6?style=flat-square)](https://oxayavongsa.github.io/ai-automation-portfolio/websites/notary-landing-page/) |
| ✅ | [**Notary Onboarding Guide**](websites/) | Interactive New vs. Renewing checklist with a resource hub | [![Live](https://img.shields.io/badge/▶_Live-14B8A6?style=flat-square)](https://oxayavongsa.github.io/ai-automation-portfolio/websites/notary-onboarding-guide/) |

## 📐 Product design

| | Project | Summary | Read it |
|:-:|---|---|:-:|
| 🧾 | [**AI Receipt & Mileage App: PRD**](product-specs/expense-mileage-app/) | Pricing tiers, 7 industry templates, a dimension-based data model, AI OCR and categorization, phased build plan | [![Spec](https://img.shields.io/badge/▶_Open_spec-B4541F?style=flat-square)](https://oxayavongsa.github.io/ai-automation-portfolio/product-specs/expense-mileage-app/) |

## 🐍 More code

Python agents that run my notary admin every morning (rotation tracking, ad-queue checks, quote estimates) live in **[ai-agents](https://github.com/oxayavongsa/ai-agents)**.

---

## 💡 What I bring

<details open>
<summary><b>Skills</b></summary>

- 🛡️ **Agent design with guardrails:** scheduled, unattended agents with explicit forbidden actions, reversible corrections, and human-review queues
- 🔌 **Tool integration:** MCP servers, REST connectors (QuickBooks, Square, Stripe, Calendly), no-code orchestration (Zapier)
- 📄 **Document intelligence:** PDF and statement parsing, OCR pipelines, classification with confidence gating
- ⚖️ **Compliance depth:** certified payroll, Davis-Bacon and prevailing wage, fringe benefits, union agreements
- 🚀 **Full-stack delivery:** from PRD and data model to a shipped, responsive front end
</details>

### 🧰 Stack

<p>
<img src="https://skillicons.dev/icons?i=py,js,html,css,nodejs,git,github,vscode&theme=dark" alt="Tech stack icons" />
</p>

<img src="https://img.shields.io/badge/Claude-D97757?style=flat-square&logo=anthropic&logoColor=white" /> <img src="https://img.shields.io/badge/MCP-000000?style=flat-square" /> <img src="https://img.shields.io/badge/Zapier-FF4A00?style=flat-square&logo=zapier&logoColor=white" /> <img src="https://img.shields.io/badge/QuickBooks-2CA01C?style=flat-square&logo=quickbooks&logoColor=white" /> <img src="https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white" /> <img src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white" />

---

<div align="center">

**Open to remote AI/ML, automation, and payroll-tech roles.**

<a href="https://github.com/oxayavongsa"><img src="https://img.shields.io/badge/GitHub-oxayavongsa-181717?style=for-the-badge&logo=github" /></a>
<a href="https://www.novard.ai"><img src="https://img.shields.io/badge/Web-novard.ai-14B8A6?style=for-the-badge" /></a>

</div>
