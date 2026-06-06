# Internal Management Design System — Architecture

Premium, low-eye-strain design system for a data-heavy internal management
system (ERP / CRM). Built on a Token-tier + Atomic Design model, leveraging
Figma Pro (Variables, Component Properties, Interactive Components, Advanced
Auto Layout). Naming is code-friendly for Flutter implementation.

## 0. Token tiers & Figma Variable collections
- Tier 1 Primitives → raw values (never used directly in UI)
- Tier 2 Semantic → meaning aliases (Light/Dark mode switch here)
- Tier 3 Component → component-scoped (large components)

| Collection | Modes | Purpose |
|---|---|---|
| 1. Primitives | single | color/size scales |
| 2. Semantic | Light / Dark | theming |
| 3. Density | Compact / Comfortable / Spacious | data/form density |
| 4. Brand (optional) | Default / White-label | client theming |

## 1. Color — Low Eye-Strain & Premium

Principles: no pure #FFFFFF / #000000; warm-neutral off-white backgrounds;
graphite (not black) text; muted indigo brand; muted status colors
(sage / ochre / terracotta / steel-blue); target body contrast ~8–11:1.

### Primitives — Neutral (Slate, warm)
| Token | HEX | | Token | HEX |
|---|---|---|---|---|
| slate.0 | #FCFCFD | | slate.500 | #737B89 |
| slate.50 | #F6F7F9 (App bg Light) | | slate.600 | #565E6C |
| slate.100 | #EDEFF2 | | slate.700 | #3D4450 (Body text) |
| slate.150 | #E4E7EC | | slate.800 | #2A303A |
| slate.200 | #D6DAE1 (Border) | | slate.900 | #1E232C |
| slate.300 | #BFC5CF | | slate.950 | #14171D (App bg Dark) |
| slate.400 | #9AA1AD | | | |

### Primitives — Brand (muted Indigo)
brand.50 #EEF0FB · 100 #DEE2F6 · 200 #C2C9EE · 300 #9EA8E0 · 400 #7B86D2 ·
500 #5A66BE · **600 #4A55A8 (Primary)** · 700 #3C4688 · 800 #313A6C · 900 #28304F

### Primitives — Status (muted)
| Role | 50 (bg) | 500 | 700 (text) |
|---|---|---|---|
| Success (sage) | #E9F3EC | #4E9A6B | #356E4C |
| Warning (ochre) | #F8F0DD | #C2913B | #8A6520 |
| Error (terracotta) | #F8E9E7 | #C75A50 | #943F37 |
| Info (steel-blue) | #E8EFF6 | #4A82B8 | #335E88 |

### Semantic (Light / Dark)
| Token | Light | Dark |
|---|---|---|
| bg.app | #F6F7F9 | #14171D |
| bg.surface | #FCFCFD | #1B1F27 |
| bg.surface.raised | #FCFCFD | #222732 |
| bg.sunken | #EDEFF2 | #101319 |
| bg.hover | #EDEFF2 | #242A34 |
| bg.selected | #EEF0FB | #2A3050 |
| border.subtle | #E4E7EC | #262C36 |
| border.default | #D6DAE1 | #2F3641 |
| border.strong | #BFC5CF | #3C4450 |
| border.focus | #5A66BE | #7B86D2 |
| text.body | #3D4450 | #D5D9E0 |
| text.heading | #1E232C | #E8EBF0 |
| text.secondary | #565E6C | #9BA3B0 |
| text.muted | #9AA1AD | #6B7280 |
| text.onBrand | #F7F8FB | #F7F8FB |
| text.link | #4A55A8 | #9EA8E0 |
| action.primary.bg | #4A55A8 | #5A66BE |
| action.primary.hover | #3C4688 | #7B86D2 |

### Other foundations
- Typography: Inter / IBM Plex Sans; display 28/36, h1 22/30, h2 18/26, h3 16/24,
  body 14/22, body-sm 13/20, caption 12/18, mono 13/20; tabular-nums ON for data.
- Spacing (4px): 0 2 4 6 8 12 16 20 24 32 40 48 64
- Radius: xs4 sm6 md8 lg10 xl14 full999
- Elevation (soft): e1 0 1 2/6%, e2 0 4 10/8%, e3 0 12 24/10% (dark: border+raised bg)
- Density (Variable mode): row-height 36/44/52, field-height 32/40/48, cell-pad-x 8/12/16
- Motion: fast120 base180 slow240, cubic-bezier(.2,.6,.2,1)
- Z-index: base0 sticky100 dropdown1000 overlay1100 modal1200 toast1300

## 2. Naming & Flutter sync
- Component: `<Layer>/<Component>` (Atom/Field, Molecule/Input, Organism/DataGrid)
- States via Component Properties, not separate components
- Variant property → Dart enum; Boolean → bool; Text → String; Instance-swap → Widget?
- Tokens: dot.case (color.bg.surface, space.4, radius.md) → ThemeExtension + const
- Variant enum values map 1:1 to Figma variant names.

## 3. Deep components (20+ states each)

### Button
Variant: Type{Primary,Secondary,Tertiary,Ghost,Danger,Link}=6 ×
Size{SM,MD,LG}=3 × State{Default,Hover,Focus,Active,Disabled,Loading}=6 = 108.
Boolean: LeadingIcon, TrailingIcon, IconOnly, FullWidth (2^4). Text: Label.
Instance-swap: Icon. → 1700+ combinations.

### Input (deepest)
Variant: Size{SM,MD,LG}=3 × State{Default,Hover,Focused,Filled,Disabled,Read-only,
Error,Success}=8 = 24 base (already >20).
Boolean: ShowLabel, Required, LeadingIcon, TrailingIcon, ClearButton, Prefix, Suffix,
HelperText, Tooltip (2^9). Text: Label/Placeholder/Value/Helper/Prefix/Suffix.
Anatomy: [Label* + Tooltip] / [leading | prefix | input(fill) | clear | suffix | trailing] / [helper + counter].
State→token: Focused = border.focus + ring(brand 24%); Error = border.error; Read-only = no border + transparent.

### Dropdown / Select
Trigger reuses Input atom. Variant: State{Default,Hover,Focused,Open,Filled,Disabled,
Error}=7 × Selection{Single,Multi}=2 × Size=3 = 42. Boolean: Searchable, Clearable, LeadingIcon.
Menu organism: Option{Default,Hover,Focused,Selected,Disabled,with-checkbox,with-icon,
with-description}; Group header; Menu state{Loading,Empty,Error}; Select-all; sticky search.

### Checkbox
Variant: Value{Unchecked,Checked,Indeterminate}=3 × State{Default,Hover,Focus,Disabled,
Error}=5 × Size{SM,MD}=2 × LabelPosition{Right,Left}=2 = 60. Boolean: ShowLabel, HelperText.

### Toggle / Switch
Variant: Value{On,Off}=2 × State{Default,Hover,Focus,Disabled,Loading}=5 × Size{SM,MD,LG}=3
× LabelPosition=2 = 60. Boolean: IconsInThumb, ShowLabel.

## 4. DataGrid architecture (4 layers)

### Layer 1 — Cell atoms (17 types)
Text, Numeric(right, tabular), Currency, Badge/Status, Avatar+Name, Date(+relative/overdue),
Progress, Action-menu(kebab), Checkbox(+select-all), Inline-Input(edit), Inline-Select(edit),
Tag-list(+N), Rating, Link, Boolean(✓/✕/toggle), Thumbnail, Empty(—).
Cell wrapper handles [padding | content(fill/hug) | align] + Density mode.

### Layer 2 — Row (Organism)
Variant State{Default,Hover,Selected,Focused,Editing,Error,Disabled,Expanded,Dragging,
Loading}=10. Boolean: Zebra, Selectable, Expandable, Draggable. Variant Pinned{None,Top,Bottom}.
Density via Variable mode. State→token: Selected=bg.selected+2px brand left; Editing=ring;
Error=error.50+2px error left. Expanded opens a detail panel below (normal flow).

### Layer 3 — Header
HeaderCell: Sort{None,Asc,Desc}; Boolean Sortable, Filterable, FilterActive, Resizable,
HasMenu, SelectAll; Variant Pinned{None,Left,Right}(sticky), Align{Left,Right,Center}.
Sticky header (z sticky); pinned columns freeze on horizontal scroll (shadow); resize handle 4px.

### Layer 4 — Global (Template)
Toolbar: title+count, Search, Filter chips, Column chooser, Density toggle, Export(CSV/Excel/PDF),
Saved views, Refresh.
Bulk action bar (on selection): "N selected" + Delete/Export/Assign/Edit/Clear.
Filter panel: per-column conditions (= ≠ > contains between in), add/remove, Apply/Reset.
Pagination: rows-per-page, "1–25 of 1,248", ‹1 2 3 … 50›, go-to-page.
Grid states: Loading(skeleton rows), Empty(illustration+CTA), No-results, Error(retry).
Footer (optional): aggregation row (Sum/Avg/Count, sticky bottom).

Atomic summary: Atoms(17 cells + headercell + sorticon + resizehandle) → Molecules(Row,
HeaderRow, FilterCondition, PaginationControl) → Organisms(Toolbar, Body, BulkBar, FilterPanel,
Pagination) → Template(DataGrid). Flutter: DataGrid<T> with columns(cell-builders), rowState,
density, onSort/onFilter/onSelect.

## 5. Library structure (100%)
00 Foundations (Color, Typography, Spacing/Sizing/Radius/Elevation/Border, Density, Motion,
Z-index, Iconography, Grid/Breakpoints)
01 Atoms (Field, Label, Icon, Checkbox-box, Radio-dot, Switch, Badge, Tag, Avatar, Button-base,
Spinner, Skeleton, Divider, Tooltip, Chip, Progress, 17×Cell, SortIcon, ResizeHandle)
02 Molecules (Input, Textarea, Select, Multi-select, Combobox, Date-field, Number-stepper, Search,
Checkbox+label, Radio-group, Toggle+label, Button, Icon-button, Segmented, Menu-item,
Breadcrumb-item, Pagination-item, Form-field, Row, HeaderRow)
03 Organisms (Form-section, Toolbar, DataGrid(+sub), Filter-panel, Bulk-bar, Pagination-bar,
Modal, Drawer, Side-nav, Top-bar, Tabs, Card, Stat-card, Toast, Command-palette, Stepper)
04 Templates (List+Detail, Dashboard, Settings, Create/Edit form, Wizard, Empty/Loading/Error)
05 Pages (real example screens)

## 6. Figma Pro usage
Variables(4 collections, modes) = theme+density+brand swap; Component Properties =
variant+boolean+text+instance-swap (no variant explosion); Interactive Components =
hover/focus/press, dropdown open, row hover, tooltip; Advanced Auto Layout = fill/hug,
min/max width (columns), wrap (chips), absolute (corner badge), nested instances (DRY).
