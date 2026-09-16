# LoadMatch — Design System v2.0 ("Modern Trust")

Base design copied 1:1 from Cephasjr101/Empty-Trackload (original MVP): same color tokens, green primary buttons, system font stack.
Functional layer added on top (kept): dark mode, marketplace filters, order-tracking sections, skeletons, back-to-top.
Visual rule: if in doubt, match the original repo look — deep green (#0B3B2E family), green pill CTAs, system fonts.

## Brand

- **Product:** LoadMatch — Ghana's freight & empty-mile marketplace
- **Promise:** Post a load, get matched with a verified truck, track the order live door to door
- **Tone:** trustworthy, operational, direct. No emojis as icons. No neon. No purple/blue AI gradients.

## Typography

| Role | Font | Weights |
|---|---|---|
| Display (h1–h4, stats, routes, KPI numbers) | Sora | 600 / 700 / 800 |
| UI & body | Inter | 400 / 500 / 600 / 700 |

Loaded via Google Fonts with full system-font fallback stacks.

## Color

| Token | Value | Use |
|---|---|---|
| green-950 / 900 / 800 | #05201A / #0B3B2E / #0F5132 | Footer, hero, page-head bands, chat header |
| green-700 / 600 / 500 | #116B4F / #157A5B / #1E9E74 | Primary brand actions (secondary), badges, focus |
| green-300 / 100 / 50 | #7FD6B6 / #DDF2E9 / #F0FAF5 | Accents on dark, icon chip bg, table headers |
| amber-500 / 400 | #F59E0B / #FBBF24 | **Primary CTA** — buttons, active nav underline, accents |
| amber-bg / amber-ink | #FDE68A / #92400E | Amber soft badge, CTA text contrast |
| ink / muted / faint | #0F172A / #334155 / #64748B | Text hierarchy |
| line / bg / bg-soft | #E2E8F0 / #FFFFFF / #F6F9F7 | Surfaces |
| danger | #B91C1C (+ #FEE2E2 bg) | Errors, invalid fields |

### Dark mode
`data-theme="dark"` on <html>: surfaces #0A1F19 / cards #0F2A22, lines #274036, text #E8EEF2.
Toggle persists in localStorage (`lm_theme`), defaults to OS preference.

## Elevation & shape

- Radius: 10px (inputs) · 14px (cards) · 20px (page-head, chat panel)
- Shadows: sm (cards) → md (hover/popovers) → lg (chat panel); all green-tinted in light mode
- Focus ring: 4px rgba(17,107,79,.22) on form fields; 3px amber outline for keyboard nav

## Key components

- **Buttons:** pill-shaped. `.btn-primary` = amber (conversion), `.btn-ghost` = green outline (secondary). Hover lift + press shrink.
- **Page-head:** green gradient band with eyebrow label — every interior page's entry point.
- **Cards:** 1px line border, hover lift + border tint; `.card-head` (icon + route), `.card-foot` (price + CTA).
- **Badges:** uppercase pill with status dot — verified / pending / match / live / rejected.
- **Forms:** numbered `.form-section` groups + `.form-progress` step bar; inline `.field-error`; honeypot + math captcha preserved.
- **Tables:** green-50 header row, row hover, wrapped in `.table-wrap`.
- **KPI cards:** left gradient accent bar + icon chip.
- **Chat widget:** gradient FAB, rounded panel, quick replies (unchanged behavior).
- **Skeletons:** shimmer placeholder cards during API loads.
- **Utilities:** skip-link, back-to-top (bottom-left), cookie banner, `prefers-reduced-motion` everywhere.

## Accessibility checklist (pre-delivery)

- [ ] Text contrast ≥ 4.5:1 in both themes
- [ ] Visible focus states, skip-link present
- [ ] `aria-current="page"` on active nav item
- [ ] Badges don't rely on color alone (status dot + label)
- [ ] Reduced motion respected (animations off)
- [ ] Responsive: 375 / 768 / 1024 / 1440

## Anti-patterns (never do)

- Emojis as icons — use inline SVG (stroke 2, currentColor)
- Bright neon / purple-pink gradients — amber + deep green only
- Harsh animations — 150–250ms ease transitions only
- Hiding focus outlines
