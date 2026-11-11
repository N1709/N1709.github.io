# N1709 — Portfolio

Personal portfolio of **Kentaro (けんたろう)**, student and solo developer focused on **Android (AOSP) development** and **game development**.

---

## Overview

A single-page, dependency-free portfolio built with plain HTML, CSS, and JavaScript. It is designed around bold typography, a rotating ring, and a WebGL-rendered name that morphs between Latin letters and hiragana (`KENTARO` ↔ `けんたろう`).

No frameworks, no build step, no bundler. Open `index.html` and it works.

## Features

- **WebGL hero** — the name is rendered in a fragment shader with a text-morph transition, cursor ripple, scroll distortion, and chromatic aberration.
- **Automatic fallback** — if WebGL is unavailable or reduced motion is on, the hero falls back to a lightweight DOM version.
- **Color themes** — 8 themes (orange, lime, black, off-white, blood red, acid yellow, gold, deep green) that blend smoothly into each other every few seconds.
- **Opening and page transitions** — a six-stripe veil wipes away when the site opens and when returning from a project page.
- **Letter-lift effect** — letters rise toward the cursor (or finger) on "Let's talk", the Works rows, the Stack rows, and the close button.
- **Project pages** — each work and stack category has its own page, routed with the URL hash (`#/work/aetheriaos`) so links can be shared.
- **Responsive** — layout adapts to phones; heavy distortion effects are toned down on touch screens.
- **Accessible motion** — respects `prefers-reduced-motion`.
- **Round favicon** — generated from the avatar image, with a pre-rounded fallback for `file://` and strict browsers.
- **Live clock** — shows local time in WIB (Asia/Jakarta).

## Sections

| Section | Description |
|---------|-------------|
| **Hero** | Animated name, navigation, role, and clock |
| **About** | Short introduction with highlighted text inside the ring |
| **Works** | AetheriaOS, PixelLines, Blood And Gunpowder, ios-whyred |
| **Stack** | Skills, Tools, Languages |
| **Contact** | "Let's talk" link plus LinkedIn, GitHub, Telegram, and itch.io |

## Projects Featured

| Project | Category | Stack |
|---------|----------|-------|
| [AetheriaOS](https://aetheriaos.github.io/) | Android ROM | AOSP, Android 16, Based on LineageOS |
| [PixelLines](https://github.com/PixelLines) | Android ROM | AOSP, Custom ROM, Privacy |
| [Blood And Gunpowder](https://github.com/N1709/Sangue_e_Polvora-demo) | Game | Godot Engine, GDScript, Game Development |
| [ios-whyred](https://github.com/N1709/ios-whyred2) | Kernel | XNU, Kernel, Whyred, SDM660, iOS 16 |

## Tech

- HTML5, CSS3 (custom properties, grid, flexbox)
- Vanilla JavaScript (ES6+)
- WebGL 1 (single fragment shader)
- Google Fonts: **Anton**, **Inter**, **Noto Sans JP**

## Project Structure

```
.
├── index.html          # The whole site (markup, styles, scripts)
├── assets/
│   └── icon/
│       ├── avatar.png      # Profile picture, cropped into the tab icon
│       ├── favicon.png     # Round fallback icon
│       └── README.md
└── README.md
```

## Run Locally

No installation needed.

**Option 1 — open the file**

Double-click `index.html`.

**Option 2 — local server** (recommended, closest to production)

```bash
# Python
python3 -m http.server 8000

# or Node
npx serve .
```

Then open http://localhost:8000.

## Customize

Everything lives in `index.html`.

**Add or edit a project**

Find the `WORKS` array in the script and add an entry:

```js
{
  slug: 'my-project',
  title: 'My Project',
  cat: 'Category',
  role: 'Developer',
  bg: '#FF3D00',          // page background
  fg: '#c3f7c6',          // page text
  stack: 'Tech A, Tech B, Tech C',
  desc: ['First sentence.', 'Second sentence.'],
  href: 'https://example.com',
  cta: 'Visit Site',
  thumb: 'Short hover caption'
}
```

**Edit skills, tools, or languages**

Edit the `STACKS` array. Each comma-separated item in `stack` becomes its own row.

**Change colors**

Edit the `THEMES` array, and keep the initial color list at the top of the file (`var c=[...]`) in the same order and length.

**Change the favicon**

Replace `assets/icon/avatar.png` and `assets/icon/favicon.png`, keeping the same file names.

**Change the name animation**

Edit the `STATES` array to change the stages of the morph (for example `KENTARO` → `けんたろう`).

## Deploy to GitHub Pages

1. Name the repository `N1709.github.io`.
2. Push `index.html` and the `assets/` folder to the `main` branch.
3. Go to **Settings → Pages** and select the `main` branch, root folder.
4. The site is available at `https://n1709.github.io` after a short build.

> GitHub Pages is case-sensitive. Keep file and folder names exactly as written.

## Browser Support

Works in current versions of Chrome, Edge, Firefox, Safari, and Opera. WebGL is used when available; otherwise the hero falls back to the DOM version automatically.

## Performance Notes

- The shader only does extra work while the name is morphing.
- Rendering pauses to a low frame rate when nothing is moving.
- Canvas resolution scales down automatically if frames get slow.
- Motion-heavy effects are reduced on touch devices and disabled for users who prefer reduced motion.

## Contact

- Telegram: [@NKB0B](https://t.me/NKB0B)
- GitHub: [N1709](https://github.com/N1709)
- LinkedIn: [kentaroaldanatien](https://www.linkedin.com/in/kentaroaldanatien)
- itch.io: [n1709.itch.io](https://n1709.itch.io/)

Open to collaboration on open-source and software engineering projects, from cross-chipset firmware ports and game loops to web back-end systems.

## License

All rights reserved unless stated otherwise. Add a `LICENSE` file if you want to open the code for reuse.
