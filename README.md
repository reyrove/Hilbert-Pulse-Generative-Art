# Hilbert Pulse — Generative Art

> A seed-based generative system for space-filling Hilbert curve compositions.  
> A reproducible catalogue of computational curve studies.

---

## What is this?

**Hilbert Pulse** is a generative design system built around the Hilbert curve — a single continuous path that visits every cell of a square grid without ever crossing itself. That path is broken into coloured segments, layered over a dark field, and rotated and scaled by a single numeric seed into a dense, rhythmic weave of line and hue.

Every artwork in this catalogue is defined by a single numeric seed. The same seed always produces the identical composition — making each piece **traceable, reproducible, and licensable** across textile, print, and apparel applications.

Named for the space-filling curve first described by David Hilbert in 1891, **Hilbert Pulse** reframes that mathematical object as a textile.

---

## Live

🌐 **[View the catalogue →](https://reyrove.github.io/Hilbert-Pulse/)**

---

## The System

The generator combines two layers:

| Layer | Description |
|-------|-------------|
| **Hilbert path** | A recursive space-filling curve drawn at order 4 to 8 — up to 65,536 points. |
| **Colour pulses** | The path is broken into segments, each tinted from a 4-colour palette derived from a seeded base hue. |

Both layers are driven by the same seed, ensuring deterministic output.

### Parameters

- **Order** — 4 to 8 (grid of 2ⁿ × 2ⁿ cells)
- **Total points** — 2ⁿ × 2ⁿ (256 to 65,536)
- **Palette** — 4 colours drawn from HSB space, each offset from a base hue by 0°, 60°, 120°, 180°
- **Stroke weight** — scaled to canvas size, seeded
- **Segment breaks** — 60% continue, 40% break
- **Transform** — optional rotation (0–45°) and scale (0.5–2.0×)
- **Background** — a bright HSB field (saturation 255, brightness 60–100)

---

## Structure

```
Hilbert-Pulse/
├── index.html              ← Full catalogue (single-file)
├── images/
│   ├── fav.svg
│   ├── hilbert-tote.png
│   ├── hilbert-cushion.png
│   └── ...
├── Hilbert-Pulse.jpg       ← Apparel mockup
└── README.md
```

The entire project is contained in a single `index.html` — no build step, no dependencies, no framework. Open it in any modern browser.

---

## Features

- **Seed-based generation** — every composition is deterministic and reproducible
- **Live catalogue** — cover, statement, plate, surfaces, process, archive, commission sections
- **Multiple surfaces** — print, scarf, textile, wallpaper — all rendered from the same seed
- **Archive of 8 seeds** — click any plate to load it into the main view
- **PNG export** — download any composition directly from the browser
- **Keyboard shortcuts** — `R` for new seed, `S` to save
- **Legal modal** — licensing, terms, and credits built in
- **Responsive** — works on desktop, tablet, and mobile
- **Mobile-first navbar** — horizontally scrollable with fade hint

---

## Usage

### Generate a new composition

Click **New Seed** or press `R`.

### Download the current composition

Click **Download** or press `S`.

### Load a seed from the archive

Click any plate in the **Archive** section.

---

## Color System

Every composition is built from HSB colour, converted to RGB at draw time:

- **Background** — a bright HSB field (saturation 255, brightness 60–100)
- **Base hue** — the starting hue for the palette
- **Palette** — 4 colours at offsets 0°, 60°, 120°, 180° from the base, with saturation 200 and brightness 255
- **Stroke weight** — scaled to canvas size, bounded per seed

Each seed selects a unique combination — no two compositions share the same palette.

---

## Technical Notes

- Pure vanilla JavaScript — no libraries
- Canvas 2D rendering
- Custom xorshift random generator for deterministic seeds
- Device-pixel-ratio aware rendering
- Fully static rendering — one seed produces one composition, no animation loops
- Single `renderStatic()` function drives the cover, plate, framed print, all four surfaces, and all eight archive thumbnails
- Recursive Hilbert curve generation in place (no lookup tables)
- Segment breaks drawn as separate paths for the woven, stitched appearance
- `prefers-reduced-motion` respected

---

## About

**Hilbert Pulse** is a project by [Reyhaneh Daneshdoost](https://reyrove.github.io/) — an Iranian-born artist working at the intersection of classical textile logic and generative systems.

The work begins with a simple observation: the woven surface — repetitive, mathematically structured, infinitely variable — has always been a form of computation, long before computers.

**Hilbert Pulse** is an attempt to render that logic visible.

> *A single line, folded through space until it touches every point of the field.*

---

## Licensing

All compositions are seed-documented and available for licensing across textile, surface, and apparel applications.

For commercial use, custom editions, or exclusive rights:

📧 **reyhanehdaneshdoost@gmail.com**

See the **Licensing** section in the live catalogue for details.

---

## Links

- 🌐 [Website](https://reyrove.github.io/)
- 📷 [Instagram](https://www.instagram.com/rey._.rove/)
- 💼 [LinkedIn](https://www.linkedin.com/in/reyhaneh-daneshdoost-730481160/)
- 🐦 [X](https://x.com/reyrove)

---

## Credits

**Design & Generative System**  
Reyhaneh Daneshdoost

**Typefaces**  
Cormorant Garamond · DM Mono

**Edition**  
Hilbert Pulse — Autumn 2026

---

<p align="center">
  <em>Generative Space-Filling Curve</em><br />
  <sub>© Reyrove Studio · All compositions reproducible by seed</sub>
</p>