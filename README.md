# SaaS Components — Design System

A complete, token-driven UI kit built in **Figma**, designed for **Light and Dark**
themes from a single source of truth.

> Bu repozitoriya Figma'dagi **SaaS Components** design system loyihasini hujjatlashtiradi.
> Komponentlar Figma faylida chizilgan; bu yerda arxitektura va ulanish tafsilotlari saqlanadi.

## 🔗 Figma file

| | |
|---|---|
| **File** | SaaS Components — Design System |
| **URL** | https://www.figma.com/design/5TS1dryeRHqObCLaTXsET6 |
| **Owner** | Jaloliddin Otajonov (Pro team) |
| **Connection** | Figma MCP (remote) — verified via `whoami` |

The file is connected and edited remotely through the official Figma MCP server,
so designs are generated and synced directly from this environment.

## 🎨 Token architecture

Everything is driven by **Figma Variables** (no hard-coded colors in components):

### `Primitives` collection — 91 variables (single mode)
- **Color ramps** (50→950): `gray`, `brand` (indigo), `blue`, `green`, `amber`, `red`
- **Base**: `white`, `black`
- **Spacing** (4px base): `0 … 24`
- **Radius**: `sm, md, lg, xl, 2xl, full`

### `Theme` collection — 35 semantic tokens × **Light / Dark** modes
Semantic tokens alias the primitives and flip automatically per mode:

| Group | Tokens |
|---|---|
| Background | `bg/canvas`, `bg/surface`, `bg/surface-hover`, `bg/surface-sunken`, `bg/inverse` |
| Border | `border/default`, `border/strong`, `border/focus` |
| Text | `text/primary`, `text/secondary`, `text/muted`, `text/inverse`, `text/link` |
| Primary | `primary/default`, `primary/hover`, `primary/active`, `primary/fg`, `primary/subtle` |
| Status | `success/*`, `warning/*`, `danger/*`, `info/*` (default / fg / subtle / text) |

Each page has a **Light board** and a **Dark board**; the Dark board simply has the
`Theme` collection mode set to *Dark*, and every bound variable resolves accordingly.

## 🧩 Pages & components

**17 pages**, each with a **Light** and **Dark** board (token-driven). Researched against
Material Design 3 / MUI, DevExpress, Syncfusion, Vuetify, Quasar, PrimeVue, Element Plus
(see `COMPONENT_SPEC.md`).

| Page | Components |
|---|---|
| 📘 **Cover** | Branded title card |
| 🎨 **Foundations** | Color ramps, semantic tokens, typography scale (Inter), spacing, radius, elevation |
| 🧩 **Forms** | Buttons (6 variants · 3 sizes · states), inputs (default/focus/error/disabled/icon), select, search, textarea, checkbox, radio, switch, slider |
| 🧭 **Layout & Navigation** | Navbar, sidebar, tabs, breadcrumb, pagination, stepper, card, stat cards, dropdown menu, accordion, modal/dialog |
| 📊 **Data & Feedback** | Data table, badges (solid + subtle), alerts (4 status), toast, avatars (sizes/status/group), tooltip, progress, spinner, skeleton, empty state |
| 🧩 **Forms · Advanced** | Icon/FAB/split/segmented/group/loading buttons, input variants (filled/outlined/underlined/borderless), prefix/suffix/clearable/password/counter, validation (error/success/warning), floating label |
| 🔽 **Selects & Pickers** | Autocomplete, multi-select (+N), cascader/tree-select, OTP, number stepper, rating (full/half), knob, color picker |
| 📅 **Date & Time** | Date picker (full day-state matrix), date range, time picker (list + wheel), mini calendar |
| 📊 **Data Grid** | Toolbar, sortable headers, select-all + row selection, status/plan tags, expandable row + detail, summary row, pagination, batch bar, skeleton, empty |
| 📈 **Charts** | Bar, line/area (vector), donut & gauge (arc), sparkline stat cards, heatmap, horizontal & stacked bars |
| 🏷 **Tags, Tree & Timeline** | Tag variants (filled/outlined/subtle), badges (dot/count/status/ribbon), tree view, timeline (states), descriptions, statistic, result |
| 🔔 **Feedback & Overlays** | Drawer, bottom sheet, popover, tooltips (plain/rich), toast stack, banner, linear/circular progress, spinner sizes, skeletons |
| 🧭 **Navigation · Advanced** | App bars (small/large/search), nav rail, bottom nav, mega menu, context menu, command palette, speed dial, wizards (horizontal/vertical) |
| 📤 **Upload & Transfer** | Dropzone (idle/drag-over), file list (uploading/success/error), image grid, avatar upload, dual-list transfer |
| 🗂 **Kanban board** | 5-column board with rich cards (tags, assignees, due, progress, comments), toolbar |
| 📁 **File manager & Editor** | File explorer (tree + storage meter + grid) and rich-text editor (formatting toolbar + document) |
| 📆 **Scheduler & Gantt** | Weekly calendar with events + now-line, and a project Gantt chart with progress bars + milestone |
| 🧱 **Component Library** | **Real, reusable Figma components** (Assets panel) — see below |

## 🧱 Reusable component library

The showcase pages above are token-driven **frames** (documentation). The
**🧱 Component Library** page contains **true Figma Components / Component Sets**
with variant properties — these appear in the **Assets panel**, can be **instanced**
(drag-drop / copy as instance), expose **variant dropdowns**, and propagate master
edits to every instance. All are bound to the Theme tokens, so instances retheme with
Light/Dark automatically.

**83 components across 18 assets:**

| Asset | Variant properties |
|---|---|
| Button | Variant (Primary/Secondary/Outline/Ghost/Danger) × Size (sm/md/lg) — 15 |
| Tag | Style (Subtle/Filled/Outlined) × Severity (6) — 18 |
| Badge | Severity (Neutral/Primary/Success/Warning/Danger/Info) |
| Avatar | Size (xs/sm/md/lg/xl) |
| Input | State (Default/Focus/Filled/Error/Disabled) |
| Checkbox | State (Unchecked/Checked/Indeterminate) |
| Radio · Switch | State |
| Alert · Toast | Severity |
| Card | Variant (Elevated/Outlined/Filled) |
| Tab · Menu item | State |
| Icon button | Variant (Filled/Tonal/Outlined/Ghost) |
| Stat card | Trend (Up/Down) |
| Tooltip · Spinner · Progress bar | single components |

## ✅ Conventions

- **Typeface:** Inter (Regular / Medium / Semi Bold / Bold)
- **Auto layout** everywhere; components hug their content
- **Colors are bound to variables only** — switching a frame's `Theme` mode is enough to retheme it
- Naming uses `/` grouping (e.g. `Button / Primary`) for organized asset panels
