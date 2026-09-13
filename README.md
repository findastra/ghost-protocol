# Ghost Protocol — Personal Security Checklist

A single-file, self-contained, interactive personal cybersecurity checklist. Matrix rain, a rank/threat-meter HUD, a hidden terminal, and a stack of easter eggs — built for Audra.

**[Live version](https://claude.ai/code/artifact/a5e30018-7271-48d9-a2a0-fb642da3651c)** *(hosted via Claude Artifacts)*

## What it is

41 checklist items across four tiers, ordered from "do this today" to "this is genuinely nitty-gritty":

- **00 · ROOT ACCESS** — the critical path (password manager, MFA, updates, disk encryption, backups, router defaults, credit freeze, recovery codes)
- **01 · PERIMETER** — hardware keys, login alerts, email separation, OAuth audits, Wi-Fi hardening, VPN, breach monitoring
- **02 · DEEP FIELD** — DNS, tracker blocking, email aliases, social privacy, data brokers, encrypted messaging, firewalls
- **03 · GHOST PROTOCOL** — key rotation, canary tokens, isolated browsing, self-hosted vaults, hardware SSH keys, VLANs, GPG, air-gapped backups

Each item expands (click the **+**) to explain *why* it matters, not just what to do.

## How state works

- **Checkbox progress** is saved in `localStorage`, per browser. Anyone who opens the link gets their own blank run — nothing is shared or synced between viewers by default.
- **The visit counter** tries to use a shared backend store (Claude's `db` artifact capability) for a real cross-visitor count; if that's unavailable to a given viewer (e.g. they're outside the artifact owner's org), it falls back to a local per-browser tally, labeled accordingly.

## Easter eggs

Told, not hidden — per request:

1. **The mini terminal** (bottom-right `>_` button) — type `help` for the full command list (`whoami`, `rank`, `progress`, `achievements`, `matrix`, `neo`, `sudo`, `credits`, `clear`, `exit`).
2. **Konami code** — ↑ ↑ ↓ ↓ ← → ← → B A anywhere on the page triggers a full-screen matrix flash and an achievement.
3. **Logo click** — click the `GHOST_PROTOCOL` logo top-left 5 times quickly to pop a hidden credits panel.
4. **The hidden pixel** — a barely-visible dot in the footer next to the version number. Click it for a "bug bounty" achievement.
5. **"Touch grass"** — the last item in tier 03 is only half a joke; checking it triggers its own reaction.
6. **`matrix` / `neo` terminal commands** — one flashes a full-screen matrix takeover, the other flips an "invert" mode.
7. **The browser console** — open devtools on the page for an ASCII-styled greeting most visitors will never see.
8. **100% completion** — clearing all 41 items triggers a full-screen "DIGITAL GHOST / FULL CLEARANCE" celebration with a particle burst.
9. **Achievements** — tracked quietly per browser: first check, each tier cleared, 3 easter eggs found ("EASTER HUNTER"), and full clearance.

## Tech

Single HTML file. No build step, no dependencies beyond a Google Fonts import (Orbitron + JetBrains Mono). Matrix rain is a `<canvas>` loop; everything else is vanilla CSS/JS.

- `index.html` — the whole site.

## Running it locally

Just open `index.html` in a browser. No server required.

---
Built by Claude, for Audra.
