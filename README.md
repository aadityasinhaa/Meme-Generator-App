# Meme Generator

A lightweight, zero-dependency browser-based meme generator. Upload an image, add text, draw annotations, and export — all in a single HTML file.

## Features

| Feature | Description |
|---|---|
| **Image Upload** | Supports JPG, PNG, and GIF. Canvas auto-resizes to image dimensions. |
| **Text Overlay** | Top and bottom text with classic meme styling (white fill, black outline). |
| **Text Customization** | Color picker, font size slider (10–100px), and 5 font families. |
| **Draggable Text** | Click and drag text anywhere on the canvas in Select mode. |
| **Drawing Tools** | Free draw, rectangle, ellipse, and eraser with configurable color and stroke width. |
| **Export** | Download the canvas as a PNG file (`meme.png`). |
| **Social Share** | One-click share to X (Twitter), Reddit, and Facebook. |

## Getting Started

No build step. No dependencies. No install.

```bash
# Option 1 — Open directly
open index.html

# Option 2 — Serve locally
npx serve .
# then visit http://localhost:3000
```

That's it. Everything runs client-side in the browser.

## Usage

1. **Upload** — Click "Upload Image" and select a JPG, PNG, or GIF.
2. **Add Text** — Type into the top/bottom text fields. Adjust color, size, and font.
3. **Move Text** — Switch to Select mode (pointer icon), then click and drag text on the canvas.
4. **Draw** — Pick a drawing tool (free draw, rectangle, circle, or eraser), set color and width, then draw on the canvas.
5. **Export** — Click "Download PNG" to save your meme.

## Canvas Rendering Order

The canvas renders in three layers, bottom to top:

1. Uploaded image
2. User drawings (freehand strokes, shapes, eraser marks)
3. Text overlays (top and bottom)

## Tech Stack

- HTML5 Canvas API for all rendering
- Vanilla JavaScript (ES5-compatible, no frameworks)
- CSS custom properties for theming
- Inter font via Google Fonts (UI only — canvas text uses system fonts)

## Browser Support

Tested on modern browsers (Chrome, Firefox, Safari, Edge). Requires:

- Canvas API
- FileReader API
- CSS custom properties

## Project Structure

```
.
├── index.html    # Complete app (HTML + CSS + JS)
└── README.md
```

## License

MIT
