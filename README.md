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

Right under the exposure meter, a small note points out that the AI chat in the bottom-right corner (`>_`) can explain any item in plain language or help figure out what to add for your own setup — in case that isn't obvious from the terminal button alone.

## Customize each tier

Every tier can be reshaped to fit your actual life. Click **"Customize this list"** right under a tier's header to reveal:

- **+ Add item** — add your own item to that tier: title, optional one-line note, optional detail, and an optional link — for anything specific to you (a particular account, device, or habit) that isn't already covered. A bare domain or URL without `http(s)://` is normalized automatically, and the item's expanded detail gets an "Open link ↗" button that opens it in a new tab.
- **✦ AI suggest** — asks the AI chat to propose several new, non-duplicate items for that tier — often broken out per-account (e.g. one item each for your email, bank, work SSO, socials) — and lets you pick which ones to actually add. Needs the live AI-connected version of the page.
- **N hidden** — restores anything you've hidden.

**×** on any item (built-in or one you added yourself) hides it from view — nothing is ever deleted, it "remains" in your saved data and comes back from the hidden list above. Each item's expanded detail also has its own **"+ add a related item"** link, so you can add something specific to that exact item (like a particular account) without hunting for the tier-wide controls.

Hiding or adding items changes what counts toward your percentage and rank — hide something that doesn't apply to you and it stops being held against your score; add something and it becomes part of your checklist, same as anything built in.

## Each item as a worksheet

Expand any of the 41 built-in items and, below the "why it matters" explanation, you'll find:

- **Step-by-step** — the same guidance, but broken into an explicit numbered checklist with its own small checkboxes. Each step is tracked separately from the main item checkbox, remembered per browser, with a running "N/M done" counter.
- **Resources** — direct links to the specific tools/sites that step mentions, pulled out into their own list instead of buried mid-paragraph.
- **Verify below** — on the handful of items a browser can actually check live (mainly the VPN item, tracker-blocking, DNS, Wi-Fi hardening, and automatic updates), a row of pill buttons that jump straight down to the matching widget(s) in the "What This Page Can See About You" panel and flash them. Every other item honestly says "No live browser check for this one — it stays on the honor system," rather than pretending a webpage can verify things like whether you actually use a password manager.

## AI chat

The bottom-right terminal (`>_`) doubles as a chat assistant — ask it anything about the checklist or security in general and it'll answer in-terminal. It runs on Claude's built-in Artifact chat capability (no API key, no separate backend, no meaningful token cost), so it only works on the live Artifact-hosted version, not a plain static copy of `index.html`. If it's unavailable in a given viewer's context, the terminal quietly falls back to its fixed command set.

## Sound

Small synthesized sound effects (checkbox ticks, achievement chimes, terminal blips) via the Web Audio API — no audio files. Muted by default is off; toggle with the speaker icon in the top HUD. The setting is remembered per browser. Checking an item off also pairs its tick sound with a small burst of 0/1 particles right at the checkbox.

## Background music

A small "MUSIC" pill next to the sound toggle plays a queue of eight instrumental tracks (about 100 seconds total), one after another, then stops — no loop. Every track is an **original, synthesized placeholder** (built the same way as the sound effects above, with plain oscillators — no audio files, no samples), each one just standing in for the mood of a song mentioned in conversation rather than being that actual recording; this page can't legally embed real copyrighted audio, and a published Claude Artifact's content policy blocks loading external audio files anyway. Each track layers a lead melody with a steady low bass pulse and, on the more upbeat tracks, a small synthesized drum thump, so it reads more like a short arrangement than a single bare tone. Click the speaker icon to mute/unmute, and use **−** / **+** to adjust volume in 10% steps (0–100%). Browsers block autoplay-with-sound until you interact with the page, so the playlist starts on your first click, key press, or tap anywhere on the page (or immediately when you unmute, if it hasn't started yet). Your mute state and volume are remembered per browser.

This feature is intentionally self-contained and easy to remove: it's all inside three blocks marked `BACKGROUND MUSIC CONTROLS` (CSS and HTML) and `BACKGROUND MUSIC — PLACEHOLDER TRACKS` (JS), uses its own `localStorage` key, and touches nothing else in the site. To turn it off without deleting anything, set `MUSIC_ENABLED = false` near the top of that JS block. To remove it entirely, delete those three marked blocks.

## What This Page Can See About You

Near the bottom of the page, above the footer, a live readout panel shows 39 real, verifiable things an ordinary website can detect about a visitor — no login, no special permissions, nothing exotic. It's grouped into three sections:

- **Network & location** — your public IP, approximate city/region/country and ISP (via a third-party IP-geolocation lookup your browser makes directly), your IP-derived timezone vs. your browser's actual timezone (a mismatch is a classic, though not certain, VPN/proxy signal), connection type, online status, a network speed estimate, and a WebRTC IP-leak check (WebRTC can expose your real IP even through a VPN that otherwise hides it).
- **Device & browser** — browser and OS, device type, screen and viewport size, pixel ratio, color depth, CPU core count, approximate device memory, GPU renderer string, touch support, battery level where exposed, a canvas-fingerprint hash, color gamut/HDR support, screen orientation, reported plugin count, and built-in PDF viewer support.
- **Privacy signals** — language, dark/light mode preference, reduced-motion preference, Do Not Track, Global Privacy Control (a newer, legally-backed alternative to Do Not Track), cookies, local storage, HTTPS status, the referrer sent to this page, and a heuristic ad/tracker-blocker check (a bait element styled like an ad — if something hides it, you're running a blocker).

Click any widget to expand it in place: every one explains **exactly how the check works** under the hood, and where a browser can genuinely do something about it, an explicit numbered "how to reduce it" list with its own small checkboxes — same worksheet pattern as the checklist items above. Widgets that are just a status flag (online status, viewport size, color depth) say so plainly instead of inventing steps to block something that isn't really a privacy concern.

This is intentionally framed as privacy education, not a pass/fail audit — most of the 41 checklist items above genuinely can't be verified by a webpage (there's no way for a page to check whether you actually use a password manager). What's shown here is exactly what a webpage *can* check, so the exposure feels concrete rather than abstract. If your browser or an extension blocks the IP lookup, the panel says so plainly — that's itself a sign the block is working.

**Is 39 widgets "enough"?** Pretty close to as far as this idea sensibly goes — it now covers every category a plain webpage can genuinely check: your network/location, your exact hardware and rendering fingerprint (including the classic canvas-fingerprint and WebRTC-leak tricks trackers actually use), and every real browser-exposed privacy signal, including the newer Global Privacy Control alongside the older Do Not Track. Going meaningfully further would mean padding with near-duplicate or purely trivial signals rather than anything new — so this is treated as the practical ceiling unless something genuinely different comes to mind.

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
8. **The white rabbit** — every so often, a small, compact always-white pixel rabbit (side-on, ears back, one eye, a little cottontail) appears at the bottom of the screen, holds still for a beat, then leaps left to right in a handful of big, choppy hops rather than a smooth run — it snaps to each new spot the instant the frame changes and holds still through the rest of that hop's pose, the way an old 8-bit sprite actually moved (no sliding, no rotation, no squash-and-stretch). Sometimes, instead of crossing the bottom, it sneaks up to a hole in one of the title letters (the O's, A's, B's, D's, P's, Q's, and R's) and hides inside it for a moment before dashing back off the bottom of the screen. Click it before it escapes: the first catch turns the whole site red, the second turns it pink, and every catch after that shifts it to a new random neon color — and it explodes into a shower of 0s and 1s that also ripples outward through the matrix rain behind it, no popup needed. The color sticks around (saved per browser) until you catch it again.
9. **The browser console** — open devtools on the page for an ASCII-styled greeting most visitors will never see.
10. **100% completion** — clearing all 41 items triggers a full-screen "DIGITAL GHOST / FULL CLEARANCE" celebration: a burst of 0/1 particles, the theme cycling through every color, the matrix rain turning rainbow, and sparkles scattered across the whole screen — the final easter egg.
11. **Achievements** — tracked quietly per browser: first check, each tier cleared, 3 easter eggs found ("EASTER HUNTER"), and full clearance.

## Tech

Single HTML file. No build step, no dependencies beyond a Google Fonts import (Orbitron + JetBrains Mono). Matrix rain is a `<canvas>` loop; everything else is vanilla CSS/JS.

- `index.html` — the whole site.

## Running it locally

Just open `index.html` in a browser. No server required.

---
Built by Claude, for Astra.
