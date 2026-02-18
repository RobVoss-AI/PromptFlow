# VAIC PromptFlow

**The AI-powered teleprompter built for presenters, not broadcasters.**

PromptFlow is a professional teleprompter application built by [Voss AI Consulting](https://www.vossaiconsulting.com). It combines traditional script scrolling with voice tracking, WPM coaching, session analytics, and multi-window control — designed for speakers, educators, and content creators who present on camera or on stage.

Built as a Progressive Web App (PWA). Installable on iOS, Android, and desktop. Works offline. No account required.

![PromptFlow](icon-512.png)

---

## Features

### Script Management
- Create, save, edit, and organize multiple scripts
- Persistent storage via IndexedDB — scripts survive browser restarts
- Drag-and-drop file import (.txt files)
- Section markers for easy navigation within long scripts

### Teleprompter
- Smooth auto-scrolling with adjustable speed (1–100)
- Adjustable font size (20–120px)
- Mirror mode for glass teleprompter rigs
- Fullscreen mode for distraction-free presenting
- Countdown timer before starting
- Section jump panel for navigating during a session
- Focus line indicator showing your current reading position

### Voice Tracking
- Real-time speech recognition syncs scroll position to your voice
- Works alongside or instead of auto-scroll
- Detects when you go off-script

### WPM Coaching
- Live words-per-minute display during sessions
- Configurable target WPM with deviation alerts
- Visual pacing indicator (too fast / on target / too slow)
- WPM tracking over time for session analytics

### Session Reports
- Exportable text reports with session duration, average WPM, deviation count
- WPM-over-time data points
- Coaching notes based on your performance

### Multi-Window Control
- BroadcastChannel API allows controlling the prompter from a separate browser window
- Run the script on one screen while controlling from another
- Useful for dual-monitor setups and presentation rigs

### Keyboard Shortcuts
| Key | Action |
|---|---|
| `Space` | Play / Pause |
| `R` | Reset to beginning |
| `↑` / `↓` | Speed up / slow down |
| `+` / `-` | Increase / decrease font size |
| `M` | Toggle mirror mode |
| `F` | Toggle fullscreen |
| `V` | Toggle voice tracking |
| `S` | Open section jump panel |
| `C` | Start countdown |
| `?` | Show keyboard shortcuts |
| `Ctrl+R` | Start/stop recording |

---

## Install as an App

### Android
Visit the site in Chrome. Tap the install banner or use Menu → "Add to Home Screen."

### iOS
Visit the site in Safari. Tap Share → "Add to Home Screen."

### Desktop
Visit the site in Chrome or Edge. Click the install icon in the address bar.

Full-screen, no browser bar, offline support, automatic updates.

---

## Tech Stack

- **Pure HTML/CSS/JS** — zero dependencies, zero build step, single file
- **IndexedDB** — persistent script storage
- **Web Speech API** — voice tracking and recognition
- **BroadcastChannel API** — multi-window synchronization
- **Progressive Web App** — manifest, service worker, offline caching
- **Hosted on Vercel** — automatic deployments from this repo

---

## Project Structure

```
├── index.html        # Complete application (single file)
├── manifest.json     # PWA manifest (app name, icons, display mode)
├── sw.js             # Service worker for offline caching
├── vercel.json       # Vercel routing and header config
├── icon-192.png      # App icon (192x192)
├── icon-512.png      # App icon (512x512)
├── icon.svg          # Vector source icon
└── README.md
```

---

## Local Development

No build tools required. Open `index.html` in a browser.

Voice tracking requires HTTPS or localhost. For local testing:

```bash
npx serve .
```

---

## Deployment

This repo is connected to Vercel. Every push to `main` triggers an automatic production deployment.

To deploy manually:

```bash
npm i -g vercel
vercel --prod
```

---

## Browser Compatibility

| Feature | Chrome | Safari | Firefox | Edge |
|---|---|---|---|---|
| Core teleprompter | ✅ | ✅ | ✅ | ✅ |
| Voice tracking | ✅ | ✅* | ❌ | ✅ |
| PWA install | ✅ | ✅ | ❌ | ✅ |
| Multi-window sync | ✅ | ✅ | ✅ | ✅ |
| Fullscreen | ✅ | ✅ | ✅ | ✅ |

*Safari voice tracking requires user permission and may have limited continuous recognition.

---

## Use Cases

- **Zoom / Teams presentations** — read your script while presenting on camera
- **YouTube / podcast recording** — maintain natural delivery with script guidance
- **Conference talks** — run on a tablet or second monitor at the podium
- **Classroom lectures** — keep on track during recorded or live sessions
- **Client demos** — nail your pitch without memorizing every word

---

## Contributing

Contributions welcome. PromptFlow is a single-file application — all HTML, CSS, and JS live in `index.html`.

1. Fork this repo
2. Make your changes
3. Test locally with `npx serve .`
4. Submit a pull request

Follow the existing blue/gold design system (CSS variables in `:root`). Keep the zero-dependency philosophy — no npm packages, no build step.

---

## License

MIT License. Free to use, modify, and distribute.

---

## About

Built by [Dr. Rob Voss](https://www.robvoss.com) at **Voss AI Consulting**.

Rob is an Associate Professor of History at Northwest Missouri State University, OpenAI Academy fellow, and AI consultant who builds tools at the intersection of education and technology.

- **Web:** [vossaiconsulting.com](https://www.vossaiconsulting.com)
- **LinkedIn:** [Rob Voss](https://www.linkedin.com/in/ai-robvoss/)
- **Newsletter:** Smart Teaching Evolved
- **Also by VAIC:** [ScrollStop](https://github.com/RobVoss-AI/vaic-scrollstop) — Content optimizer for social media posts

*Transforming Potential into Performance with AI*
