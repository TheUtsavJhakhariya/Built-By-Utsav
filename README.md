# Handoff: BuiltByUtsav — Coming Soon (Blue Hour)

## Overview
Single-page "coming soon" holding page for builtbyutsav.com. Shows the brand logo, a one-line pitch, a short build-in-public progress log and an email capture.

## About the Design Files
`index.html` is a **design reference built in HTML** — a working, responsive prototype. Recreate it in the target codebase (Next.js/React, Astro, etc.) using its own patterns. If no codebase exists yet, `index.html` is clean enough to ship as-is on static hosting, or port it to Next.js / Astro.

## Fidelity
**High-fidelity.** Final colours, type, spacing and copy. Match pixel-for-pixel.

## Screen: Coming Soon
Full-viewport page (`min-height:100dvh`), 3 rows via flex column `justify-content:space-between`, padding `clamp(22px, 4vw, 56px)`.

1. **Top bar** — flex, space-between. JetBrains Mono 500, `clamp(10px,1vw,12px)`, letter-spacing .08em, white.
   - Left: `BUILTBYUTSAV.COM` · Right: 8×8 white square + `COMING SOON`.
2. **Hero** — centered column, gap `clamp(16px,2vw,22px)`.
   - **Logo** (see below), font-size `clamp(70px, 9vw, 130px)`.
   - Paragraph: General Sans 500, `clamp(15px,1.3vw,17px)`/1.5, max-width 520px, centered, `text-wrap:balance`.
     Copy: "A studio for websites, web apps and software — designed and coded in public. The site ships soon."
3. **Bottom** — flex row, space-between, align end; stacks to column (stretch) below 640px.
   - **Build log** (JetBrains Mono 500 12px/1.3, gap 8px): `✓ brand identity — shipped` · `◐ website — in progress` + 7×14 white block caret · `○ launch` in #C9CDFF.
   - **Email form**: white bar, 400px (full width on mobile), padding 5px 5px 5px 16px, square corners. Input General Sans 500 15px, placeholder #8A8A85. Button: #0C0C0C bg, white General Sans 600 15px, padding 12px 18px, label "Notify me →", hover #2A2A2A.

### Background (layered, bottom → top)
1. `linear-gradient(180deg, #3445FF 0%, #2B3BFF 45%, #1A26B8 100%)`
2. `radial-gradient(ellipse 70% 50% at 50% 38%, rgba(90,104,255,.55), transparent 70%)` — soft glow behind logo
3. Grain: SVG `feTurbulence` (baseFrequency .9, 3 octaves) tile 180px, `mix-blend-mode:soft-light`, opacity .6, fixed
4. Giant word **"soon"** — Instrument Serif italic 400, `clamp(230px, 43vw, 620px)`, line-height .8, letter-spacing -0.04em, `rgba(255,255,255,.07)`, centered, anchored to bottom edge, decorative (`aria-hidden`).

## Logo (blue colourway)
Two lines, General Sans 700, line-height .78, letter-spacing -0.06em:
- Line 1: `Built` white + `by` in **Instrument Serif italic 400** at 1.03em, colour #0C0C0C.
- Line 2: plate (#0C0C0C bg, padding .16em .16em .22em .1em, margin-top .1em) containing `Ut` white, `sav` #ffffff50 (white, ~31% opacity), caret bar .08em × .78em white.
- Caret blinks (1.1s, steps(1)); disabled under `prefers-reduced-motion`.
Other colourways (light / dark) are in the brand guide.

## Interactions
- Form submit: validate email (native `type=email`); on success replace form with "You're on the list — launch link coming your way." Wired to FormSubmit → builtbyutsav@gmail.com (activate via first-submit email; swap address for FormSubmit alias).
- Focus-visible: 2px #2B3BFF outline, 2px offset.

## Responsive
Fluid via `clamp()`. One breakpoint at 640px (footer stacks, form full width). Verified at 1440×900, 834×1112, 390×844.

## Design Tokens
- Blue #2B3BFF · Blue top #3445FF · Blue deep #1A26B8
- Ink #0C0C0C · Paper #FFFFFF · Suggest (on blue) #8E97FF · Muted #C9CDFF
- Fonts: General Sans 500/600/700 (Fontshare), Instrument Serif italic (Google), JetBrains Mono 500 (Google)
- Radius: 0 (square system) · Shadows: none

## Assets
No images. Grain is an inline SVG data URI. Fonts load from Fontshare + Google Fonts — self-host in production.

## Files
- `index.html` — complete responsive page (HTML + CSS + tiny JS)
- `README.md` — this spec
