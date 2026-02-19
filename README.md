# Ivan But — Full Stack Engineer Portfolio

> Personal portfolio website · Single-file HTML · No build tools · €100/hr

---

## 🌍 Live Preview

Open `portfolio.html` in any browser. That's it.

---

## 📁 File Structure

```
.
├── portfolio.html     ← The entire site (HTML + CSS + JS in one file)
├── README.md          ← This file (English)
└── README.ru.md       ← Russian version
```

There are intentionally **no dependencies**, no `package.json`, no `node_modules`.
Everything — styles, animations, layout — lives in one file.

---

## 🧱 Site Sections

| Section | ID / Class | Description |
|---|---|---|
| Navigation | `<nav>` | Fixed top bar with links + availability status |
| Hero | `.hero` | Full-screen intro with animated text |
| Stats Bar | `.stats-bar` | 4 key numbers (animated counters) |
| Tech Stack | `#stack` | 6 category cards with technology tags |
| Projects | `#projects` | 4 project cards with descriptions + tech |
| Experience | `#experience` | Career timeline with achievements |
| Contact | `#contact` | CTA with email, LinkedIn, GitHub |
| Footer | `<footer>` | Copyright + open-to-work signal |

---

## 🎨 Design System

### Colors (CSS Variables in `:root`)

| Variable | Value | Usage |
|---|---|---|
| `--bg` | `#080810` | Main dark background |
| `--surface` | `#0e0e1a` | Card / section backgrounds |
| `--accent` | `#00ff88` | Green highlight — primary accent |
| `--text` | `#e8e8f0` | Main body text |
| `--muted` | `#6b6b85` | Secondary / hint text |
| `--border` | `rgba(255,255,255,0.07)` | Subtle divider lines |
| `--glow` | `0 0 40px rgba(0,255,136,0.15)` | Green glow shadow |

To change the accent color globally — update only `--accent`.

### Typography

| Font | Usage | Weights |
|---|---|---|
| **Syne** | Headings, logo, titles | 400, 700, 800 |
| **DM Mono** | Body text, tags, labels | 400, 500 (italic) |

Loaded from Google Fonts. Requires internet connection on first load (cached after).

---

## ⚙️ JavaScript Features

### 1. Custom Cursor
Two-layer cursor:
- **Dot** (`.cursor`) — snaps to mouse instantly
- **Ring** (`.cursor-ring`) — follows with a smooth lag using **lerp interpolation**

Lerp formula: `pos = pos + (target - pos) * 0.12`

On hover over links/cards → cursor expands.

### 2. Scroll Reveal
All elements with class `.reveal` start invisible (`opacity: 0`, `translateY: 20px`).

`IntersectionObserver` watches them. When an element enters the viewport (10% visible), the class `.visible` is added → CSS transition kicks in.

Staggered: each element in a batch gets `+60ms` delay for a cascade effect.

### 3. Animated Counters
Stats (7+, 40+, 12M, €100) count up from zero when the stats bar enters view.

Uses **easeOutCubic** timing: `eased = 1 - (1 - progress)³`
Fast at the start, slows at the end — feels natural.

---

## ✏️ How to Customize

Search the HTML file for comments marked **`CHANGE ME`** — they mark every piece of personal data.

### Quick checklist:

- [ ] `<title>` tag — page title in browser tab
- [ ] `.nav-logo` — your initials (e.g. `IB/`)
- [ ] `.hero-title` — your first and last name
- [ ] `.hero-desc` — your personal pitch (2–3 sentences)
- [ ] `.hero-label` — tagline + rate
- [ ] Stats values in JS `values[]` array + HTML
- [ ] Stack cards — add/remove technology tags
- [ ] Project cards — replace with your real projects
- [ ] Timeline items — your real job history
- [ ] Contact links — `href="mailto:..."`, LinkedIn URL, GitHub URL
- [ ] Footer copyright — your name + year

---

## 🎯 Performance Notes

- **No JavaScript frameworks** — vanilla JS only
- **No external CSS** — everything is inline in `<style>`
- **Google Fonts** — only 2 fonts, loaded async with `display=swap`
- **CSS animations** — GPU-accelerated (`transform`, `opacity`)
- **IntersectionObserver** — lazy evaluation, stops after first trigger (`unobserve`)
- **requestAnimationFrame** — smooth 60fps cursor and counter animations

---

## 📱 Responsive Behavior

| Breakpoint | Changes |
|---|---|
| `> 768px` | Full layout — all columns, nav links visible |
| `≤ 768px` | Nav links hidden, 2-column stats, reduced padding |

> **TODO:** Add hamburger menu for mobile nav.

---

## 🌐 Browser Support

Works in all modern browsers:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

> Note: `backdrop-filter: blur()` not supported in Firefox < 103.
> The nav will still work, just without the blur effect.

---

## 📄 License

Free to use, modify, and deploy for personal portfolio use.
Attribution appreciated but not required.

---

## 👤 Author

**Ivan But** — Full Stack Engineer
- 📧 w3st.hd@gmail.com
- 💼 [LinkedIn](https://linkedin.com/in/ivanBut)
- 🐙 [GitHub](https://github.com/sh3vhd)
- 💰 Rate: €100/hour · Remote-first · Available now
