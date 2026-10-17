# Ghost Protocol

Part of Astra's Pet Apps. Public credit: Astra.

Keep existing product behavior and source intact. The pet interface is ghost-protocol-20261008.html; metadata is pet.json. Never commit credentials, personal health or finance data, local settings, caches, or logs. Imported or user-entered text must be rendered as text, not HTML. State integration limits plainly. New filenames use lowercase words and a date immediately before the extension.

Pet interface and art integration: OpenAI Codex (GPT-6), 2026-10-08.

Desktop artwork and size sync: OpenAI Codex (GPT-6), 2026-10-11. Read desktop-pet-20261011.json. No sparkles. Keep draft and approved design status explicit.

Desktop appearance revision by OpenAI Codex (GPT-6), 2026-10-11. See desktop-pet-20261011.json; runtime behavior is in astras-pet-apps.

Checklist text escaping (typed and AI-suggested items; links kept to http and https and fully escaped): Claude Opus 5.5, 2026-10-17. Finding 6 in findastra/astras-pet-os docs/security-assessment-20261016.md; regression test there: test/ghost-protocol-escape-test-20261017.mjs (ghost-protocol-20261008.html is byte-identical to that repo's copy).
