# Rendering and external assets

## Sub-features
Capture every slide and inspect the pixels. Slide 3 must show separate JWT bullets and a real code block. Mermaid and KaTeX render locally; external Tweet, background, theme images, logos and PlantUML are blocked by the isolated harness. Final visual acceptance remains false.

## How to get to it (user POV)
Run `npm run dev` and open Slidev, or use the static production helper from SKILL.md. Navigate with the keyboard; do not click editor integrations.

## Driving it with Puppeteer
Run the helper command from SKILL.md. Inspect its active-slide screenshots, counter-after.png and result.json. Every run builds the actual source and owns its browser and server.

## Gotchas
External asset availability, technical content currency, export, mobile and CI are unverified. This is not final deck acceptance.
