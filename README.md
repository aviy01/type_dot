# TYPE.

A fast, minimal, single-file typing test — built for people who just want to type, see honest numbers, and get out.

![mode: words](https://img.shields.io/badge/mode-words-e2564f) ![mode: paragraph](https://img.shields.io/badge/mode-paragraph-e2564f) ![mode: numbers](https://img.shields.io/badge/mode-numbers-e2564f) ![mode: pangram](https://img.shields.io/badge/mode-pangram-e2564f)

---
<https://typingdot.vercel.app/>

## Why TYPE.

Most typing tests are one trick with a paint job. TYPE. is one file — no build step, no backend, no account — that covers four genuinely different practice modes, gives tactile feedback while you type, and tells you *exactly* what to fix afterward instead of just handing you a number.

## Features

- **Four distinct modes**, not four themes on the same word list
  - **Words** — common high-frequency English words, shuffled continuously
  - **Paragraph** — connected, readable sentences instead of disjointed words, so you practice real rhythm and punctuation, not just isolated keystrokes
  - **Numbers** — numeric strings, for people who actually need numpad/number-row speed (data entry, dev work, finance)
  - **Pangram** — a curated pool of pangram-style vocabulary drawn so that, over a session, every letter of the alphabet gets used a **roughly equal number of times** — deliberate, evenly-distributed letter practice rather than the natural bias toward common letters like E and T that every other word-based test has
- **Adjustable duration** from 15 seconds up to 5 minutes, with a live-updating slider
- **Live HUD** — time remaining, WPM, and accuracy update as you type, not just at the end
- **Detailed results screen** — WPM, accuracy, correct/total characters, and total mistypes
- **Mistyped-character breakdown** — a ranked list of exactly which characters tripped you up and how often, so you know what to drill next instead of just "you got 94%"
- **Tactile audio feedback** — a subtle click on every keystroke and interaction, with a full volume slider and mute toggle (built on the Web Audio API with an `<audio>` fallback, so it stays responsive even with rapid, overlapping keystrokes)
- **Zero setup** — a single self-contained HTML file. No npm install, no server, no tracking, no login. Open it and type.

## What makes it different from other typing tests

| | Typical typing test | TYPE. |
|---|---|---|
| Word selection | Random common words only | Words, connected paragraphs, numbers, **and** a letter-balanced pangram mode |
| Letter coverage | Naturally skewed toward frequent letters (e, t, a, o...) | Pangram mode actively balances letter exposure across the alphabet |
| Feedback after a test | A score and maybe a graph | A ranked breakdown of your actual mistyped characters |
| Feedback while typing | Numbers appear only at the end, or update in a detached panel | Timer, WPM, and accuracy update live in the HUD as you go |
| Sound | None, or a generic system beep | A tuned click with its own volume control, mixed in-page |
| Setup | Account, ads, or a web app shell | One HTML file, works offline, no dependencies |

## Getting started

1. Download `typing-test.html`
2. Open it in any modern browser
3. Click into the text area (or just start typing) to begin
4. Pick a mode and duration from the controls bar before you start, if you want something other than the default

No installation, no build tools, no server required.

## Tech notes

- Pure HTML/CSS/JS — no frameworks, no external runtime dependencies (only a Google Font is loaded over the network)
- Audio is decoded once into a reusable buffer via the Web Audio API for low-latency, overlapping click sounds, with a pooled `<audio>` element fallback for environments where Web Audio isn't available
- Fully keyboard-driven; the visible text area is decorative, real input is captured through a hidden input field for reliable cross-device typing (including mobile)

## Customize

Everything — word lists, colors, timing options, sound — lives in this one file, so it's easy to fork: swap the `WORDS`, `PARAGRAPH_FRAGMENTS`, or `PANGRAM_WORDS` arrays for your own content, or restyle it entirely via the CSS custom properties defined at the top of the file (`--accent`, `--paper`, `--bg-1`, etc.).

---

*Built for people who'd rather practice typing than configure a typing test.*
