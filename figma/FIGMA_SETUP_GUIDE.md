# BamtryOS — Figma Setup Guide
**Step-by-step guide for setting up the BamtryOS design in Figma**
Bamtry Technologies Ltd. | For: Jam-Forte Technologies | 2026

---

## What You Have (Design Phase Package)

The HTML design package at `https://mubby27.github.io/bamtryos-design/` is the **living design reference** — it covers architecture, flows, API specs, and the interactive prototype. It is the source of truth for the design.

Figma is where Jam-Forte needs the design for development. This guide gets you there.

---

## Step 1 — Create Figma Accounts

1. Go to **figma.com** → Sign Up (free plan works to start)
2. Create a **Team** called: `Bamtry Technologies`
3. Create a **Project** called: `BamtryOS`
4. Inside that project, create **4 files**:
   - `BamtryOS — Design System`
   - `BamtryOS — Wireframes`
   - `BamtryOS — Hi-Fi Screens`
   - `BamtryOS — Prototype`

---

## Step 2 — Set Up Design System File

Open `BamtryOS — Design System` and create 4 pages:
1. `Tokens` — color swatches, typography scale, spacing
2. `Components` — all UI components
3. `Icons` — icon library
4. `Motion` — animation specs

### Import Color Tokens via Token Studio

1. In Figma: **Plugins → Search "Token Studio" → Install** (free)
2. Open Token Studio plugin
3. Click **"Import"** → **"JSON"**
4. Paste the contents of `figma/design-tokens.json` (from your download folder)
5. Click **Apply** → all color tokens appear as Figma styles instantly

This gives you all colors, spacing, typography, shadows, and component tokens in one import.

### Set Up Color Styles Manually (if Token Studio fails)

Create these as Figma Color Styles (the paint bucket in the right panel):

| Style Name | Hex |
|---|---|
| `color/primary/blue` | `#00A3FF` |
| `color/bg/base` | `#0A0A0F` |
| `color/bg/surface` | `#12121C` |
| `color/bg/elevated` | `#1A1A2E` |
| `color/border/subtle` | `#1E2040` |
| `color/text/primary` | `#FFFFFF` |
| `color/text/secondary` | `#8899BB` |
| `color/semantic/success` | `#00E676` |
| `color/semantic/error` | `#FF4444` |
| `color/semantic/warning` | `#FFB300` |

### Set Up Text Styles

Create these Figma Text Styles:

| Style | Font | Weight | Size |
|---|---|---|---|
| `text/display` | Space Grotesk | 800 | 48 |
| `text/h1` | Space Grotesk | 700 | 36 |
| `text/h2` | Space Grotesk | 700 | 28 |
| `text/h3` | Space Grotesk | 700 | 22 |
| `text/h4` | Space Grotesk | 600 | 18 |
| `text/body-l` | Inter | 400 | 16 |
| `text/body-m` | Inter | 400 | 14 |
| `text/caption` | Inter | 400 | 12 |
| `text/label` | Inter | 600 | 11 |
| `text/mono` | JetBrains Mono | 400 | 12 |

### Publish the Design System

1. Click the file name → **"Publish Styles and Variables"**
2. This makes it available to all other Figma files in your team
3. All other files (wireframes, hi-fi, prototype) will use these styles

---

## Step 3 — Set Up FigJam for User Flows

FigJam is Figma's whiteboard. Use it for visual flow diagrams.

1. Go to **figma.com/figjam** → New FigJam file
2. Name it: `BamtryOS — User Flows & Architecture`
3. Recreate the 8 user flows from `07_User_Flows.html` as visual diagrams:

**Color coding by actor:**
- 🔵 Blue boxes = **Bridge App** actions (local device)
- 🟣 Purple boxes = **Cloud OS** actions (decentralized)
- 🟡 Yellow = **Blockchain** transactions
- 🟢 Green = **Success / completion** states
- 🔴 Red = **TEE / signing** (security gates)

**Tool tips:**
- Use **Shape tool (R)** for screen boxes
- Use **Arrow tool (A)** to connect screens with flow direction
- Use **Text (T)** for step labels
- Use **Sticky Notes** for annotations and requirements

---

## Step 4 — Build Wireframes

1. Open `BamtryOS — Wireframes` file
2. Add a page: `Mobile Wireframes`
3. For each screen, create a Frame: **iPhone 14 Pro (393 × 852px)**

**Screens to wireframe (in order):**
1. Welcome / Onboarding
2. Create Identity (DID setup)
3. Backup Phrase (12-word mnemonic)
4. Wallet Setup
5. Dashboard / Home
6. Wallet Screen
7. Send Transaction (3-step flow)
8. Receive Screen
9. dApp Store
10. Identity / Profile
11. Settings
12. AI Agent Chat
13. Device Management
14. Transaction History

**Wireframe rules:**
- Black, white, and gray ONLY — no color
- Use rectangles for content blocks
- Use X-marks for image placeholders
- Use wavy lines for text placeholders
- Label every element with its purpose

**Autoflow plugin:**
- Install **Autoflow** (Figma Community → search "Autoflow")
- Select two frames → click Autoflow → draws a connecting arrow automatically
- Shows the navigation flow visually

---

## Step 5 — Build Hi-Fi Screens

1. Open `BamtryOS — Hi-Fi Screens` file
2. Enable the Design System library: **Assets panel → Libraries → BamtryOS Design System ✓**
3. For each wireframe approved screen, create the hi-fi version

**Hi-fi design rules:**
- Always use color tokens — never hardcode hex values
- Apply glassmorphism: `fill: rgba(18,18,28,0.7) + backdrop-blur: 16px`
- Blue glow effect: `Drop Shadow: color #00A3FF, spread 24, opacity 35%`
- Space Grotesk for all headings and balance figures
- Inter for all body text and navigation labels

**Screen-by-screen reference:** See `index.html` and `02_UI_Prototype.html` for exact visual designs

---

## Step 6 — Build Figma Prototype

1. Open `BamtryOS — Prototype` file
2. Copy all hi-fi screens into it
3. Switch to **Prototype mode** (top-right toggle in Figma)
4. For each button/CTA: drag the blue arrow → connect to target screen
5. Set transition: **Smart Animate** (creates smooth, app-like motion)
6. Press **Play** → interactive clickable prototype opens in browser

**Key flows to connect:**
- Welcome → Create Identity → Backup Phrase → Dashboard
- Dashboard → Wallet → Send → Confirm → Success
- Dashboard → dApp Store → App Detail → Install → Dashboard
- Dashboard → AI Agent → Action Card → PIN → Success

**Share the prototype:**
- Click **Share** → Copy prototype link
- Send to Abdul Basit and Jam-Forte for review

---

## Step 7 — Developer Handoff to Jam-Forte

### Figma Dev Mode

1. In Figma, switch to **Dev Mode** (toggle top-right)
2. Jam-Forte can click any element and see:
   - Exact dimensions (px)
   - Color values with token names
   - Font: size, weight, family
   - Spacing and padding values
   - Auto-generated CSS code
3. Share a **Dev Mode link**: File → Share → "Anyone with link can view in Dev Mode"

### Zeroheight (Design System Docs Site)

1. Go to **zeroheight.com** → Create account
2. Click **"Connect Figma"** → select `BamtryOS — Design System`
3. Zeroheight auto-pulls all components, colors, typography
4. Add written descriptions using the guidelines in `07_User_Flows.html`
5. Publish → share the link with Jam-Forte

### CSS Variables File

The file `figma/variables.css` contains all design tokens as CSS custom properties. Share this with Jam-Forte's engineering team — they can import it into their codebase directly.

### Design Tokens JSON

The file `figma/design-tokens.json` can be imported into any Token Studio or Style Dictionary workflow the Jam-Forte engineering team uses.

---

## Step 8 — Set Up Notion Design Hub

1. Go to **notion.so** → Create workspace: `BamtryOS Design Hub`
2. Create these pages:
   - `Design System` — embed Figma design system file + Zeroheight link
   - `Screen Inventory` — list all screens with Figma links
   - `User Flows` — embed FigJam + link to `07_User_Flows.html`
   - `Brand Guidelines` — embed `01_Design_System.html`
   - `Architecture` — link to `03_System_Architecture.html`
   - `API Reference` — link to `04_API_Specification.html`
   - `Changelog` — track all design decisions
3. Invite Jam-Forte: **Settings → Share → Invite by email**

---

## Plugins to Install in Figma

| Plugin | Purpose | Link |
|---|---|---|
| **Token Studio** | Import design-tokens.json instantly | Search in Figma Plugins |
| **Autoflow** | Draw arrows between screens | Figma Community |
| **Anima** | Convert React/HTML code → Figma frames | animaapp.com |
| **Unsplash** | Stock photos for mockup content | Search in Figma Plugins |
| **Content Reel** | Realistic placeholder text, names, addresses | Search in Figma Plugins |
| **Icons8** | Icon library (Web3 icons available) | Search in Figma Plugins |

---

## Naming Convention

Use this naming convention consistently so Jam-Forte can find everything:

```
Screens:      [Pillar]/[ScreenName]   e.g. Wallet/Send, Identity/Onboarding
Components:   [Type]/[Name]/[State]   e.g. Button/Primary/Default
Colors:       color/[group]/[name]    e.g. color/primary/blue
Spacing:      space/[size]            e.g. space/4
```

---

## Quick Reference — Brand Colours

| Token | Hex | Use |
|---|---|---|
| Primary Blue | `#00A3FF` | Buttons, links, active states |
| Background | `#0A0A0F` | App background |
| Surface | `#12121C` | Cards, panels |
| Surface Elevated | `#1A1A2E` | Elevated components |
| Border | `#1E2040` | Dividers |
| Text Primary | `#FFFFFF` | Main text |
| Text Secondary | `#8899BB` | Subtext |
| Success | `#00E676` | Confirmed, verified |
| Error | `#FF4444` | Failed, rejected |
| Warning | `#FFB300` | Risk alerts |

---

*This guide + all design files are at: https://mubby27.github.io/bamtryos-design/*
*Bamtry Technologies Ltd. | bamtry.com | 2026*
