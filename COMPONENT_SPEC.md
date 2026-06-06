# Component Build Spec — SaaS Components

Consolidated from a deep-research pass across **Material Design 3 / MUI (+ MUI X)**,
**DevExpress DevExtreme**, **Syncfusion**, **Vuetify 3**, **Quasar**, **PrimeVue**, and
**Element Plus** (cross-checked vs Ant Design, Carbon, Polaris, Chakra).

This is the master checklist for the premium Figma library. Every component is built
**token-driven** with **Light + Dark** boards.

## Global conventions
- **Sizes:** `xs · sm · md(default) · lg · xl` (density model: comfortable/default/compact)
- **Interaction states:** enabled · hover · focus-visible · active/pressed · disabled · read-only · loading
- **Validation states (form):** default · error · success · warning
- **Variant consensus:** buttons `primary/secondary/tertiary/outlined/ghost/link/danger`; cards `elevated/outlined/filled`; alerts/toasts `info/success/warning/danger/neutral`
- **RTL-ready:** leading/trailing icon slots

---

## Build progress (Figma pages)
Built: Cover · Foundations · Forms · Layout & Navigation · Data & Feedback ·
**Forms · Advanced** · **Selects & Pickers** · **Date & Time** · **Data Grid** · **Charts**.
In progress: Tags/Tree/Timeline · Feedback & Overlays · Navigation Advanced · Upload & Transfer · Enterprise.

## Status legend: [x] built · [ ] planned

### Foundations  `[x]`
- [x] Color ramps + semantic tokens (Light/Dark), typography, spacing, radius, elevation

### Forms — basic  `[x]`
- [x] Button (6 variants · 3 sizes · states), Input (states), Select, Textarea, Search, Checkbox, Radio, Switch, Slider

### Forms — advanced  `[ ]`
- [ ] Button extras: icon-only, FAB (sm/md/lg + extended), Split button, Button group / Segmented, Loading button
- [ ] Input variants: filled · outlined · underlined · borderless; with prefix/suffix, clearable, password reveal, char counter
- [ ] Validation states: error / success / warning with helper text + floating label
- [ ] Autocomplete / Combobox (suggestions, async loading, creatable)
- [ ] MultiSelect (chips + `+N` overflow, select-all)
- [ ] TreeSelect / Cascader (multi-level)
- [ ] OTP input, Number stepper input, Input mask
- [ ] Rating (full + half), Knob (circular input)
- [ ] Color picker, Transfer (dual-list shuttle)
- [ ] File upload / Dropzone (idle · drag-over · uploading · file-list · error)

### Date & Time  `[ ]`
- [ ] Date picker (calendar popover: today/selected/range/disabled/other-month day states)
- [ ] Date range picker, Time picker, Mini calendar, Full calendar with events

### Data display — basic  `[x]`
- [x] Data table (avatar/status/value), Badges, Alerts, Toast, Avatars, Tooltip, Progress, Spinner, Skeleton, Empty state

### Data — advanced  `[ ]`
- [ ] DataGrid (toolbar search/filter, select-all + batch bar, sortable headers, density, zebra, sticky header, selected row, expandable row, inline edit, pagination footer, skeleton loading, empty)
- [ ] Tag variants (filled/outlined/subtle × severities, removable, with avatar)
- [ ] Badge variants (dot / count `99+` / status / ribbon)
- [ ] TreeView, TreeTable
- [ ] Timeline (vertical, states: completed/active/pending/error)
- [ ] Descriptions list, Statistic cards, Result page
- [ ] Kanban board (columns + cards)

### Layout & Navigation — basic  `[x]`
- [x] Navbar, Sidebar, Tabs, Breadcrumb, Pagination, Stepper, Card, Stat card, Dropdown menu, Accordion, Modal

### Navigation — advanced  `[ ]`
- [ ] App bar variants (small / large / search / center)
- [ ] Nav rail (collapsed), Bottom navigation (mobile)
- [ ] Mega menu, Context menu, Command palette
- [ ] Steps / Wizard (horizontal + vertical with error state)
- [ ] SpeedDial / FAB menu, Tabs variants (line/pill/enclosed)

### Feedback & Overlays — advanced  `[ ]`
- [ ] Drawer / Sheet (side), Bottom sheet
- [ ] Popover (header/footer), Tooltip (plain + rich)
- [ ] Toast stack (severities × positions), Snackbar with action, Banner
- [ ] Progress: linear + circular (determinate/indeterminate), Spinner sizes
- [ ] Skeleton variants (text/rect/circle/card)

### Charts & Data-viz  `[ ]`
- [ ] Bar, Line/Area, Pie/Donut, Sparkline, Gauge, Progress ring, Heatmap, Stat + mini chart

### Enterprise / Premium  `[ ]`
- [ ] Kanban board, Scheduler (week view), Gantt timeline
- [ ] File manager, Rich text editor (toolbar + content), Dashboard layout sample

---

## Per-library premium highlights (reference)
- **MUI X:** DataGrid (Pro: pinning, tree data, master-detail, virtualization; Premium: row grouping, aggregation, pivoting, Excel export), Date/Time + Range pickers, Charts (bar/line/pie/scatter/sparkline/gauge/radar/heatmap/funnel/sankey), Tree View, Scheduler
- **DevExtreme:** DataGrid, PivotGrid, TreeList, Scheduler, Gantt, Diagram, HtmlEditor, FileManager, Charts/Gauges/Maps, Sankey/Funnel/TreeMap
- **Syncfusion:** DataGrid, Pivot Table, Tree Grid, Spreadsheet, Document Editor, PDF Viewer, Diagram, Gantt, Kanban, Scheduler, Rich Text Editor, Image Editor, Query Builder, File Manager, 50+ charts, Smart AI components (Smart TextArea/Paste, AI AssistView)
- **PrimeVue:** DataTable (frozen/grouping/lazy), Editor (Quill), Terminal, OrderList/PickList, Galleria, Stepper, Splitter, TieredMenu/MegaMenu/PanelMenu, Knob, MeterGroup, SpeedDial, Dock
- **Element Plus:** Cascader, Transfer, Virtualized Select/Table/Tree, Descriptions, Statistic, Result, Tour, Segmented, Watermark, Mention, Anchor, Affix, Backtop
- **Quasar:** QTable (all modes), QEditor (rich text), QUploader, QSplitter, QKnob, QColor, QCarousel, QStepper, QChatMessage
- **Vuetify:** v-data-table (client/server/virtual), v-sparkline, v-treeview, v-timeline, v-calendar, v-color-picker, v-otp-input, v-number-input
