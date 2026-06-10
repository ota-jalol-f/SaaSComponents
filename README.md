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

## 📕 Storybook-style documentation

Every component family has its own **doc page** (`📕 Docs · {Component}`) modelled on
Storybook's Docs view. A **📕 Docs** landing page indexes all of them, grouped by
Actions · Forms · Data display · Feedback · Containers · Navigation.

Each doc page contains:

| Section | Contents |
|---|---|
| **Header** | Title, one-line description, status badges (Stable · Ready for dev · version · variant count) |
| **Preview** | A **live instance** of the real component pulled from the Assets library |
| **Props** | Table of variant & control properties — type, default, description |
| **Stories** | Every key state/variant rendered from the **real component** (not redrawn) |
| **Anatomy** | Numbered breakdown of the component's structural parts |
| **Usage** | Do / Don't guidance in paired columns |
| **Accessibility** | WCAG 2.2 AA notes (roles, keyboard, focus, contrast, touch targets) |
| **Code · Flutter API** | Copy-ready Flutter widget usage snippet |

**38 documentation pages** (37 components + the Overview index): Button, Input, Select,
Checkbox, Radio, Switch, Slider, Number stepper, Rating, Icon button, Segmented control,
Tag, Chip, Badge, Avatar, Status dot, Stat card, Skeleton, Empty state, Divider, DataGrid,
Tree, Calendar event, File item, Alert, Toast, Tooltip, Spinner, Progress bar, Progress
circular, Card, Accordion, Tabs, Menu item, Breadcrumb, Pagination, Step indicator.

## 🧩 Pages & components

**97 pages** (showcase boards + the documentation set + ten **🧩 Sets** volumes + eight
**🧬 Unique** archetype pages), token-driven across **Light, Dark and High-contrast**.
**1,520 build-ready Figma components** across **294 component sets** live in the Assets panel. Researched against
Material Design 3 / MUI, DevExpress, Syncfusion, Vuetify, Quasar, PrimeVue, Element Plus,
Ant Design, Carbon, Chakra and Radix (see `COMPONENT_SPEC.md`).

### 🧬 Unique component archetypes (research-driven)

After a deep-research pass across **Material/MUI X, Ant Design, Carbon, Fluent, Chakra,
Mantine, Radix, shadcn, PrimeReact/Vue, DevExpress DevExtreme, Syncfusion, Vuetify,
Quasar, Element Plus, Bootstrap, Polaris** and the data-viz literature, we identified and
built the **structurally-distinct archetypes** the library was missing — each one a genuinely
different structure/behaviour, not a restyled pill/chip/row. **82 unique types across 8
"Unique" pages:**

| Page | Archetypes |
|---|---|
| **Unique I · Charts** | Line, Area, Bar, Grouped bar, Stacked bar, Pie/Donut, Scatter, Bubble, Radar, Histogram — all with real axes & gridlines |
| **Unique II · Charts+** | Treemap, Sankey, Funnel, Waterfall, Candlestick, Box plot, Bullet, Heatmap matrix, Calendar heatmap, Gauge cluster (speedometer) |
| **Unique III · Pickers** | Color picker (SV + hue), Date-range (dual month), Time wheel, Cascader, Emoji picker, Phone input, Query builder, Key-value editor, Signature pad, Markdown editor |
| **Unique IV · Data** | Pivot table, Tree table, Spreadsheet (formula bar), Master-detail grid, Org chart, Flow node, Network graph, Kanban board, Gantt chart, Scheduler grid |
| **Unique V · Media** | Video player, Audio waveform, Image carousel, Image cropper, Before/after slider, Galleria, PDF viewer, Map, Code editor (syntax), Diff viewer |
| **Unique VI · Layout** | Split pane, Dock, Command palette, App shell, Email layout, Onboarding checklist, Order tracker, Seat map, Booking grid, Anchor TOC |
| **Unique VII · Widgets** | Calculator, Dialer, Weather, Stock ticker, Analog clock, Compass, Equalizer, Terminal, Transfer shuttle, Stat scorecard |
| **Unique VIII · More** | Chord diagram, Wind rose, Pareto, Choropleth, Violin plot, JSON tree viewer, Cron builder, Mind map, Swimlane/BPMN, Timeline scrubber, QR code, Comment thread |

Charts and diagrams are drawn from real vectors / arcs and bound to the **Data-viz** token
collection (colorblind-safe Wong / Viridis / RdBu palettes).

### 🧩 Component-set volumes (Assets panel)

Beyond the documented core families, **ten "Sets" pages** add deep, real variant sets
covering the long tail a production SaaS needs — each a true Figma Component Set with
variant properties:

| Volume | Families |
|---|---|
| **Sets II** | Link, Kbd, Inline code, FAB, Split button, Button group, Avatar group, List item, Notification item, Timeline item, Banner, Snackbar, Description item, Meter |
| **Sets III** | Toolbar button, Toggle button, Color swatch, OTP digit, PIN field, Tag input, Search bar, Combobox option, Carousel dot/control, Gallery thumb, Nav item, Nav rail item, Bottom nav item, Command item, Dock item |
| **Sets IV** | Pricing card, Feature card, Profile card, KPI tile, Gauge, Legend item, Heatmap cell, Progress steps, Wizard step, Chat message, Blockquote, Callout, Knob |
| **Sets V** | Like, Bookmark, Follow, Copy, Vote, Reaction, Attachment, Mention, Priority, Currency, Version, Git branch, CI status, PR status, Country, Severity icon |
| **Sets VI** | Dropdown trigger, Popover, Context menu item, Tooltip bubble, Modal header, Sheet grabber, Editor tab, Mega menu item, Sidebar group header, Account switcher, Notification bell, Theme toggle, Avatar upload, Logo lockup, Scrim |
| **Sets VII** | Textarea, Form field, Field label, Help text, Range slider, Date/Time input, Password input, Checkbox/Radio card, Switch row, Upload zone, Slider · value, View switcher |
| **Sets VIII** | Sparkline, Mini bar chart, Donut mini, Trend arrow, Key-value row, Data badge, Activity item, Audit log row, Comparison bar, Rating display, Tag overflow, Avatar + label, Status node, Progress label, Empty cell, Summary cell |
| **Sets IX** | Cookie consent, Feedback face, NPS score, Survey option, Poll bar, Quiz option, Achievement badge, Streak counter, Credit chip, Leaderboard row, Level bar, Milestone, Countdown unit, Inline edit, Color input, Badge ribbon, Tour step, Hotspot, Skeleton card |
| **Sets X** | Multiselect token, Transfer item, Tree checkbox node, Calendar nav, Weekday header, Timezone chip, Filter group header, Sort menu item, Density toggle, Zoom control, Rows per page, Page jump |

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
