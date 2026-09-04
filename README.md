# Division Flash Cards

A simple, offline-friendly web app for practicing division facts (1–12). Students pick a divisor or group, answer on a keypad or by **voice**, and track progress per set.

Open [`division-flashcards.html`](./division-flashcards.html) in a modern browser—no build step or server required (see [Voice input](#voice-input) for mic notes).

## Features

- **Individual sets** — practice ÷1 through ÷12
- **Groups** — 2–5, 6–8, 9–12, or All (1–12)
- **Whole-number only** — every problem is exact (no remainders); answers are 1–12
- **Keypad + keyboard** — tap digits or type `0–9`, `Backspace`, `Enter`
- **Voice answers** — tap the mic and say the number (e.g. “six” or “12”)
- **Progress tracking** — saved in the browser (`localStorage`), per divisor
- **Session results** — score and percent at the end of each run
- **Options** — randomize order, double the deck, reset all progress

## How to use

1. Open `division-flashcards.html` in Chrome, Edge, or Safari.
2. Choose a blue set button (÷3, 2–5, All, etc.).
3. Solve each card with the keypad, keyboard, or mic.
4. Buttons turn **green** when that set reaches **100%** correct over time.
5. Use **Reset all progress** on the home screen to clear saved stats.

Progress is stored locally under the key `divFlashProgress` and stays on that device/browser.

## Voice input

- Shown only when the browser supports the Web Speech API (Chrome, Edge, Safari).
- Tap **🎤**, allow microphone access if prompted, then say the answer.
- The number is filled in and submitted automatically after a short pause.
- Tap again while listening to cancel.

**Note:** Speech recognition usually needs **HTTPS** or **localhost**. Opening the file as `file://` may block the mic in some browsers. For local testing, serve the folder briefly, e.g.:

```bash
npx serve .
# or
python3 -m http.server 8080
```

## Options (home screen)

| Option | Effect |
|--------|--------|
| **Randomize flash cards** | Shuffle the deck each session (on by default) |
| **Double the number of cards** | Play each fact twice in one session |
| **Reset all progress** | Clears saved correct/total counts for all divisors |

## Technical notes

- Single HTML file: React 18 + Babel via CDN (no install or bundler).
- Styling is self-contained CSS (dark theme).
- Progress buttons: blue by default, green at 100%; percentage sits in a nested bar that fills with practice.
- Demo mode: add `?demo=1` to the URL to auto-start a short ÷3 session.

## Browser support

| Feature | Chrome | Edge | Safari | Firefox |
|---------|--------|------|--------|---------|
| Core practice / keypad | ✅ | ✅ | ✅ | ✅ |
| Progress (localStorage) | ✅ | ✅ | ✅ | ✅ |
| Voice input | ✅ | ✅ | ✅ | ❌ |

## License

Use and adapt freely for classroom or personal study.
