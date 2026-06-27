---
name: qbem-design
description: Use this skill to generate well-branded interfaces and assets for QBem (Brazilian B2B benefits-management platform), either for production or throwaway prototypes/mocks/etc. Contains essential design guidelines, colors, type, fonts, assets, and UI kit components for prototyping.
user-invocable: true
---

Read the `README.md` file within this skill, and explore the other available files.

Key entrypoints:
- `colors_and_type.css` — source of truth for all design tokens (colors, fonts,
  scales, radii, shadows). Always `<link>` or `@import` this in any artifact
  you create.
- `assets/logo-qbem.svg`, `assets/symbol-smile.svg`, `assets/favicon-qbem.svg` —
  copy in directly, don't redraw.
- `assets/screens/` — production screenshots; use as visual reference for
  fidelity, never as a substitute for tokens.
- `ui_kits/qbem-admin/` — modular JSX components (Button, Input, Select, Card,
  StatCard, SectionBand, Modal, TopNav, etc.) plus screen-level recreations
  (login, dashboard, movimentações list, edit modal). Lift these into new
  artifacts rather than recreating them.
- `preview/` — small swatch/specimen cards documenting each token.

Visual non-negotiables:
1. **Font**: LINE Seed JP (Thin / Regular / Bold / ExtraBold only). Verdana is
   the system fallback for Office / e-mail contexts. Plus Jakarta Sans covers
   the missing Medium / Semibold weights when needed on web.
2. **Colors**: only use values from the three brand families (Petrol/Teal,
   Green, Lime) + the documented semantic tokens. Never invent hex codes.
3. **Icons**: Material Symbols Rounded (Google Fonts variable). Weights 100–700,
   grade −25 to 200. Never use Lucide, Heroicons, FontAwesome, or emoji as
   functional icons.
4. **Symbol**: the smile mark (`symbol-smile.svg`) is the brand's visual
   language, not just a logo. Use it cropped from frames, as a sticker, or
   tiled in backgrounds. Don't redraw it as a letter "B".
5. **Voice**: Portuguese (BR) primary, "você" not "vocês"/"tu", direct and
   efficient. Capitalize domain terms (Estipulante, Beneficiário, Operadora,
   Movimentação) as proper nouns.

If creating visual artifacts (slides, mocks, throwaway prototypes, etc), copy
assets out and create static HTML files for the user to view. If working on
production code, follow the project's stack conventions from CLAUDE.md.
