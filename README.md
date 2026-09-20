# FingerFuel

Offline typing tests in the style of Monkeytype, made for old PCs. Each app is **one HTML file**. There is nothing to install, no internet is needed, and there are no libraries or servers.

| File | What it is | Runs on |
|---|---|---|
| [`FingerFuel.html`](FingerFuel.html) | Full typing test | Chrome 49+, Firefox 31+, current Edge, including Windows 7 with Chrome 109 |
| [`FingerFuel-Lite.html`](FingerFuel-Lite.html) | The same idea, simplified for very old browsers | Internet Explorer 8 and newer, plus everything above |

Not sure which one to use? Open `FingerFuel.html` first. If the page does not load or looks broken, use `FingerFuel-Lite.html`.

Author: [github.com/animeshmahat](https://github.com/animeshmahat)

---

## Quick start

1. Copy the `.html` file to the computer (a USB stick is fine).
2. Double-click the file. It opens in the default browser.
3. Optional: right-click the file and choose *Send to > Desktop (create shortcut)*.

For a clean window without browser tabs, create a Chrome shortcut whose target ends with:

```
--app=file:///C:/Path/To/FingerFuel.html
```

> **Tip:** browsers store scores and settings per browser *and per file location*. Keep the file at the same path every time so your results stay together.

---

## Features

| | FingerFuel | FingerFuel Lite |
|---|:---:|:---:|
| Time mode (15, 30, 60, 120 seconds) | Yes | Yes |
| Words mode (10, 25, 50, 100 words) | Yes | Yes |
| Notes mode (34 notes, 7 topics) | Yes | Yes |
| Custom text | Yes | - |
| Punctuation and numbers options | Yes | - |
| WPM, accuracy, raw speed, character breakdown | Yes | Yes |
| Consistency and speed-over-time chart | Yes | - |
| Chalkboard, Paper and High contrast themes | Yes | - |
| High scores with player name | Yes | Yes |
| Caps Lock and keyboard-layout warnings | Yes | Yes |
| Layout that adapts down to phone-size windows | Yes | Yes |

Lite leaves out the chart, themes, punctuation and numbers, and custom text because they need features that old Internet Explorer does not have.

### Modes

- **time**: type as much as you can before the timer ends.
- **words**: type a fixed number of words. Words are picked at random from a list of 198 common English words.
- **notes**: type short computer notes and read them again after the result (see below).
- **custom text** (full version): paste any passage; the test ends at the last word.

**Punctuation** and **numbers** (full version) can be switched on in time and words modes.

### Notes mode

34 short notes in seven topics: Basics, Hardware, Software, Internet and safety, Office tools, Logic and coding, Typing and health. Every note is shown once, in random order, before any repeats. After the result, the note is shown again for reading. Pick a topic from the drop-down or use *All topics*.

### Results

Both versions show WPM, accuracy, raw speed, a character breakdown (correct / wrong / extra / missed), time and the test setup. The full version also shows consistency and a speed-over-time chart.

### Players and high scores

- The best score for each test setup is saved on the computer.
- A name is asked for **only after a new high score**. The name is always shown at the top right ("guest" until set); click it to change it.
- The **scores** button lists the record for every test, with player and date. *Clear all scores* needs a second click to confirm.

### Look (full version)

Chalkboard, Paper and High contrast themes. The layout adapts from large monitors down to phone-size windows, and the text box always shows exactly three lines.

---

## Keys

| Key | Action |
|---|---|
| `Tab` | New test |
| `Esc` | Same words again |
| `Backspace` | Delete a letter (in the full version it steps back into the previous word when the current one is empty) |
| `Ctrl` + `Backspace` | Delete the whole word (`Alt` or `Cmd` also work) |

Warnings appear for Caps Lock and for a non-English keyboard layout (for example Nepali). Press `Alt + Shift` or `Windows + Space` to switch to English.

---

## Adding your own notes

Both files have a `NOTES` list near the top of the script. Open the file in a text editor, copy a line and edit it:

```js
["Topic", "Title", "Text to type"],
```

Use the same topic names to keep notes grouped. Use plain English letters and normal punctuation. If you add a new topic name, also add it to the `NOTE_CATS` list just above `NOTES` so it appears in the drop-down.

---

## Notes for very old browsers (Lite)

- Written in plain old JavaScript so it runs in **Internet Explorer 8 and newer**, for example on Windows XP or 7 machines that only have IE.
- IE may show a yellow bar saying it "restricted this webpage from running scripts". Click it once and choose *Allow blocked content*.
- IE8 and IE9 do not normally save data for pages opened from a file. Lite tries `localStorage` first, then IE's own `userData` storage, and if neither works, scores last only until the window is closed. Test this once on each type of machine: set a score, close the browser, reopen the file.
- Internet Explorer 7 and older, and IE running in compatibility view, are not supported.

---

## Where data is stored

Everything stays in the browser on that computer. Nothing is sent anywhere. Clearing the browser's site data removes it.

| Data | FingerFuel (`localStorage`) | Lite |
|---|---|---|
| Settings | `fingerfuel.settings` | `ff_settings` |
| High scores | `fingerfuel.best` | `ff_best` |
| Player name | `fingerfuel.player` | `ff_player` |

The two versions keep separate data, so scores from one do not appear in the other.

---

## Troubleshooting

| Problem | What to do |
|---|---|
| Test does not react to keys | Click once on the page so it has focus. |
| Wrong letters appear | The keyboard layout is not English. Press `Alt + Shift`. |
| Page does not load or looks broken | Use `FingerFuel-Lite.html`. |
| Yellow bar in Internet Explorer | Click it and choose *Allow blocked content*. |
| Scores disappear after closing the browser | The browser is not allowing storage for local files (mainly IE8 and IE9). Scores then last only for that session. |

---

## How it was tested

- Driven in a real browser with real keystrokes and mouse actions, at window sizes from 2560x1440 down to 320x480, checking that nothing overflows or scrolls.
- The code uses no modern-only features, and was also run with those features switched off to imitate old browsers.
- Not yet tested on a physical Windows 7 or Internet Explorer machine, so please try each file on your oldest PC first.

---

## License

Released under the [MIT License](LICENSE). Copyright (c) 2026 Animesh Mahat.

You are free to use, copy, modify and share this app as long as the copyright notice and license text are kept.
