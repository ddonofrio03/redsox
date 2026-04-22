# ⚾ Boston Red Sox Live Scoreboard

A real-time Red Sox game tracker powered by the **official MLB Stats API** — no API key, no cost, no dependencies.

## Features

- 🔴 **Live score** with inning-by-inning breakdown (R/H/E)
- ⚾ **Current pitcher** — IP, K, BB, H, pitch count
- 🏏 **Batter at the plate** — H-AB, RBI, R, K, BB
- 🔵 **Count display** — balls, strikes, outs (visual dots)
- 🔴 **Diamond bases** — highlights occupied bases in red
- 📊 **Full batting box score** for both teams
- 📋 **Pitching lines** for both teams
- 🕐 **Auto-refreshes every 30 seconds**
- 📅 **Scheduled game info** when no game is in progress
- 🔜 **Next game lookup** on off days

## API

Uses MLB's official public REST API — **free, no key required**:

| Endpoint | Purpose |
|---|---|
| `statsapi.mlb.com/api/v1/schedule` | Today's Red Sox game, status, probable pitchers |
| `statsapi.mlb.com/api/v1.1/game/{gamePk}/feed/live` | Live feed: count, bases, matchup, box score |

## Usage

Open `index.html` directly in a browser. For best results (to avoid CORS issues), serve it from a local web server:

```bash
# Python
python3 -m http.server 8080

# Node
npx serve .
```

Then visit `http://localhost:8080`.

## Deploy to GitHub Pages

1. Go to **Settings → Pages**
2. Source: **Deploy from branch → main → / (root)**
3. Your scoreboard will be live at `https://<username>.github.io/redsox/`

## Colors

| Color | Hex |
|---|---|
| Red Sox Navy | `#0C2340` |
| Red Sox Red | `#BD3039` |
| Red Sox Silver | `#556677` |

## Notes

- CORS proxy (`corsproxy.io`) is used for browser requests to MLB API. Falls back to direct fetch.
- MLB Stats API is for personal, non-commercial use. See MLB copyright notice.
- Live count (balls/strikes) updates on 30-second polling — not pitch-by-pitch.
