<div align="center">

# Meme Generator

**A fast, zero-dependency browser-based meme generator — one file, infinite memes.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![No Dependencies](https://img.shields.io/badge/dependencies-none-2ecc71.svg)](#)
[![Single File](https://img.shields.io/badge/file-1%20HTML%20file-3498db.svg)](#)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#contributing)

[Features](#features) · [Quick Start](#quick-start) · [Usage](#usage) · [Architecture](#architecture) · [Contributing](#contributing)

</div>

---

## Overview

Meme Generator is a self-contained web application that runs entirely in the browser with no build tools, no package managers, and no server-side logic. Drop a single HTML file into any browser and start creating memes instantly.

Built with the native HTML5 Canvas API and vanilla JavaScript — zero frameworks, zero external dependencies.

## Features

<details open>
<summary><strong>Image & Text</strong></summary>

- Upload any JPG, PNG, or GIF image
- Canvas auto-scales to match image dimensions
- Top and bottom text with classic meme styling — white fill, black outline
- Text auto-wraps for long phrases
- Adjustable text color, font size (10–100 px), and font family
- Drag text freely anywhere on the canvas

</details>

<details open>
<summary><strong>Drawing Tools</strong></summary>

- Freehand draw (pencil)
- Rectangle and ellipse shape tools
- Eraser
- Configurable stroke color and width (thin / medium / thick)
- Clear all drawings without affecting image or text

</details>

<details open>
<summary><strong>Export & Share</strong></summary>

- Download finished meme as `meme.png`
- One-click share to X (Twitter), Reddit, and Facebook

</details>

## Quick Start

No installation required. Pick one:

```bash
# Open the file directly in your browser
open index.html

# Or serve it locally
npx serve .
# → http://localhost:3000
```

## Usage

| Step | Action |
|------|--------|
| 1 | Click **Upload Image** and select a file |
| 2 | Enter top and bottom text in the sidebar |
| 3 | Adjust color, size, and font to your liking |
| 4 | Switch to **Select** mode and drag text into position |
| 5 | Use drawing tools to annotate the image |
| 6 | Click **Download PNG** to save your meme |

## Architecture

### Rendering Pipeline

The canvas renders in three distinct layers, bottom to top:

```
┌─────────────────────────────────┐
│  Layer 3 — Text Overlays        │  fillText + strokeText
├─────────────────────────────────┤
│  Layer 2 — User Drawings        │  strokes + shapes
├─────────────────────────────────┤
│  Layer 1 — Uploaded Image       │  drawImage
└─────────────────────────────────┘
```

### Text Rendering

```javascript
// Classic meme style
font         = bold {size}px {family}
textAlign    = center
strokeStyle  = #000
fillStyle    = user-selected color
lineWidth    = max(3, fontSize / 10)

// Draw order: strokeText → fillText
```

### File Structure

```
.
├── index.html    Complete application (HTML + CSS + JS)
├── README.md     Project documentation
├── LICENSE       MIT license
└── .gitignore    Standard exclusions
```

### Browser APIs Used

| API | Purpose |
|-----|---------|
| Canvas 2D | All rendering — image, text, drawings |
| FileReader | Read uploaded images as data URLs |
| Mouse Events | Drag-and-drop text, drawing interactions |
| CSS Custom Properties | Theme configuration |

## Font Families

Five built-in options:

| Font | Style |
|------|-------|
| Impact | Classic meme — default |
| Arial | Clean sans-serif |
| Comic Sans MS | Casual / humorous |
| Georgia | Serif, editorial feel |
| Courier New | Monospace, retro |

## Browser Support

| Browser | Status |
|---------|--------|
| Chrome 90+ | ✅ Fully supported |
| Firefox 88+ | ✅ Fully supported |
| Safari 14+ | ✅ Fully supported |
| Edge 90+ | ✅ Fully supported |

Requires: Canvas API, FileReader API, CSS Custom Properties.

## Contributing

Contributions are welcome. To get started:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/name`)
3. Commit your changes (`git commit -m 'feat: add feature'`)
4. Push to the branch (`git push origin feature/name`)
5. Open a Pull Request

### Commit Convention

This project follows [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: add new feature
fix: resolve a bug
docs: documentation changes
style: formatting, no code change
refactor: code restructuring
```

## License

Distributed under the MIT License. See [LICENSE](LICENSE) for details.

---

<div align="center">

**[Report Bug](https://github.com/aadityasinhaa/Meme-Generator-App/issues) · [Request Feature](https://github.com/aadityasinhaa/Meme-Generator-App/issues)**

</div>
