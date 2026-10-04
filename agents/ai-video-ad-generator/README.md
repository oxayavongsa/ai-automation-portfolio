# AI Video Ad Generator (Local-Business Commercials)

A reusable prompt-engineering workflow for producing 15-second vertical (9:16) Instagram commercials with text-to-video models, built for a real local service business and templated for reuse.

## Problem

Text-to-video models produce glossy, generic, often wrong output: misspelled text, the wrong landmark, uncanny faces. A local business needs ads that look real, relatable, and on-brand.

## Approach

| Technique | Why |
|---|---|
| **Second-by-second shot list** (0–2s, 2–4s, …) | Forces pacing; the model stops improvising filler |
| **Faceless talent** (hands, forearms, torso only) | Avoids uncanny-valley faces; keeps focus on the service |
| **Negative constraints** ("NOT a suspension bridge", "not wax, not a wax seal") | Corrects the model's most likely wrong guesses |
| **Exact on-screen text** spelled out, with layout | Text rendering is the #1 failure point; constrain it tightly |
| **Motion grammar** (snap → slow-mo, whip-pans, match cuts, freeze-frames) | Gives a consistent, premium editing style |
| **Brand palette** called out explicitly | Keeps every shot on-brand |
| **SFX-only audio spec** | Music and logo end-card added in post for brand control |

## Workflow

1. Brief → shot list (Claude)
2. Shot list → text-to-video model (Seedance via ElevenLabs, 720p, 15s, audio on)
3. Review variations, pick best
4. Add real logo end-card + licensed music in post
5. Save the approved prompt as a template ([`prompt-template.md`](prompt-template.md))

## Skills shown

Prompt engineering for generative video · constraint design · brand-safe AI content · repeatable creative ops
