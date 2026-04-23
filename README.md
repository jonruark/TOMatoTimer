# 🍅 TOMatoTimer

A sleek, single-file Pomodoro timer that runs entirely in your browser — no install, no dependencies, no server required. Just open the HTML file and focus.

![TOMatoTimer screenshot](screenshot.png)

---

## Features

**Classic Pomodoro intervals**
- 25-minute focus sessions
- 5-minute short breaks
- 15-minute long breaks
- Auto-advances to the next session and tracks your progress with 4 session dots

**Four clock styles**
- **Block** — chunky, rounded display (default)
- **Digital** — Orbitron sci-fi font
- **Retro** — VT323 pixel/terminal aesthetic
- **Flip** — animated CSS 3D flip clock with split-card mechanics and screw-head details

**Four clock sizes**
- S, M, L (default), XL — scales both the text display and flip cards together via CSS custom properties

**Live browser tab countdown** — the tab title updates every tick with the remaining time and a 🍅 / ☕ emoji so you always know where you are even when the tab is in the background

**Fully configurable alarms** — enable or disable any combination:
- 🔔 **Beep** — four-note Web Audio API tone, no internet required
- 🖥 **Desktop Notification** — system-level pop-up via the Notifications API
- ⚡ **Screen Flash** — white strobe overlay to grab your attention
- ▶ **YouTube** — opens any YouTube URL in a new tab when the timer ends; paste your own link (hype song, ambient stream, stretch video, etc.)

A **PREVIEW** button fires all enabled alarms on demand so you can test your setup before committing to a session.

---

## Usage

1. Download `pomodoro.html`
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari)
3. Click **START**

No build step. No npm. No framework. One file.

---

## Alarm Configuration

All alarm options are toggled from the bar at the bottom of the page. They persist for the duration of your browser session.

| Alarm | Notes |
|---|---|
| Beep | Uses the Web Audio API; works offline |
| Notification | Browser will prompt for permission on first enable |
| Screen Flash | White strobe, 4 pulses |
| YouTube | Paste any URL; opens in a new tab on session end |

The default YouTube link is set to a focus/work playlist. You can change it to anything — a celebratory song, a guided stretch, a Pomodoro-start ritual, whatever fits your workflow.

---

## Keyboard / Controls

| Control | Action |
|---|---|
| START / PAUSE / RESUME | Main center button |
| ⏭ (skip) | Jump to the next session immediately |
| ↺ (reset) | Restart the current session |
| NEW TIMER | Hard reset to the beginning of the current mode |

---

## Customizing Intervals

Open `pomodoro.html` in a text editor and find the `MODES` object near the top of the `<script>` block:

```javascript
const MODES = {
  work:  { label: 'Focus',       sec: 25*60, ... },
  short: { label: 'Short Break', sec:  5*60, ... },
  long:  { label: 'Long Break',  sec: 15*60, ... },
};
```

Change the `sec` values to whatever intervals suit you.

---

## Customizing the Default YouTube URL

Find this line in the `<script>` block and replace the URL:

```javascript
value="https://www.youtube.com/watch?v=2yJgwwDcgV8"
```

---

## Browser Compatibility

Tested and working in all modern evergreen browsers. Requires:
- Web Audio API (beep)
- Notifications API (desktop notification)
- CSS 3D transforms (flip clock)
- `requestAnimationFrame` (smooth countdown)

All features degrade gracefully if an API is unavailable or permission is denied.

---

## File Structure

```
pomodoro.html   — the entire app; HTML, CSS, and JS in one file
README.md       — this file
```

---

## License

MIT — do whatever you want with it.
