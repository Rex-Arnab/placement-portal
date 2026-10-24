# Placement Portal

A placement portal for tracking job applications through their stages, from applied to hired.

Built with Next.js 16, React 19, Tailwind CSS v4 and TypeScript.

## Getting started

This project uses Yarn 1 (`packageManager: yarn@1.22.22`).

```bash
yarn install
yarn dev
```

Open [http://localhost:3000](http://localhost:3000). Edit `app/page.tsx`; the page reloads as you save.

| Command      | What it does               |
| ------------ | -------------------------- |
| `yarn dev`   | Start the dev server       |
| `yarn build` | Build for production       |
| `yarn start` | Serve the production build |
| `yarn lint`  | Run ESLint                 |

## Design system

> **Status:** the tokens below are the target design. They are **not in the code yet**.
> `app/globals.css` still has the create-next-app defaults, and `app/layout.tsx` still loads Geist.
> The tokens were drafted as a Tailwind v3 `tailwind.config.js`. This project runs Tailwind v4,
> so they must go into `app/globals.css` as an `@theme` block instead.

### Colours

| Token       | Value                 | Use                                                                 |
| ----------- | --------------------- | ------------------------------------------------------------------- |
| `action`    | `#346B63`             | Primary actions (hover `#2B5A53`, active `#234A44`, soft `#E9F4EE`) |
| `emphasis`  | `#1A3332`             | Navigation, dark hero                                               |
| `highlight` | `#DFEEA4`             | Accent                                                              |
| `canvas`    | `#F5F7FA`             | Page background                                                     |
| `surface`   | `#FFFFFF`             | Cards, fields                                                       |
| `ink`       | `#1D2E33`             | Primary text (muted `#5B6B70`, subtle `#8A979B`)                    |
| `line`      | `#DCE1E4`             | Borders (strong `#C5CDD1`)                                          |
| `disabled`  | `#DDE4E7` / `#7D8A8F` | Disabled background / text                                          |

### Badges and application stages

Each badge tone has a background and a text colour. Always pair them.

| Tone     | Background | Text      | Stages                      |
| -------- | ---------- | --------- | --------------------------- |
| `gray`   | `#F5F7FA`  | `#5B6B70` | Applied, Withdrawn          |
| `blue`   | `#EBF1FE`  | `#2F4FA8` | Review                      |
| `green`  | `#E9F4EE`  | `#2F6B55` | Shortlisted, Offered, Hired |
| `purple` | `#F1ECFB`  | `#6A4B9E` | Interview                   |
| `amber`  | `#FDF4DE`  | `#816124` | Needs review                |
| `red`    | `#FAEDF0`  | `#A3464D` | Rejected, errors            |

### Type

Font: **Manrope**. It is not loaded yet; load it with `next/font/google` in `app/layout.tsx`.

| Token     | Size / line height |
| --------- | ------------------ |
| `title`   | 30 / 40            |
| `heading` | 22 / 30            |
| `body`    | 16 / 24            |
| `ui`      | 14 / 22            |

### Layout

- Corner radius: 8px (buttons, fields, badges), 12px (cards), 16px (panels, hero cards).
- Sidebar width: 232px. Max app width: 1440px.
- Page margin: 40px on desktop, 20px on mobile.
- Minimum tap target: 44px.
- Breakpoints: 375, 390, 430 and 1440px.
- Focus: a 2px `action` outline with a 2px offset on `:focus-visible`.

### Components

Planned component classes: `.btn-primary`, `.btn-secondary`, `.btn-ghost` (grey when disabled),
`.badge`, `.field` (red border when `aria-invalid="true"`), `.field-label`, `.field-error`,
`.nav-item` (highlighted when `aria-current="page"`), `.card`, and `.metric-label` /
`.metric-value` / `.metric-hint`.

### Values to confirm

These colours were estimated from screenshots, not taken from Figma. Check them against Figma:

- Badge text colours
- `ink` muted (`#5B6B70`)
- `line` border grey (`#DCE1E4`)
