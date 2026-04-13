# Painkiller Wireframes — Claude Code Instructions

## What This Project Is

This is the **Painkiller wireframe prototype** — a single HTML file (`index.html`) that contains all of the app's screen designs. It's a living design document that gets deployed automatically to the web every time you push changes.

**Live site:** https://painkiller-wires.vercel.app
**GitHub repo:** https://github.com/aromanarguello/painkiller-wires

Every time you push to `main`, Vercel automatically deploys the new version. There's no build step — it just publishes the HTML file as-is.

## How the File Is Structured

Everything lives in one file: `index.html` (~3,800 lines). Here's how it's organized:

### 1. Design tokens (lines 9–27)
CSS variables that control the entire color palette, fonts, and spacing:
```css
--cream:#ffffff;      /* primary surface */
--border:#e5e5e5;     /* hairline borders */
--camel:#737373;      /* muted label text */
--dark:#141414;       /* ink / primary text */
--red:#cf4a3c;
--green:#17a34a;
```
The font is **Inter** everywhere (weights 400–700).

### 2. Shared styles (lines 28–250ish)
CSS for buttons (`.btn`), pills (`.pill`), navigation (`.topnav`, `.cy-tabs`), cards, tables, and layout (`.wrap`, `.main`).

### 3. Screens (the bulk of the file)
Each screen is a `<section class="screen" id="...">`. The screens in order:

| Screen | ID | Starts at line | What it is |
|--------|----|----------------|------------|
| Address Gate | `gate` | ~865 | Landing — enter your address |
| Results | `results` | ~1110 | Property match results |
| Pricing | `pricing` | ~1291 | Subscription tiers |
| Onboarding | `onboard` | ~1362 | Post-signup setup flow |
| Dashboard | `dashboard` | ~1424 | Main home dashboard |
| Property Overview | `overview` | ~1962 | Single property detail |
| Expenses | `expenses` | ~2381 | Spending tracker |
| Improvements | `improvements` | ~2952 | Home improvement projects |
| Vendors | `vendors` | ~3198 | Vendor/contractor list |

### 4. JavaScript (lines 3760–3836)
Small scripts for:
- **Screen switcher** — the dark toolbar at the top that toggles between screens
- **Notification drawer** — slide-out panel
- **Cmd+K search** — search overlay
- **Chart scrubber** — interactive spending chart on the expenses screen

## How to Make Changes

### Editing text, colors, or layout
Just edit `index.html`. The CSS is all inline in the `<style>` block at the top of the file. Each screen is self-contained in its own `<section>`.

### Adding a new screen
1. Add a new `<section class="screen" id="your-id">` before the `<script>` tag
2. Add a button to the switcher bar (look for `id="switcher"` near the top of the `<body>`):
   ```html
   <button data-target="your-id">Screen Name</button>
   ```
3. The JS switcher handles the rest automatically

### Changing the design system
Edit the CSS variables in `:root` at the top. Changes cascade everywhere.

### Adding images
Put image files in the same directory. Reference them with relative paths: `<img src="photo.jpg">`. They'll deploy alongside the HTML.

## Important Rules

- **Don't delete the `<script>` block** at the bottom — it powers the screen switching and interactions
- **Don't change the `class="screen"` or `id="..."` attributes** on existing sections unless you also update the switcher buttons
- **Keep it as one file** — the whole point is simplicity. Don't split into multiple HTML files unless Alejandro says to
- **Test locally** before pushing — just open `index.html` in your browser (double-click the file, or drag it into Chrome/Safari)
- **The switcher toolbar** (dark bar at top) is only for design review — it won't be in the real app

## Pushing Your Changes

After making edits, push to deploy:

```
git add index.html
git commit -m "describe what you changed"
git push
```

Vercel deploys automatically in ~10 seconds. Refresh the live site to see your changes.

If you added new files (like images), add those too:
```
git add .
git commit -m "describe what you changed"
git push
```
