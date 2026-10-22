# Web token inventory — 2026-10-22

- **Web file:** `VYNooSMqyhqJPom58kg8zV` (Field Manager v2.2), page "-> Current Website (WIP)".
- **Library:** AOH UI/ShadCN component library. It is the only library linked to the web file.
- **Mode:** read-only. Nothing in Figma was changed.
- **Machine-readable copy:** `2026-10-22-web-tokens.json`.

Each module frame contains the whole dashboard (map, list and header), so shared components such as `Map/ IncidentPin` and `Map/ Cluster` are counted in every module.

## Coverage by module

| Module | Nodes | Solid paints bound | Hardcoded | Text with a style |
|---|---|---|---|---|
| [Incident](https://www.figma.com/design/VYNooSMqyhqJPom58kg8zV/Field-Manager-v2.2?node-id=19553-372547) | 14,020 | 98.6% | 122 | 98.9% |
| [Responder](https://www.figma.com/design/VYNooSMqyhqJPom58kg8zV/Field-Manager-v2.2?node-id=19595-5721) | 20,303 | 98.7% | 180 | 97.2% |
| [Chat](https://www.figma.com/design/VYNooSMqyhqJPom58kg8zV/Field-Manager-v2.2?node-id=19605-7561) | 30,367 | 98.7% | 269 | 95.5% |
| [Geofence](https://www.figma.com/design/VYNooSMqyhqJPom58kg8zV/Field-Manager-v2.2?node-id=19615-11620) | 8,039 | 97.8% | 126 | 98.6% |
| [Camera](https://www.figma.com/design/VYNooSMqyhqJPom58kg8zV/Field-Manager-v2.2?node-id=19622-14597) | 3,151 | 98.1% | 41 | 97.8% |
| [Active](https://www.figma.com/design/VYNooSMqyhqJPom58kg8zV/Field-Manager-v2.2?node-id=19625-15120) | 9,344 | 98.9% | 70 | 99.0% |
| [Map](https://www.figma.com/design/VYNooSMqyhqJPom58kg8zV/Field-Manager-v2.2?node-id=19630-18977) | 9,001 | 98.6% | 83 | 98.9% |
| [Login](https://www.figma.com/design/VYNooSMqyhqJPom58kg8zV/Field-Manager-v2.2?node-id=19632-21327) | 751 | 90.2% | 46 | 93.5% |
| **All eight** | **94,976** | **98.5%** | **937** | **97.4%** |

The web file has no paint styles on solid colours and no local variables. Everything that is bound goes through AOH, except the stale collections listed below.

## Tokens in use

- **AOH semantic colours (52 of 106):**
  - **Background:** `color-bg`, `-subtle`, `-elevated`, `-strong`, `-disabled`, `-invers`, `-primary`, `-secondary`, `-success-strong/-muted`, `-error-strong/-muted`, `-warning-strong/-muted`, `-info-strong/-muted`.
  - **Border:** `color-border`, `-hover`, `-input`, `-disabled`, `-onColor`, `-primary`, `-success`, `-error`, `-error-muted`, `-warning`, `-warning-muted`, `-interactive`, `-focusRing`.
  - **Icon:** `color-icon`, `-muted`, `-disabled`, `-invers`, `-onColor`, `-primary`, `-success`, `-error`, `-warning`, `-info`, `-interactive`.
  - **Text:** `color-text`, `-muted`, `-disabled`, `-placeholder`, `-inverse`, `-onColor`, `-success`, `-primary`, `-error`, `-warning`, `-info`, `-interactive`.
- **AOH spacing, radius and size:**
  - **Spacing:** the full scale, `spacing-3xs` to `spacing-3xl`.
  - **Radius:** all 10 radius tokens, including `radius-card`.
  - **Size:** `size-button-sm/md`, `size-input-sm/md`, `size-avatar-xs/sm/md`, `size-formControll-sm/md/lg`.
- **Text styles (AOH):**
  - `text-xs/{light, regular, medium, semiBold, bold}`
  - `text-sm/{regular, medium, semiBold, bold}`
  - `text-base/{medium, semiBold}`
  - `text-lg/{semiBold, bold}` and `text-xl/bold`
  - `ShadCN typography/h3`, on Login only
- **Effect styles (AOH):** `Shadows/sm`, `sm-strong`, `md`, `lg`.
- **Paint styles:**
  - The AOH `Avatars/*` images.
  - `Gradient - Dark` on Login, which is not an AOH style.

### Stale variables (also used on mobile)

Neither of these collections belongs to any library linked to the web file or the mobile file, and AOH's current collections don't include them. Their values are frozen and will not follow AOH changes.

| Collection | Variables |
|---|---|
| `.Semantic` | `Spacing/spacing-2xs`, `spacing-xs`, `spacing-lg`, `space-sm`, `input-size-container-md`, `input-size-containr-sm` (misspelled), `Radius/rounded-full`, `rounded-sm` |
| `Dimensions` | `Spacing/px`, `0.5`, `1.5`, `3.5`, `space-2`, `Border Radius/rounded`, `rounded-lg`, `rounded-none` |

## Hardcoded values

| Value | Where | Note |
|---|---|---|
| `#eeeeee` text, Inter 64 / Inter Black 500 | all 8 modules | Module title labels on the frame. Propose excluding them. |
| `#f97316` (Orange/500) as 30% fill + stroke, and ellipses | all 8 modules | No AOH token for this orange (PAR-002) |
| `#09090b`, `#71717a` text; `#e4e4e7` stroke | Login | These are `color-text`, `-muted` and `color-border` (PAR-009) |
| `#bd74ff` text, `#0369a1` stroke, `#0ea5e9` rings | Chat | |
| `#3b82f6` at 20% | Geofence | |
| Geist Regular 10, no style | Chat (240) | Below the AOH minimum of 12 (PAR-013) |

## Spacing not bound to tokens (designer-placed nodes)

- **`padLeft 12`:** in every module (Chat 893, Responder 486, Incident 472). `spacing-md` exists and should be bound.
- **`gap 10`:** in every module (Chat 627, Responder 366). This value is off the AOH spacing scale.
