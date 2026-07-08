# Session — OneFile born (2026-07-07)

**Branch:** master · **Commits:** 2

| Commit | Summary |
|---|---|
| 1 | OneFile: your life in a single file you own (v1 — capture/threads/timeline, localStorage, export/import, 0-network badge, a11y/dark/mobile) |
| 2 | On-device encryption: AES-256-GCM passphrase lock + sealed `.onefile` export |

**Files:** `index.html` (self-contained app), `README.md` (ELI5), `LICENSE` (MIT).

**Live:** https://lifeatlas.github.io/onefile/ (GitHub Pages, master, `/`).

## What it is
A single HTML file = a private, offline, local-first notebook. No account, no server, no tracking. Data stays on-device; optional passphrase encryption (Web Crypto: PBKDF2 250k → AES-256-GCM) with sealed `.onefile` backups. A live badge proves zero network requests.

## Verification
- JS syntax checked (`node --check`).
- In-browser (Playwright): entry capture → encrypt → reload → lock screen → wrong pass rejected → correct pass restores. Storage confirmed ciphertext-only (plaintext secret absent).
- Both builds confirmed on live Pages (HTTP 200 + grep of live bundle).

## Open items
- [ ] PWA "Add to Home Screen" (offline install)
- [ ] Reflection prompts, offline health charts, markdown/CSV import
- [ ] Decide Life Atlas framing: sovereignty demo / local-first seed / free-tier lead magnet
