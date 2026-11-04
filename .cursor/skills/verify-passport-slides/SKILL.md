---
name: verify-passport-slides
description: Build and drive this ten-slide Passport/Slidev tutorial deck, verify active-slide navigation and Counter interaction, capture slide pixels and report external-asset visual blockers honestly.
---
# Passport slide source verification

## Launch
Use Node22.12+ and `npm ci --ignore-scripts`, then `npm ci --ignore-scripts --prefix .cursor/skills/verify-passport-slides`. Source is slides.md and components/Counter.vue. Existing locked Slidev0.35.4/themes0.21.2,0.21.3 are now explicit, not latest; this fixes clean-install drift without a major upgrade. Normal workflow: `npm run dev`; production: `npm run build`. Chrome required, CHROME_PATH optional.

## Doctor
`node .cursor/skills/verify-passport-slides/helpers/verify.mjs /tmp/passport-proof` checks source, builds actual static output in its own temporary directory and serves it on a private loopback port. It verifies the active main page heading after navigation, not hidden overview thumbnails. Failed attempts close their own browser/server before rerun. Never attach to a shared Slidev editor or use open-in-editor buttons during proof.

## Drive
The same helper traverses all10 existing slides with real arrow keys until the active slide matches, captures each, verifies slide3's real JWT code block, clicks the actual Counter+ from10to11 on slide5 and checks Space navigates cover to strategies. No Vue/internal navigation setters or fake endpoints. It does not remove starter slides or change technical claims to inflate success. Fixed only broken Markdown separation on JWT slide, preserving wording/order/theme/notes.

## Evidence
Named output contains build.log,result.json,slide01-10PNGs. Inspect each full-size image, not hidden headings or screenshot existence. Helper blocks external network and records every attempted URL: fonts, Unsplash background,Tweet,theme preview images,animated logos,PlantUML,favicon. These missing assets are deliberate network-isolation coverage limits, not proven provider outages. No whole-deck visual acceptance: visualAcceptance is false. Local Mermaid/KaTeX and Counter render, but external panels/animation assets are unresolved. Inspecting a captured initial animation state is not an animation-finish pass.

## Cleanup
Helper owns/cleans its browser,ephemeral server and temporary build after every iteration; named proof survives. Confirm result.json and slides remain after exit. Do not delete source/assets/notes or prior evidence. Concurrent runs need their own output directories and owned sessions.

## Limits and maintenance
Build/navigation/Counter proof is separate from final presentation quality. No factual-currency, external-assetavailability, whole-deckvisualacceptance,mobile,allclickreveals,presenter,PDF/PPTXexport,CI,securityorhostedclaim. npm audit46(3critical25high18moderate) remains open. The deck has3Passportintro slides then7Slidevstarter examples; purpose/content expansion requires deliberate work, not silent deletion. Use /maintain-verification-skill after source changes and keep product/deck fixes separate from map maintenance.
