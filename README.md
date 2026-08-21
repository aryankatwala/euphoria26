# Euphoria '26 — "The Night We Don't Talk"

Official website for **Euphoria '26**, the freshers' party.
A single-page, dependency-free site (HTML/CSS/JS only) built to host on **GitHub Pages**.

**Live sections:** Hero + countdown → About → Highlights → Menu → Aftermovie → Organizers → Venue (map + QR) → Footer.

## 🚀 Deploy on GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under "Build and deployment", set **Source: Deploy from a branch**, branch `main`, folder `/ (root)`.
4. Save — your site goes live at `https://<username>.github.io/<repo-name>/`.

No build step required — it's plain HTML/CSS/JS.

## 📁 Project structure

```
euphoria26/
├── index.html          → all page content & sections
├── css/style.css        → theme, layout, animations
├── js/script.js         → nav toggle, scroll header, countdown timer
├── img/
│   ├── organizers/      → organizer photos go here
│   ├── menu/             → menu item photos go here
│   └── gallery/          → aftermovie poster / gallery images
└── video/                → teaser + aftermovie video files
```

## ✏️ Things left empty on purpose

You said you'd fill these in yourself — they're already wired up in `index.html`,
just replace the placeholder block in each spot. Each one has an HTML comment
right above it explaining exactly what to swap in.

### 1. Teaser video — `#about` section
Drop your file in `video/` and replace the `.media-empty` block with:
```html
<video src="video/euphoria-teaser.mp4" autoplay muted loop playsinline></video>
```

### 2. Aftermovie — `#vibe` section
Same idea, further down the page (`.media-empty-wide` block). Works with a local
`<video>` file or a YouTube/Instagram `<iframe>` embed.

### 3. Menu — `#menu` section
Delete the `.menu-empty` div and add one `.menu-card` per dish:
```html
<div class="menu-card">
  <div class="menu-card-img"><img src="img/menu/starters.jpg" alt="Starters"></div>
  <h3>Starters</h3>
  <p>Two types</p>
</div>
```

### 4. Organizers — `#organizers` section
Replace each `.organizer-card--empty` div with:
```html
<div class="organizer-card">
  <div class="organizer-photo"><img src="img/organizers/name.jpg" alt="Full Name"></div>
  <h3>Full Name</h3>
  <p>Organizer</p>
</div>
```

### 5. Entry pass QR code — `#venue` section
Add your QR image to `img/` and swap the `.media-empty-qr` block for:
```html
<img src="img/QrCode.png" alt="Scan to get your Euphoria 26 pass">
```

### 6. Contact numbers — footer
Fill in the two `tel:` links in the footer's "Contact" column.

## 🎨 Theme tokens

Colors, fonts and spacing all live as CSS variables at the top of `css/style.css`
(`:root`), so the whole palette can be retuned from one place:

| Token | Value | Use |
|---|---|---|
| `--bg` | `#08050a` | page background |
| `--pink` | `#ff2f7e` | primary neon accent |
| `--violet` | `#9b4dff` | secondary accent / gradient |
| `--gold` | `#ffb84d` | chrome-title highlight |
| Display font | Anton | headings |
| Script font | Permanent Marker | "the night we don't talk" tagline |
| Body / mono | Space Grotesk / JetBrains Mono | copy & labels |

## 📅 Event details baked into the page

- **Date:** Sunday, 23rd August 2026
- **Time:** 6:00 PM – 11:00 PM
- **Venue:** Flavour Fall Restro, Sevasi Road, Vadodara
- **Entry Pass:** ₹777

Update these in `index.html` (and the `EVENT_DATE` constant in `js/script.js` for
the countdown) if any of it changes.
