# BuyMaterials Design System

## Overview

**BuyMaterials** (buymaterials.com) is a B2B online marketplace for construction and building materials. It connects buyers (contractors, construction companies) with merchants (suppliers and distributors). The platform features a **Buyer-facing marketplace** and a **Merchant dashboard** for managing products, orders, and branch locations.

### Sources

- **Figma Design System**: `BuyMaterials _ Design System.fig` — mounted as virtual filesystem. Contains 5 pages: Cover, Style, Components, Starter-kit, Exploration. 106 top-level frames.
  - Figma file ID (for reference): see the `.fig` attachment
- **GitHub Repository**: [nebojsab/BM-DS](https://github.com/nebojsab/BM-DS) — Claude test DS

---

## Products / Surfaces

| Surface | Description |
|---|---|
| **Marketplace (Buyer)** | Public-facing catalog with product listing, search (Omni-search), categories, product detail pages, cart |
| **Merchant Dashboard** | Private app with sidebar navigation — manages products, orders, branches, buyers |
| **Mobile Web** | Responsive variant of both surfaces (360px breakpoint) |

---

## CONTENT FUNDAMENTALS

### Tone & Voice
- **Professional but accessible.** Copy is direct and task-focused — no fluff.
- **Sentence case** used throughout UI labels (e.g. "Add to cart", not "Add To Cart").
- **Second person ("you/your")** is assumed from context; very little first-person copy visible.
- **No emoji** in UI copy. Icons are used as visual anchors, not emoji.
- **Concise labels**: navigation items use single words ("Orders", "Branches", "Buyers") or short noun phrases.
- **Decimal formatting** for prices/quantities uses standard locale format.
- **Status labels** are single-word, title-cased: Success, Warning, Danger, Info, Neutral.

### Examples
- "Primary button - Filled / Secondary button - Outlined / Tertiary button - Without fill / Destructive"
- "Enabled / Hovered / Focused / Pressed / Disabled" (state vocabulary)
- Navigation: "Dashboard", "Marketplace", "Orders", "Branches", "Buyers"
- Page copy: "Buyer / Product Details Page"

---

## VISUAL FOUNDATIONS

### Colors

**Brand / Primary (Mint)**
- Main: `#56D2BA` (rgb 86,210,186)
- Scale: `#2F7466` → `#3D9584` → `#4EBFA9` → `#56D2BA` → `#78DBC8` → `#8EE1D1` → `#B1EADF` → `#CBF1EA` → `#EEFBF8`
- Used as primary action color (buttons, active states, highlights)

**Neutral / Text**
- Dark navy (text primary): `#00001E`
- Dark charcoal (sidebar bg): `#212623`
- Medium grey: `#999B9A`
- Light grey border: `#EEEEEE`, `#E4E5E5`
- Off-white bg: `#F7F7F7`, `#F9F9F9`

**Semantic**
- Success (green): `#3CC752` (main), scale from `#216D2D`
- Info (blue): `#47B0D2` (main), scale from `#276174`
- Danger (red): `#D64949` (main), scale from `#762828`
- Warning (orange): `#EB9A4C` (main), scale from `#81552A`
- Purple (other): `#6200EE` (main), scale from `#360083`

### Typography

Primary font: **Poppins** (Regular, SemiBold, Bold, Medium)
Secondary font: **Inter** (Regular, Medium, Bold) — used for data/tables/smaller UI

| Role | Font | Weight | Size | Line Height |
|---|---|---|---|---|
| H1 | Poppins | Bold | 29px | 160% |
| H2 | Poppins | Bold | 24px | 160% |
| H3 | Poppins | Bold | 20px | 160% |
| H4 | Poppins | SemiBold | 16px | 140% |
| H5 | Poppins | SemiBold | 14px | 140% |
| H6 | Poppins | SemiBold | 12px | 140% |
| Body L | Poppins | Regular | 16px | 160% |
| Body M | Poppins | Regular | 14px | 160% |
| Body S | Poppins | Regular | 12px | 160% |
| Button L | Poppins | SemiBold | 16px | 100% |
| Button M | Poppins | SemiBold | 14px | 100% |
| Button S | Poppins | SemiBold | 12px | 100% |
| Caption | Poppins | Regular | 12px | 160% |
| Pre-title | Poppins | SemiBold | 12px | — (letter-spacing 5%) |
| Link | Poppins | Regular | 16px | Underline |

> **Font files**: Full Poppins family (18 weights/styles) is included locally in `fonts/`. Inter is loaded via Google Fonts (no brand file supplied). Sofia Pro (used for style guide headers) is a commercial font — substituted with Poppins Bold. Please supply `SofiaPro-Bold.woff2` if available.

### Backgrounds
- Page backgrounds: `#F6F6F6` (product pages), `#FFFFFF` (cards/modals)
- Sidebar: `#212623` (very dark green-charcoal)
- Design guidelines highlight sections: `#F5FAFF` (light blue tint)
- No full-bleed photography in the design system itself; product listing cards use product images

### Shadows & Elevation
- **Elevation 1**: `box-shadow: 0px 4px 4px -2px rgba(0,0,0,0.15)` — cards, dropdowns
- **Elevation 2**: `box-shadow: 0px 8px 16px rgba(0,0,0,0.10)` — modals, popovers (inferred)
- Corner radius: `4px` (small — inputs, badges), `8px` (default — buttons, chips), `12px` (sidebar), `16px` (cards, page frames), `32px` (style guide panels)

### Borders
- Standard border: `1px solid #EEEEEE` or `1px solid #E4E5E5`
- Input borders: `1px solid #CACBCA`
- Active/focus borders: `2px solid #56D2BA`

### Hover / Press States
- Hover: lighter tint of brand color or opacity shift (~0.85)
- Pressed: darker shade of brand color
- Disabled: opacity 0.38–0.5, color `#CACBCA`
- Focus ring: `2px solid #56D2BA` with slight offset

### Animation
- No complex animations in the design system; transitions are subtle
- Standard easing assumed: `ease-in-out`, 150–200ms for micro-interactions

### Imagery
- Product images are shown in cards with placeholder boxes
- No illustrated backgrounds; clean white/light-grey surfaces
- No grain or texture
- Cool-neutral color temperature in product imagery

### Iconography approach
- Custom icon set: **Style=Line** (line icons, Bold=Yes/No variants)
- Very high usage (1948+ instances of line bold icons)
- Icons are typically 16px or 24px
- Icon color matches text color or uses brand mint for active states
- No emoji used as icons

---

## ICONOGRAPHY

- **Primary icon style**: Line icons, two weights — Bold and Regular
- **Sizing**: 16px (inline/compact), 24px (standard UI)
- **Format**: Custom SVG set referenced as components in Figma
- **CDN substitute**: [Phosphor Icons](https://phosphoricons.com/) — closest stroke-weight match to the BuyMaterials line icon set. Loaded via `<script src="https://unpkg.com/@phosphor-icons/web"></script>`
- Common icons used: chevron-down, add/plus, search/magnifying glass, check/interface check, placeholder, close
- ⚠️ The original icon SVGs are embedded as Figma vector components. This kit uses Phosphor Icons as a substitute. Supply original SVG exports for production use.

---

## File Index

```
/
├── README.md                    ← This file
├── SKILL.md                     ← Agent skill descriptor
├── colors_and_type.css          ← All CSS custom properties (colors + typography)
├── assets/
│   ├── logo-full.png            ← Full logo (mark + wordmark, dark on white)
│   ├── logo-wordmark.png        ← Wordmark only
│   └── logo-mark.png            ← Icon mark only (rounded square, dark)
├── preview/
│   ├── colors-brand.html        ← Brand mint color scale
│   ├── colors-neutral.html      ← Neutral greys
│   ├── colors-semantic.html     ← Semantic colors (success/danger/warning/info)
│   ├── type-scale.html          ← Heading + body type specimens
│   ├── type-buttons.html        ← Button text styles
│   ├── spacing-tokens.html      ← Corner radius + shadow tokens
│   ├── components-buttons.html  ← Button components
│   ├── components-badges.html   ← Badge/tag components
│   ├── components-inputs.html   ← Form inputs
│   ├── components-nav.html      ← Sidebar navigation
│   └── brand-logo.html          ← Logo variants
└── ui_kits/
    └── web/
        ├── README.md            ← UI kit notes
        └── index.html           ← Interactive web app prototype
```
