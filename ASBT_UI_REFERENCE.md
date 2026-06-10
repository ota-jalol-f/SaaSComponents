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

## TODO / to confirm on next screenshots
- Populated table rows (row striping, selected row, status pills in `HOLAT` / `SO'ROV HOLATI`).
- Hover/active states for toolbar buttons & tabs.
- Exact metric formatting and any filled-data modal states.
- Whether the left TabPanel has more than two tabs in other modules.
