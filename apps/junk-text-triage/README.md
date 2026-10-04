# Junk Text Triage

**[Live demo →](https://oxayavongsa.github.io/ai-automation-portfolio/apps/junk-text-triage/)**

A privacy-first, single-file web app that analyzes an Android SMS backup (SMS Backup & Restore XML) and ranks every junk sender by volume, sorted into **block**, **unsubscribe**, or **ignore**.

## Highlights

- **100% client-side.** The file is parsed in the browser with `FileReader`; nothing is uploaded, sent, or stored.
- **Handles large backups.** Streaming regex parser processes messages in 4,000-record chunks with `setTimeout` yielding so the UI never freezes on 100MB+ files.
- **Rule-based classifier** with 5 categories: scam/phishing, marketing, automated alerts, verification codes, real conversation.
  - Scam signals: smishing phrases (unpaid toll, package held, account locked), URL shorteners, "wrong number" openers
  - Opt-out language → legitimate marketing (STOP is safe to send)
  - Shortcodes, toll-free prefixes, OTP patterns
  - Known contacts or any outbound reply → protected as a real conversation
- **Actionable output.** Per-category advice (why replying STOP to a scammer is harmful), one-click "copy block list."
- Accessible: keyboard focus states, `aria-pressed` filters, reduced-motion support, light/dark themes.

## Stack

Vanilla JavaScript · HTML/CSS · zero dependencies · zero network calls
