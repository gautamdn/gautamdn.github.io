# Portfolio Redesign: Midnight Blue + Featured Projects

## Context

Gautam's portfolio site (gautamdn.github.io) is a single-page HTML site that needs to stand out as a senior engineering leader who actively ships products. The current site has a green terminal aesthetic on a light background — functional but doesn't convey the right level of gravitas. Several project updates are also needed: GitaFlow is in App Store review, Jeopardy Tracker is being replaced, and a new Jeopardy Prep app is in progress.

**Goal:** A visitor should think "this person ships" within 30 seconds.

---

## Theme: Midnight Blue

**Color palette swap — no structural changes to the theme system.**

| Variable | Current | New |
|----------|---------|-----|
| `--bg` | `#f4f4f0` | `#0d1117` |
| `--surface` | `#ffffff` | `rgba(255,255,255,0.03)` |
| `--surface-hover` | `#fafaf7` | `rgba(255,255,255,0.06)` |
| `--border` | `#d8d8d0` | `rgba(255,255,255,0.08)` |
| `--text` | `#111111` | `#e2e8f0` |
| `--text-dim` | `#555555` | `#94a3b8` |
| `--accent` | `#0a8f5c` | `#63b3ed` |
| `--accent-light` | `rgba(10,143,92,0.06)` | `rgba(99,179,237,0.12)` |
| `--accent-border` | `rgba(10,143,92,0.2)` | `rgba(99,179,237,0.25)` |
| `--grid-color` | `rgba(0,0,0,0.04)` | `rgba(99,179,237,0.07)` |

**Background:** Linear gradient `135deg, #0d1117 → #161b22 → #1a1a2e → #16213e`.

**Typography:** Unchanged — JetBrains Mono + Space Grotesk. Colors invert for dark mode.

**Nav:** Same glass effect with `backdrop-filter: blur`, background changes to `rgba(13,17,23,0.85)` (dark transparent instead of white transparent).

**Dot grid:** Kept, recolored to subtle blue.

**Animations:** All existing animations (fadeUp, blink, pulse, fade-in) remain unchanged.

---

## Hero Section

**Structure stays the same. Two content changes:**

1. **Heading:** Change from `Hey, I'm gautamdn` to:
   - `Hey, I'm Gautam Dambekodi`
   - Add subtitle line: `a.k.a. gautamdn` in monospace, dimmed color
2. **All other content unchanged:** Bio paragraph, role chips, CTA buttons. Just re-themed.

---

## Projects Section: Featured + Grid

This is the main structural change. Replace the current stacked list of 6 cards with a **featured card + grid of 5 cards** (3 top row, 2 bottom row centered, or wrapping naturally).

### Featured Card (GitaFlow)

- Large card spanning full width
- Left blue accent bar (3px solid `--accent`)
- Layout: screenshot placeholder (220×150px) on the left, content on the right
- Title + "in app store review" status badge (blue background, like deployed but distinct)
- Full description, tech stack badges, GitHub link
- Screenshot slot: user will provide an app screenshot image

### Grid Cards (4 projects, 2×2)

Compact cards for: **Katha**, **Learn Indian Languages**, **Mann Shanthi**, **Gambling AI**, **Jeopardy Prep**

Each card contains:
- Emoji icon + title + status badge (top row)
- Short description (trimmed from current — 1-2 lines max)
- Tech stack badges
- Link (GitHub or live URL)

**Status badges:**
- `deployed` — green (`rgba(34,197,94,0.1)`, text `#22c55e`)
- `live` — same green, used for Learn Indian Languages (links to Netlify)
- `wip` — yellow/amber (keep current styling)
- `in app store review` — blue (`--accent-light`, text `--accent`)

### Jeopardy Prep (Grid Card)

- Joins the grid as a 5th card — grid becomes 3 top + 2 bottom (or 2×3 with last row centered)
- Emoji: 🧠
- Status badge: `live` (green, same as Learn Indian Languages)
- Description: "A lovable Jeopardy preparation app — practice clues, track your progress, and sharpen your trivia game."
- Link: `jeopardy-whiz.lovable.app`
- Tech stack: `lovable`

### Removed

- **Jeopardy Tracker** — removed entirely

### Mobile Responsive

- Featured card: stacks vertically (screenshot above content)
- Grid: collapses to single column

---

## Ideas Section

No structural changes. Theme only:
- Card backgrounds: `rgba(255,255,255,0.03)` with `rgba(255,255,255,0.08)` border
- Text colors adapt to dark mode
- Add subtle `// more ideas coming soon` centered text below the card

---

## About Section

No structural changes. Theme only:
- Same two-column layout (bio text + 2×2 stats grid)
- Stat cards: dark surface background with blue accent numbers
- Mobile: stacks to single column (keep current breakpoint at 768px)

---

## Contact Section

No structural changes. Theme only:
- Same 4 link cards (GitHub, LinkedIn, X, Email)
- SVG icons carry over from current site, recolored for dark theme
- Hover states adapt to dark surface colors

---

## Footer

- Copyright text dimmed (`#4a5568`)
- Pulse dot: green → blue (`#63b3ed`)
- "always shipping" text stays

---

## Terminal Block

The decorative `$ ls ./projects` terminal block at the bottom of the projects section:
- Update to remove `jeopardy-tracker/` and add `jeopardy-whiz/`
- Restyle for dark theme (should look natural on dark background)

---

## Files to Modify

- `/Users/gautamdambekodi/repos/gautamdn.github.io/index.html` — the only file. All CSS and HTML are inline.

---

## Out of Scope

- No new files (keep single-file architecture)
- No JavaScript changes (animations, intersection observer, email protection all stay)
- No new fonts or external dependencies
- Screenshots will be added by the user later — just ensure the layout supports them with placeholder styling
- No content rewrites beyond what's specified (hero name, project status updates, Jeopardy swap)

---

## Verification

1. Open `index.html` in a browser — verify midnight blue theme renders correctly
2. Check all sections render on desktop (1200px+) and mobile (375px)
3. Verify featured card layout with screenshot placeholder
4. Verify grid cards display correctly at 2×2 on desktop, 1×1 on mobile
5. Verify Jeopardy Prep card appears in grid with "live" badge linking to jeopardy-whiz.lovable.app
6. Verify Jeopardy Tracker is fully removed
7. Verify GitaFlow shows "in app store review" badge
8. Verify Learn Indian Languages links to netlify.app URL with "live" badge
9. Verify nav glass effect works on dark background
10. Verify all animations still function (fadeUp, scroll fade-in, cursor blink, pulse)
11. Verify dot grid is visible but subtle in blue
