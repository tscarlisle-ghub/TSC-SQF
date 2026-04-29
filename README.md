# Construction Cost Estimator
### Carlisle Moore Architects — preliminary scope &amp; budget

A single-file, client-facing cost estimator for CMA's custom residential
projects in the Birmingham, Alabama market. Configures a project by bedroom
count, floor structure, finish level, and material selections, then shows
preliminary cost ranges across three tiers in real time.

## Live tool

Open `index.html` directly in any browser, or deploy via GitHub Pages
(the file has no build step and no server dependencies).

## What it does

- Bedroom stepper auto-populates a room list per CMA's `SAMPLE SPACE
  CALCULATIONS 2026` template.
- Each room has a slider (20% smaller to 50% larger than the starting
  size) plus typeable W and L inputs in whole-foot increments. Type any
  value to override the slider range.
- Stairs are based on a 5'×18' switchback assumption with a 5% growth cap.
- Modifiers: **Two-story**, **Basement**, and a 3-tier **Steep site**
  selector (Flat / Sloping / Steep at 0% / 4% / 8% surcharge).
- Material selectors:
  - **Exterior walls** — Painted brick, Wood siding, Brick, Reclaimed brick, Stone
  - **Roof** — Asphalt, Cedar shake, Slate
  - **Interior finish level** — Normal, Elevated, Custom
  - **Cabinetry &amp; millwork** — Normal, Semi-custom, Fully custom
- Cost summary shows all three tiers (Normally Nice / High / Very High)
  simultaneously. The under-roof $/sf is the contractor pricing baseline;
  conditioned $/sf is shown as a derived figure.

## Hosting on GitHub Pages

1. Create a public repo and add `index.html` (and optionally this `README.md`).
2. In the repo's **Settings → Pages**, set the source to your default branch
   (root). Save.
3. The tool will be available at
   `https://&lt;your-username&gt;.github.io/&lt;repo-name&gt;/`.

## Persistence

Configuration is saved to your browser's `localStorage` automatically on
every change. Reloading the page restores your last state. Use the **Reset**
button to discard the saved state and return to defaults.

`localStorage` is per-browser-per-device — data does not sync between machines.
To carry a configuration to another device, use **Export to Excel** and reopen
the file there.

## Outputs

- **Print &middot; PDF** — uses the browser's print dialog with a custom
  print stylesheet that hides interactive UI; choose "Save as PDF" to get
  a clean printable snapshot.
- **Export to Excel** — downloads `CMA-Cost-Estimate.xlsx` with three
  sheets: Setup, Rooms (editable W &amp; L with formulas for SF and totals),
  and Costs. Styled with **Seaford** as the base font.

## Pricing data

Tier ranges and material adjustments are derived from recent CMA project
bids (Young, Ray, Taylor, Davis, Stratas) covering multiple bidders per
project. Numbers reflect construction cost only — no land, design fees,
pools, landscaping, furnishings, or sales tax.

Tier $/sf are expressed against **under-roof SF** (the metric contractors
use); a 15% uplift on summed conditioned room SF accounts for wall
thicknesses and miscellaneous circulation, matching CMA's standard area
calculation.

| Tier | $/sf under roof |
|---|---|
| Normally Nice | $315 – $345 |
| High | $350 – $390 |
| Very High | $420 – $465 |

To tune: edit the `TIERS` and `MATERIALS` blocks at the top of the
`<script>` in `index.html` — single source of truth.

## Dependencies

- **Adobe Typekit** kit `ikf0hkb` — used for Interstate Condensed (tier
  labels, floor headings) and Trajan Sans (firm name).
- **ExcelJS 4.4.0** via cdnjs — loaded on demand only when "Export to Excel"
  is clicked.

## Files

- `index.html` — the tool (HTML + CSS + JS in one file)
- `.session-notes.md` — running log of changes/instructions on this project
- `inputs/` — source GC estimates and CMA plan sheets used to derive pricing
- `SAMPLE- SPACE CALCULATIONS 2026.xlsx` — CMA's reference space-calculation sheet

## License

&copy; Carlisle Moore Architects, Inc. All rights reserved.
