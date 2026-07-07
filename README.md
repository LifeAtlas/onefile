# OneFile

**Your life in a single file you own — forever.**

No account. No cloud. No tracking. Open one page in your browser, write down what matters, and it *never leaves your device*. There's even a little badge in the corner that stays green because OneFile contacts **zero servers, ever**.

👉 **[Open it](https://lifeatlas.github.io/onefile/)** (or download `index.html` and double-click it — it works with no internet at all).

---

## Explain it like I'm 5

Imagine a notebook that:

- lives on **your** desk, not someone else's,
- nobody can read but you,
- still works if the internet dies,
- and you can pick up and carry away whenever you want.

That's OneFile. It's one web page. You type notes, decisions, people, health stuff, small wins. It remembers them on your device. When you want a backup, it hands you **one plain file** you keep forever — readable without any app, on any computer, for the rest of your life.

## Why it exists

Most apps keep your life on *their* computers. If they get bought, hacked, or shut down, your memories go with them. OneFile flips that: **your data starts on your device and stays there.** Privacy isn't a promise buried in a policy — it's the design. If you can open the file, you own it.

## What you can do

- **Capture** — a note, a decision, a person, a health metric, a win. Tag it.
- **Threads** — tags become threads you follow over time (`#health`, `#family`, a project).
- **Timeline** — search everything, newest first.
- **Back up / Restore** — export a `.json` file that's yours; import it on any device.
- **Print / Save as PDF** — a paper copy in one click.
- **Erase everything** — one button, gone, no trace anywhere.

## The promise (and the proof)

OneFile makes **no network requests**. It doesn't load fonts, scripts, or images from anywhere — everything is inside `index.html`. The green badge in the corner watches `fetch`/`XHR` and would turn into a loud warning if anything ever tried to phone home. It never does.

- 🔒 100% offline-capable
- 📄 One file — no build step, no dependencies, no framework
- 🧳 Zero lock-in — your backup is plain, human-readable JSON
- ♿ Keyboard-navigable, dark/light, mobile-first, works at 375px
- ⚖️ MIT licensed

## Run it yourself

```bash
# it's literally one file
open index.html      # macOS
start index.html     # Windows
xdg-open index.html  # Linux
```

No server needed. To host it (like the link above), any static host works — GitHub Pages, Netlify, or a USB stick.

## Roadmap

- [x] Optional on-device encryption — passphrase-locked with **AES-256-GCM + PBKDF2** (250k iterations). No reset, no backdoor: if you forget it, the data stays sealed.
- [x] Encrypted export — sealed `.onefile` backup you can carry between devices and open only with the passphrase.
- [ ] Daily/weekly reflection prompts
- [ ] Simple charts for health metrics (still 100% offline)
- [ ] Import from plain markdown / CSV
- [ ] PWA install ("Add to Home Screen") so it feels like a native app — still no server

### Security notes

- Encryption uses the browser's built-in [Web Crypto API](https://developer.mozilla.org/docs/Web/API/Web_Crypto_API) — no third-party crypto libraries.
- Your passphrase is **never stored and never transmitted**; it only derives a key in memory while the file is open.
- Encryption requires a secure context (https or localhost). Over `file://`, some browsers disable Web Crypto — the app tells you and stays unencrypted rather than pretending.

---

*Built as a small proof of a big idea: sovereignty is architecture, not policy. Part of the [Life Atlas](https://github.com/LifeAtlas) worldview — you, in control.*
