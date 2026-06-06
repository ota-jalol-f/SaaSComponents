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

| Page | Components |
|---|---|
| 📘 **Cover** | Branded title card |
| 🎨 **Foundations** | Color ramps, semantic tokens, typography scale (Inter), spacing, radius, elevation |
| 🧩 **Forms** | Buttons (6 variants · 3 sizes · states), inputs (default/focus/error/disabled/icon), select, search, textarea, checkbox, radio, switch, slider |
| 🧭 **Layout & Navigation** | Navbar, sidebar, tabs, breadcrumb, pagination, stepper, card, stat cards, dropdown menu, accordion, modal/dialog |
| 📊 **Data & Feedback** | Data table, badges (solid + subtle), alerts (4 status), toast, avatars (sizes/status/group), tooltip, progress, spinner, skeleton, empty state |

## ✅ Conventions

- **Typeface:** Inter (Regular / Medium / Semi Bold / Bold)
- **Auto layout** everywhere; components hug their content
- **Colors are bound to variables only** — switching a frame's `Theme` mode is enough to retheme it
- Naming uses `/` grouping (e.g. `Button / Primary`) for organized asset panels
