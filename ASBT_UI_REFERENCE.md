# ASBT — UI Reference (observed from product screenshots)

> Memory note for the design team / Claude. The **ASBT** cadastre-registry app is the
> structural reference our Figma project should follow **everywhere** (tab panels, split
> panels, borders, paddings, table conventions). This file records what was identified
> from the supplied screenshots so future screens can be matched consistently.

## Screens captured so far
1. **Main data window** (`e3f74959-3146.jpg`) — empty list state ("Ma'lumot topilmadi").
2. **"Shaxsga tegishli xonadonlar" modal** (`36576494-3147.jpg`) — modal over the main window.

Figma recreations live on page **`🖥 ASBT · Reference`** (frames `ASBT — Main` and `ASBT — Modal`).

## Global layout (top → bottom)
1. **App-shell navbar** — full-width, dark navy, ~48px. Left: home icon · `ASBT` brand (shield badge) · "Navigatsiya" search pill (`⌘K`). Right: `uz O'zb` language · dark-mode moon · user chip (`FO Foydalanuvchi`, blue avatar) · `Chiqish` (logout).
2. **Kadastr form row** — white card, border, radius ~8. `Uy kadastr №:` label + monospace input "Kadastr raqamini kiriting" + enter/return icon button. Far right: 4 blue outline icon buttons (info · group · layers · person).
3. **Status metrics row** — left muted hint "kadastr raqami kiritilmagan". Right: 4 metrics `Umumiy maydon`, `Doimiy ro'yxatda`, `Vaqtincha ro'yxatda` (amber), `Bo'sh maydon` (red) each `– m²`.
4. **Action toolbar** — bordered rounded container, small gap. Buttons L→R: refresh ⟲ · **primary blue** "Yangi so'rovnoma yaratish" (download icon) · `ФБШ` · `IR` · "Kartoteka uchun qo'shish" · camera · "Chop etish varaqalari"/print · `F-17` · 2 icon buttons. Right: **green** "'Face' tasdiqlash" · **red/coral** "'Face' bekor qilish".
5. **Body = TabPanel + table** — left **vertical tab strip** (~32px) with rotated labels: "Ro'yxatga olishga so'rovnomalar" (active) / "Ro'yxatga olinganlar". Main panel = white card titled **"Doimiy ro'yxatga olish uchun so'rovnomalar"** with a **grouped-header data table**.
6. **SplitPanel divider** — a thin horizontal divider with a centered collapse button (chevron `˅`) between the main table and the bottom panel.
7. **Bottom panel** — "Jarayonlar ro'yxati" table.
8. **Footer bar** — `v0.0.3` · center "2026 Technologic ASBT. Barcha huquqlar himoyalangan." · right status "Ma'lumot yo'q | Lug'atlar: 121 ta | Oxirgi yangilanish: 6/10/2026 …".

## Data-table conventions
- Header text: UPPERCASE, ~10–11px, letter-spaced, muted grey `#9AA3B0`, on a light-sunken header band.
- **Grouped headers**: a spanning group label (e.g. `SHAXS MA'LUMOTLARI`, `ASOSIY HUJJAT`) sits on top of its sub-columns. Two-row header.
- Main table columns: `HOLAT · JSHSHIR · [SHAXS MA'LUMOTLARI: FAMILIYA · ISM · OTASINING ISMI · TUG'ILGAN SANA] · [ASOSIY HUJJAT: HUJJAT TURI · SERIYA VA RAQAM] · ISTISNO SABABI · RO'YXAT SANASI · KELISH BANDI · SO'ROV HOLATI`.
- Process table columns: `JARAYON KODI · JARAYON TURI · BOSHLANGAN SANA · TUGALLANGAN SANA · JARAYON NATIJASI · MA'LUMOTLAR · KETGAN VAQT · JARAYON HOLATI`.
- Thin 1px column separators; **empty state** = centered magnifier icon + "Ma'lumot topilmadi" (muted).
- Table footer: `Jami: N` left, pagination chip (active page = filled blue) right.

## Modal conventions ("Shaxsga tegishli xonadonlar")
- Centered, white, radius ~12, drop shadow, over a dim scrim. Width ≈ 480–520px.
- **Header**: title (dark, slightly bold) + `✕` close (top-right).
- **Body**: caption "ID karta, pasport yoki yashash guvohnomasi" → form row `Hujjat №` input · `Tug'ilgan sana` (DD.MM.YYYY) input · blue search icon button → divider → section title "Shaxsga tegishli xonadonlar ro'yxati" → sub-table (`KADASTR RAQAMI` · `VILOYAT`) with its own centered empty state + right scrollbar → "Pasport-Viza" tab/label.
- **Footer**: green primary "Tanlangan kadastr bilan ishlash (F5)" + outline "Yopish".

## Observed palette (hex, approximate)
| Token | Hex | Use |
|---|---|---|
| nav-bg | `#0F1B2E` | dark navbar |
| nav-text | `#C8D0DC` | navbar text |
| canvas | `#F5F6F8` | page background |
| surface | `#FFFFFF` | cards / panels |
| sunken | `#F0F2F5` | table header band |
| border | `#E5E8EC` | dividers / card borders |
| border-strong | `#D4D8DF` | input borders |
| text-primary | `#232A35` | titles / values |
| text-secondary | `#5A6472` | body |
| text-muted / header | `#9AA3B0` | labels, table headers |
| primary (azure) | `#3E78D6` | primary buttons, links, active page |
| primary-subtle | `#EAF1FC` | active tab / hover |
| success (green) | `#5BC4A4` | "Face tasdiqlash", confirm |
| danger (coral) | `#E08A80` | "Face bekor qilish", cancel |
| metric-amber | `#E0913C` | "Vaqtincha ro'yxatda" |
| metric-red | `#D45B52` | "Bo'sh maydon" |

> NB: the app's primary is **azure `#3E78D6`** (vs. the component-library indigo `#4A55A8`).
> Keep ASBT recreations on this azure so they read as the real product.

## Spacing / border conventions
- Card radius **8px**, modal radius **12px**, button/input radius **6–8px**.
- Card/panel border **1px** `#E5E8EC`. Section padding **12–16px**. Toolbar item gap **6–8px**.
- Control height ~**32–34px**. Font: **Inter** throughout.
- Density is **compact** (enterprise grid app) — tight row heights, small type.

## Reusable ASBT component kit (Assets panel — page `🧩 ASBT UI Kit`)

The reference screens are assembled from **instances** of these reusable components. Reuse
them on every new ASBT screen; if a needed component is missing, add it here and instance it.

| Component | Type | Notes |
|---|---|---|
| **ASBT / Button** | Set · `Type=Primary/Secondary/Success/Danger` | azure / outline / green / coral; editable `label` |
| **ASBT / Toolbar button** | Set · `State=Default/Active` | bordered toolbar action |
| **ASBT / Icon button** | Component | square outline icon button (`icon` text) |
| **ASBT / Input** | Component | bordered field, editable `placeholder`, resizable width |
| **ASBT / Metric** | Component | `label` + `value` (status-row metric) |
| **ASBT / Page chip** | Set · `State=Default/Active` | pagination chip |
| **ASBT / Side tab** | Set · `State=Active/Default` | **vertical side tab** — fixed center-aligned rotated label box so any `label` stays readable & centered |

### Active Side-tab geometry (important — it's a *tab shape*, not a flat rectangle)
The **active** tab has the classic "tab-with-ears" shape that connects into the content panel:
- **2 × 14px** rounded corners on the **outer (left)** edge.
- **2 × 11px concave "ears" (quloq)** at the **content (right) junction** — top-right and
  bottom-right curve outward to blend the tab into the panel.
- Built as a vector (44 × 190 strip), fill azure-subtle `#EAF1FC`, 3px azure left accent,
  azure Semi-Bold label. Default tab = plain white strip + right border + grey label.
- Vector path: `M 0 25 Q 0 11 14 11 L 33 11 Q 44 11 44 0 L 44 190 Q 44 179 33 179 L 14 179 Q 0 179 0 165 Z`
  (outer corners use the 14px Q-radius; the two `Q 44 …` segments are the 11px ears).

> **Side tab fix:** earlier the vertical tab was an ad-hoc rotated text that looked cramped /
> "chrome-like" and unreadable. It's now a proper reusable component: a 40px strip with a
> **fixed-size, center-aligned, rotated label**, clear Active/Default states. The TabPanel is
> just a vertical stack of two `ASBT / Side tab` instances.
>
> Per-instance label **position can't be overridden**, so the label must be a fixed-size
> centered box (not auto-resize) — that's why the component uses `textAutoResize='NONE'` +
> `textAlignHorizontal='CENTER'`. Only `characters` (and fills) are overridden per instance.

## Modules observed (same shell, different table/title/action)

The app reuses ONE shell (navbar → form → metrics → toolbar → Side-tab TabPanel + table →
SplitPanel → process table → footer) across modules. Only the **title, primary action, and
table columns** change. Modules captured so far:

| Module | Table title | Primary action | Toolbar notes | Figma frame |
|---|---|---|---|---|
| **Permanent reg.** | "Doimiy ro'yxatga olish uchun so'rovnomalar" | "Yangi so'rovnoma yaratish" | `ФБШ` (Cyrillic) · IR | `ASBT — Main` |
| **Residence reg. (ALT)** | "Turish joyi bo'yicha ro'yxatga olish uchun so'rovnomalar" | "Yangi ALT so'rovi" | `FBSh` (Latin) · IR | `ASBT — Turar joy (ALT)` |

Both modules share the **same two Side tabs**: "Ro'yxatga olishga so'rovnomalar" (active) /
"Ro'yxatga olinganlar" — this confirms the vertical Side-tab design is correct.

**ALT module columns — NOT fully legible** (photo was angled/blurry). Partially read:
`SO'ROV HOLATI · SHAXSIY RAQAMI · [SO'ROVNOMASI… (group): FAMILIYA (KIRIL…) · …]`. The ALT
frame currently reuses the permanent-reg columns as a placeholder — **needs a clear,
straight-on screenshot of the ALT table header to finalize the exact columns.**

## TODO / to confirm on next screenshots
- Populated table rows (row striping, selected row, status pills in `HOLAT` / `SO'ROV HOLATI`).
- Hover/active states for toolbar buttons & tabs.
- Exact metric formatting and any filled-data modal states.
- Whether the left TabPanel has more than two tabs in other modules.
