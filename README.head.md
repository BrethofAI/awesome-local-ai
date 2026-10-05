# awesome-local-ai

> Curated list of AI tools that run **100% on your machine** — no cloud, no telemetry, no "local-ish" setups that secretly phone home.

Maintained by [Brethof AI](https://brethof.ai). Companion to
[awesome-llms-txt](https://github.com/BrethofAI/awesome-llms-txt) and
[awesome-private-ai](https://github.com/BrethofAI/awesome-private-ai).

## Why this list exists

The phrase "local-first" has been stretched to mean almost anything in
2026. Lots of tools advertise on-device AI but then call out to remote
APIs for "complex" prompts, sync your data to a "private" cloud bucket,
or ship telemetry that re-introduces every privacy problem the local
mode was meant to solve.

This list applies a strict rule: **the tool must perform inference on
hardware you own and not transmit prompts, embeddings, or audio off
that hardware during normal use.** Optional cloud features (like model
download or update checks) are fine; mandatory ones disqualify.

Where a tool is partially-local (e.g. ships a fully-local mode but
defaults to cloud), we say so explicitly. Every link is checked — a
CI-style sweep cuts entries whose URL 404s.

## Inclusion rules

To be listed:

- It runs on the user's own hardware — inference on a CPU, GPU, NPU or
  local accelerator, or a component of a local AI stack (vector store,
  memory, embeddings, training).
- No mandatory account just to use it offline.
- Source code or signed binaries — verifiable provenance.
- A real artefact you can install today, not a "coming soon" page.

New or small is fine: we don't turn a tool away for being young or
little-known. Every entry is labelled honestly instead — 🆕 marks a
listing from the last 60 days — and our weekly check removes anything that
stops working or goes six months without a release, commit or merged PR.
We decline only tools with nothing real to point at, misleading claims,
or no local mode at all.

## Legend

- 🐧 Linux · 🪟 Windows · 🍎 macOS · 📱 iOS / Android · 🌐 Web (in-browser)
- 🔓 open source · 🔒 closed source
- 🆓 free for personal · 💰 paid · 🆓💰 free + paid tiers
- 🐍 Python · 🦀 Rust · 🐹 Go · ⚙️ C/C++ · 🟦 TypeScript / JS
- 🆕 new — listed in the last 60 days
