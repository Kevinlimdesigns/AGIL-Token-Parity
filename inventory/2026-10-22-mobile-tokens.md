# Mobile token inventory — 2026-10-22

- **Mobile file:** `e6RBhSWdLlLinhceozYLYe` (working file).
- **Library:** AOH UI/ShadCN component library, `IQxwVUqzckYn7u7nNhX6lF`. It is the only library linked to the mobile file.
- **Mode:** read-only. Nothing in Figma was changed.
- **Machine-readable copy:** `2026-10-22-mobile-tokens.json`.

This is a baseline of the tokens the mobile app uses. It is not yet a parity audit: the web dashboard has not been compared.

## Coverage by page

"Solid paints bound" means a fill or stroke bound to a variable. Counts include nodes inside component instances.

| Page | Nodes | Solid paints bound | Hardcoded | Paint style | Text with a style |
|---|---|---|---|---|---|
| [Comms](https://www.figma.com/design/e6RBhSWdLlLinhceozYLYe/AGIL-Mobile-App?node-id=735-39373) | 42,091 | 81.8% | 4,138 | 1,217 | 91.9% |
| [Recent](https://www.figma.com/design/e6RBhSWdLlLinhceozYLYe/AGIL-Mobile-App?node-id=4925-124137) | 4,638 | 86.8% | 290 | 108 | 88.8% |
| [Chat](https://www.figma.com/design/e6RBhSWdLlLinhceozYLYe/AGIL-Mobile-App?node-id=735-51530) | 58,649 | 69.0% | 8,090 | 4,724 | 74.5% |
| [Map](https://www.figma.com/design/e6RBhSWdLlLinhceozYLYe/AGIL-Mobile-App?node-id=808-6171) | 19,610 | 86.1% | 1,361 | 492 | 96.3% |
| [Incident](https://www.figma.com/design/e6RBhSWdLlLinhceozYLYe/AGIL-Mobile-App?node-id=735-47082) | 18,250 | 83.9% | 1,095 | 819 | 94.0% |
| [Directory](https://www.figma.com/design/e6RBhSWdLlLinhceozYLYe/AGIL-Mobile-App?node-id=850-11256) | 6,347 | 82.9% | 532 | 224 | 97.0% |
| **All six** | **149,585** | **77.7%** | **15,506** | **7,584** | **86.5%** |

## Tokens in use

### AOH semantic colours (49 of 106 used)

- **Background:** `color-bg`, `-subtle`, `-elevated`, `-strong`, `-disabled`, `-invers`, `-primary`, `-primary-active`, `-secondary`, `-success-strong`, `-success-muted`, `-success-muted-active`, `-error-strong`, `-error-muted`, `-warning-strong`, `-warning-muted`, `-info-strong`, `-info-muted`, `-interactive`, `-magic-muted-hover`.
- **Border:** `color-border`, `-hover`, `-disabled`, `-onColor`, `-focusRing-sidebar`, `-primary`, `-error`, `-interactive`, `-interactive-focus`.
- **Icon:** `color-icon`, `-muted`, `-disabled`, `-onColor`, `-primary`, `-error`, `-info`, `-interactive`.
- **Text:** `color-text`, `-muted`, `-disabled`, `-placeholder`, `-inverse`, `-onColor`, `-success`, `-primary`, `-error`, `-warning`, `-info`, `-interactive`.

The most-used tokens on every page are `color-icon`, `color-text`, `color-text-muted`, `color-bg-subtle`, `color-border` and `color-bg-primary`.

### AOH spacing, radius and size

- **Spacing:** `spacing-3xs`, `2xs`, `sm`, `md`, `lg`, `xl`, `2xl`.
- **Radius:**
  - Used: `radius`, `-sm`, `-lg`, `-button`, `-input`, `-iconButton`, `-focusRing`, `-dialog`, `-round`.
  - Never used: `radius-card`.
- **Size:** `size-button-sm/md/lg/xl`, `size-input-md/lg`, `size-formControll-md/lg`.

### Variables from a remote library that is not AOH

These collections are not among AOH's collections, which are `.Primitives`, `Semantic colors`, `Spacing`, `Theme` and `Breakpoints`.

| Collection | Variables | Pages |
|---|---|---|
| `.Semantic` | `Spacing/spacing-2xs`, `Spacing/spacing-lg` (same names as AOH), `Spacing/input-size-container-md/lg`, `Spacing/space-sm`, `Radius/rounded-full` | all |
| `Dimensions` | `Spacing/px`, `Spacing/0.5`, `Spacing/space-2`, `Border Radius/rounded-full` | all but Recent |
| `Color Nav bar` | `Text & icon/Primary` | Comms (6 uses) |

`Spacing/spacing-2xs` and `Spacing/spacing-lg` exist in both AOH and `.Semantic`. Two tokens with the same name from different libraries are a drift risk, because they can silently hold different values.

### Local mobile variables

- **Used:**
  - `comms/avatar-surface` (all pages), `comms/bar-surface` and `comms/bar-text-primary`.
  - `chat/bubble-out`, `chat/receipt` and `kbd/key`.
  - `priority level/minimal`, `medium`, `high` and `critical`.
  - `state-layer/pressed` and `Selected`.
- **Unused on these pages:** `comms/mic-surface`, `comms/bar-text-secondary`, `chat/bubble-in`, `kbd/bg`, `kbd/key-alt`, `priority level/low`, `size/button-critical`, `state-layer/focus`, and all 21 variables in `Cheatsheet / Pastel`.

### Text and effect styles

- **AOH text styles:**
  - `text-xs/{regular, medium, semiBold, bold}`
  - `text-sm/{regular, medium, semiBold, bold}`
  - `text-base/{regular, medium, bold}`
  - `text-lg/semiBold` and `text-xl/bold`
  - `ShadCN typography/{h1, h2, h3, h4, p, Small}`
- **Text styles not from AOH:** `Typography/H1- Heading 1` and `Default/Bold/Body`, on Comms only (1–2 uses).
- **AOH effect styles:** `Shadows/sm`, `sm-strong`, `md`, `lg`.
- **Local effect styles:** `Drop Shadow` and `Layer Blur`.
- **Paint styles not from AOH:** AOH's own paint styles are only avatar images. These come from other libraries:
  - `wireframes/colors/secondary/gray` and `colors/backgrounds/light`, both inside `Android-nav-bar`.
  - `Neutral/*`, `Surface/Light/Primary` and `Default Accent/Dark/*`, from the keyboard kit.
  - `Red`, `White` and `Extra Light Grey`, on Comms only.

## Where the hardcoded values come from

Most of the hardcoded count comes from a few master components.

| Component | Hardcoded values | Proposed handling |
|---|---|---|
| `Chat/ Audio bubble` (local) | `#5d6471` ×3,080, `#5e7c85` ×1,120, `#404958` ×110 | Fix once in the master (the waveform bars) |
| `Android-nav-bar` (local) | `#949494` ×1,464, plus the wireframe paint styles | System UI drawn by the OS: exclude from parity |
| Keyboard (local and kit) | `Default Accent/*`, `Neutral/*`, `#303031` | System UI drawn by the OS: exclude from parity |
| `Chat / Location Bubble`, `Chat/ Reply` (local) | `#788496` ×135, `#404958` ×45 | Bind to AOH |

### Hardcoded values placed directly on screens

| Value | AOH equivalent | Where |
|---|---|---|
| `#09090b` frame fill | Zinc/950 = `color-bg` in Dark mode | Comms 117, Map 63, Directory 54, Chat 42, Recent 22 |
| `#ffffff` fill + `#0ea5e9` stroke on vectors | White, Sky/500 | Chat 134, Comms 53, Map 47, Directory 24, Incident 20. Probably flow arrows and annotations; confirm, then exclude. |
| `#ffffff` at 5% on rectangles | none | Directory 141 |
| `#262626` stroke override on `Comms / Call Log Row` | Neutral/800 primitive (not a semantic token) | Recent 72, Comms 26 |
| `#8d948a`, `#98a2aa` text | none | Comms 44 each |
| `#ff6565` | none (AOH error is Red/600 in Light, Red/400 in Dark) | Comms 22 |

## Layout and type not bound to tokens (designer-placed nodes only)

- **Spacing off the AOH scale (2/4/6/8/12/16/24/32/48):**
  - `gap 10`: Chat 469, Comms 305, Map 124, Incident 94.
  - `padLeft 9`, `gap 11`, and fractional values such as 7.99 and 8.01.
- **Spacing on the scale but not bound to a token:**
  - `gap 8`: Chat 724, Comms 671, Incident 285.
  - `padLeft 16`: Chat 730, Comms 295.
  - `padTop 8`: Comms 417.
- **Radius not bound to a token:**
  - 8 (Comms 274) and 20 (Chat 134, Comms 60).
  - 999, 9999 and 12498.75, all of which should be `radius-round`.
  - Fractional values on Chat.
- **Fonts:**
  - Inter, which AOH doesn't use: Regular 18 on four pages, plus sizes 4–5 on Map.
  - Atkinson Hyperlegible Next, on Comms.
  - Geist sizes outside the AOH ramp: 13, 15, 22, 28, 30, 34 and 64. SemiBold 15 alone appears 190 times on Chat.
  - Fractional sizes from scaled instances.
- **Shadows without a style:** blur radius 8, 12, 16 and 24 on Comms and Map; 24.96 on Chat.

## Open decisions before the parity audit

1. Exclude system UI drawn by the OS (`Android-nav-bar`, keyboard, status bar) and annotations from parity? Recommended: yes.
2. Which library is `.Semantic` / `Dimensions`? Retire it, or treat it as part of AOH?
3. Should `priority level/*` and `comms/*` become AOH semantic tokens, so the web dashboard can match them?
