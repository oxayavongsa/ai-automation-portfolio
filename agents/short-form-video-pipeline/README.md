# Claude → CapCut Short-Form Video Pipeline

An agent workflow that turns a one-line topic into an editable CapCut project for YouTube Shorts / Reels / TikTok (9:16) or YouTube long-form (16:9), using a Model Context Protocol (MCP) server to write CapCut drafts directly.

**Status:** designed and configured; scaling niche/style selection in progress

## Flow

```
Topic request
   │
   ▼
Claude agent ── writes hook, script, timed scene list, caption cues
   │
   ▼  (MCP tool calls)
CapCut MCP server ── writes draft JSON into CapCut's local drafts folder
   │                  (captions at second markers, scene breaks, music placeholders)
   ▼
CapCut Desktop ── apply TTS voiceover + AI visuals ── export ── upload
```

## Why MCP

The model doesn't just generate a script for a human to copy-paste. It *builds the project file*. Caption timing, scene cuts, and aspect ratio are set programmatically, so the human step shrinks to review, voice, and export.

## Config

See [`claude_desktop_config.example.json`](claude_desktop_config.example.json) for how the MCP server is registered (Node command + `CAPCUT_DRAFTS_PATH` env var).

## Example agent prompt

```text
Create a 45–50 second YouTube Short on "<topic>".
Split it into timed segments (hook 0–3s, 3–4 beats, CTA last 5s).
Place each caption at its second marker.
Create a 9:16 CapCut draft named "<slug>" with scene breaks and a music placeholder.
```

## Skills shown

MCP integration · agentic tool use · local-file automation · content pipeline design
