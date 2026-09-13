# Ghost Protocol — Personal Security Checklist

A single-file, self-contained, interactive personal cybersecurity checklist. Matrix rain, a rank/threat-meter HUD, a hidden terminal, an AI chat assistant, and a stack of easter eggs — built for Astra.

**[Live version](https://claude.ai/code/artifact/a5e30018-7271-48d9-a2a0-fb642da3651c)** *(hosted via Claude Artifacts)*

## What it is

41 checklist items across four tiers, ordered from "do this today" to "this is genuinely nitty-gritty":

- **00 · ROOT ACCESS** — the critical path (password manager, MFA, updates, disk encryption, backups, router defaults, credit freeze, recovery codes)
- **01 · PERIMETER** — hardware keys, login alerts, email separation, OAuth audits, Wi-Fi hardening, VPN, breach monitoring
- **02 · DEEP FIELD** — DNS, tracker blocking, email aliases, social privacy, data brokers, encrypted messaging, firewalls
- **03 · GHOST PROTOCOL** — key rotation, canary tokens, isolated browsing, self-hosted vaults, hardware SSH keys, VLANs, GPG, air-gapped backups

Each item has a small chevron dot — click it to reveal *why it matters* and how to do it, written in plain language with real detail rather than a one-line summary (nothing shows until you click it). Specific tools/services mentioned there (password managers, encryption tools, breach-check sites, etc.) are hyperlinked straight to their current official pages.

## Customize each tier

Every tier can be reshaped to fit your actual life. Click **"Customize this list"** right under a tier's header to reveal:

- **+ Add item** — add your own item to that tier: title, optional one-line note, optional detail — for anything specific to you (a particular account, device, or habit) that isn't already covered.
- **✦ AI suggest** — asks the AI chat to propose several new, non-duplicate items for that tier — often broken out per-account (e.g. one item each for your email, bank, work SSO, socials) — and lets you pick which ones to actually add. Needs the live AI-connected version of the page.
- **N hidden** — restores anything you've hidden.

**×** on any item (built-in or one you added yourself) hides it from view — nothing is ever deleted, it "remains" in your saved data and comes back from the hidden list above. Each item's expanded detail also has its own **"+ add a related item"** link, so you can add something specific to that exact item (like a particular account) without hunting for the tier-wide controls.

Hiding or adding items changes what counts toward your percentage and rank — hide something that doesn't apply to you and it stops being held against your score; add something and it becomes part of your checklist, same as anything built in.

## AI chat

The bottom-right terminal (`>_`) doubles as a chat assistant — ask it anything about the checklist or security in general and it'll answer in-terminal. It runs on Claude's built-in Artifact chat capability (no API key, no separate backend, no meaningful token cost), so it only works on the live Artifact-hosted version, not a plain static copy of `index.html`. If it's unavailable in a given viewer's context, the terminal quietly falls back to its fixed command set.

## Sound

Small synthesized sound effects (checkbox ticks, achievement chimes, terminal blips) via the Web Audio API — no audio files. Muted by default is off; toggle with the speaker icon in the top HUD. The setting is remembered per browser.

## How state works

- **Checkbox progress** is saved in `localStorage`, per browser. Anyone who opens the link gets their own blank run — nothing is shared or synced between viewers by default.
- **The visit counter** tries to use a shared backend store (Claude's `db` artifact capability) for a real cross-visitor count; if that's unavailable to a given viewer (e.g. they're outside the artifact owner's org), it falls back to a local per-browser tally, labeled accordingly.

## Easter eggs

Told, not hidden — per request:

1. **The mini terminal** (bottom-right `>_` button) — type `help` for the full command list (`whoami`, `rank`, `progress`, `achievements`, `matrix`, `neo`, `sudo`, `credits`, `clear`, `exit`), or just ask it a question.
2. **Konami code** — ↑ ↑ ↓ ↓ ← → ← → B A anywhere on the page triggers a full-screen matrix flash and an achievement.
3. **Logo click** — click the `GHOST_PROTOCOL` logo top-left 5 times quickly to pop a hidden credits panel.
4. **The hidden pixel** — a barely-visible dot in the footer next to the version number. Click it for a "bug bounty" achievement.
5. **"Touch grass"** — the last item in tier 03 is only half a joke; checking it triggers its own reaction.
6. **`matrix` terminal command** — flashes a full-screen matrix takeover.
7. **`neo` terminal command** — flips an "invert" mode. The first time you ever type it, it says "Follow the white rabbit." Every time after that, it replies with a different random line from *The Matrix* or *Alice in Wonderland*.
8. **The white rabbit** — every so often, a small rabbit sprints across the bottom of the screen. Click it before it escapes: the first catch turns the whole site red, the second turns it pink, and every catch after that shifts it to a new random neon color. The color sticks around (saved per browser) until you catch it again.
9. **The browser console** — open devtools on the page for an ASCII-styled greeting most visitors will never see.
10. **100% completion** — clearing all 41 items triggers a full-screen "DIGITAL GHOST / FULL CLEARANCE" celebration with a particle burst.
11. **Achievements** — tracked quietly per browser: first check, each tier cleared, 3 easter eggs found ("EASTER HUNTER"), and full clearance.

## Tech

Single HTML file. No build step, no dependencies beyond a Google Fonts import (Orbitron + JetBrains Mono). Matrix rain is a `<canvas>` loop; everything else is vanilla CSS/JS.

- `index.html` — the whole site.

## Running it locally

Just open `index.html` in a browser. No server required.

---
Built by Claude, for Astra.
