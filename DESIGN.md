---
name: Executive Precision
colors:
  surface: '#f7f9fb'
  surface-dim: '#d8dadc'
  surface-bright: '#f7f9fb'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f2f4f6'
  surface-container: '#eceef0'
  surface-container-high: '#e6e8ea'
  surface-container-highest: '#e0e3e5'
  on-surface: '#191c1e'
  on-surface-variant: '#464555'
  inverse-surface: '#2d3133'
  inverse-on-surface: '#eff1f3'
  outline: '#777587'
  outline-variant: '#c7c4d8'
  surface-tint: '#4d44e3'
  primary: '#3525cd'
  on-primary: '#ffffff'
  primary-container: '#4f46e5'
  on-primary-container: '#dad7ff'
  inverse-primary: '#c3c0ff'
  secondary: '#565e74'
  on-secondary: '#ffffff'
  secondary-container: '#dae2fd'
  on-secondary-container: '#5c647a'
  tertiary: '#005338'
  on-tertiary: '#ffffff'
  tertiary-container: '#006e4c'
  on-tertiary-container: '#7df1bd'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#e2dfff'
  primary-fixed-dim: '#c3c0ff'
  on-primary-fixed: '#0f0069'
  on-primary-fixed-variant: '#3323cc'
  secondary-fixed: '#dae2fd'
  secondary-fixed-dim: '#bec6e0'
  on-secondary-fixed: '#131b2e'
  on-secondary-fixed-variant: '#3f465c'
  tertiary-fixed: '#85f8c4'
  tertiary-fixed-dim: '#68dba9'
  on-tertiary-fixed: '#002114'
  on-tertiary-fixed-variant: '#005137'
  background: '#f7f9fb'
  on-background: '#191c1e'
  surface-variant: '#e0e3e5'
typography:
  display-lg:
    fontFamily: Geist
    fontSize: 36px
    fontWeight: '600'
    lineHeight: 44px
    letterSpacing: -0.025em
  display-lg-mobile:
    fontFamily: Geist
    fontSize: 28px
    fontWeight: '600'
    lineHeight: 36px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Geist
    fontSize: 28px
    fontWeight: '600'
    lineHeight: 36px
    letterSpacing: -0.02em
  headline-md:
    fontFamily: Geist
    fontSize: 22px
    fontWeight: '600'
    lineHeight: 28px
    letterSpacing: -0.015em
  headline-sm:
    fontFamily: Geist
    fontSize: 18px
    fontWeight: '600'
    lineHeight: 24px
    letterSpacing: -0.01em
  title-md:
    fontFamily: Geist
    fontSize: 16px
    fontWeight: '500'
    lineHeight: 24px
    letterSpacing: -0.005em
  body-lg:
    fontFamily: Geist
    fontSize: 15px
    fontWeight: '400'
    lineHeight: 22px
  body-md:
    fontFamily: Geist
    fontSize: 13px
    fontWeight: '400'
    lineHeight: 18px
  body-sm:
    fontFamily: Geist
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
  label-md:
    fontFamily: Geist
    fontSize: 12px
    fontWeight: '500'
    lineHeight: 16px
    letterSpacing: 0.01em
  label-sm:
    fontFamily: Geist
    fontSize: 11px
    fontWeight: '500'
    lineHeight: 14px
    letterSpacing: 0.02em
  code-sm:
    fontFamily: JetBrains Mono
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  gutter: 1rem
  gutter-desktop: 1.5rem
  margin: 1rem
  margin-desktop: 2rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 0.75rem
  space-lg: 1rem
  space-xl: 1.5rem
---

## Brand & Style

This design system is engineered for analytical rigor, rapid information retrieval, and sustained operational focus. Built specifically for enterprise operators, systems architects, and executive leaders, the interface balances high-density utility with modern architectural refinement.
This design system is engineered for analytical rigor, rapid information retrieval, and sustained operational focus. Built specifically for enterprise operators, systems architects, and executive leaders, the interface balances high-density utility with modern architectural refinement.

The aesthetic style is rooted in modern precision-minimalism: deliberate negative space, restrained tonal layering, ultra-crisp hairline divisions, and subtle purposeful motion. The experience feels fast, deterministic, and dependable—eliminating visual noise to bring metrics, anomalies, and structural data relationships into sharp focus.

## Colors

The palette leverages an architectural foundation of slate and crisp indigo. Canvas backgrounds maintain absolute clarity using `#F8FAFC`, paired with structural text in `#0F172A` and muted utility values in slate tints (`#64748B`, `#94A3B8`). Structural elements and subtle boundaries rely strictly on `#E2E8F0`.

The semantic system relies on calibrated, unambiguous signals:
- **Primary / Active:** `#4F46E5` (Indigo 600) drives key interactions, active routes, and prioritized focus rings. Deep slate `#0F172A` acts as an anchor for navigation and high-contrast control surfaces.
- **Success:** `#059669` (Emerald 600) with `#ECFDF5` container fills for positive margins, system health, and completed state indicators.
- **Warning:** `#D97706` (Amber 600) with `#FFFBEB` fills for pending operations, approaching rate limits, and non-blocking warnings.
- **Critical / Danger:** `#E11D48` (Rose 600) with `#FFF1F2` fills for critical failures, service drops, and destructive triggers.
- **Info:** `#2563EB` (Blue 600) with `#EFF6FF` fills for context annotations and background synchronization events.

## Typography

The typography scale utilizes Geist for its precise glyph geometry, compact vertical proportions, and superior legibility across dense data displays. Monospaced figures (`font-variant-numeric: tabular-nums`) must be enabled universally for numbers, KPIs, timestamps, and table columns.

JetBrains Mono serves strictly for API keys, JSON payloads, commit SHAs, and raw system logs. Negative letter-spacing is applied systematically to display and headline tiers to maintain tight optical density, while label tokens incorporate micro-tracking for high legibility at 11px and 12px scales.

## Layout & Spacing

The layout model is a structured fluid grid optimized for high-resolution displays (1440px and beyond) with dynamic adaptation for smaller surfaces:

- **Desktop (≥1280px):** Fixed 240px or collapsible 64px vertical sidebar, 12-column content grid, 24px gutters, and 32px canvas margins. Multi-column dashboards reflow cleanly into 3- or 4-column KPI rows.
- **Tablet (768px - 1279px):** Auto-collapsing sidebar to icon rail, 8-column layout, 16px gutters, and 24px canvas margins. Secondary data panels convert to overlay drawers.
- **Mobile (<768px):** Off-canvas slide-out navigation, single-column vertical stack, 16px outer margins, and horizontal table scrolling with sticky lead columns.

Internal component rhythm is built strictly on an 8px grid increment, with 4px sub-steps reserved for compact badge padding, data-table cell heights, and icon-to-label gaps.

## Elevation & Depth

Visual hierarchy prioritizes crisp hair-line boundaries over heavy shadows, keeping visual noise minimal in data-dense layouts:

- **Level 0 (Base Canvas):** `#F8FAFC` flat surface.
- **Level 1 (Card & Content Blocks):** `#FFFFFF` surface bounded by a continuous 1px solid border (`#E2E8F0`). Shadows are ultra-subtle ambient diffusions: `0 1px 2px 0 rgba(15, 23, 42, 0.04)`.
- **Level 2 (Hover & Contextual Surfaces):** `#FFFFFF` surface with `0 4px 6px -1px rgba(15, 23, 42, 0.07), 0 2px 4px -2px rgba(15, 23, 42, 0.05)` and border `#CBD5E1`.
- **Level 3 (Dropdowns & Popovers):** Elevated `#FFFFFF` layer with `0 10px 15px -3px rgba(15, 23, 42, 0.08), 0 4px 6px -4px rgba(15, 23, 42, 0.03)` with a precise 1px `#E2E8F0` border.
- **Level 4 (Modals & Command Palettes):** Centered `#FFFFFF` surface floating above an `#0F172A` backdrop at 45% opacity with 4px background blur. Elevated with `0 20px 25px -5px rgba(15, 23, 42, 0.12), 0 8px 10px -6px rgba(15, 23, 42, 0.04)`.

## Shapes

The design system employs a refined soft-radius standard (Level 1) to convey precision and structural stability:
- **Base Components:** Inputs, buttons, dropdown triggers, and badges use 4px (`rounded`).
- **Cards & Data Panels:** Metric containers, table wrappers, and modals use 8px (`rounded-lg`).
- **Pill Exceptions:** Status dots and live telemetry tags may use full pill rounding (`9999px`) strictly when displaying binary online/offline indicators or compact categorical filters.

## Components

### Buttons
- **Primary:** Solid `#4F46E5` background, white text, 4px radius, 32px standard height (compact) or 36px (default). On hover: `#4338CA`. Active: `#3730A3`. Focus-visible: 2px offset ring with `#4F46E5`.
- **Secondary:** `#FFFFFF` background, `#0F172A` text, 1px border `#E2E8F0`. On hover: `#F1F5F9` background, border `#CBD5E1`.
- **Destructive:** `#EF4444` background with white text, or borderless `#E11D48` text variant for secondary destructive actions.
- **Icon Buttons:** Fixed 32x32px square bounds with centered 16px SVG glyphs; subdued `#64748B` foreground shifting to `#0F172A` on hover.

### Structured Data Tables
- **Header:** 36px height, `#F8FAFC` background, 1px solid bottom border (`#E2E8F0`). Text is `label-sm`, uppercase, tracked +0.05em, `#64748B`.
- **Row:** 44px standard height (36px in compact view mode), `#FFFFFF` surface with `#F1F5F9` border-bottom. Row hover adopts `#F8FAFC` transition.
- **Selection State:** Row background transitions to `#EEF2FF` with a 2px active primary indigo border accent on the left-most cell edge.
- **Numerical Alignment:** Numeric columns right-align with `tabular-nums` applied; text columns left-align; status and short codes center-align.

### KPI Metric Cards
- **Structure:** 8px radius, `#FFFFFF` background, 1px `#E2E8F0` border, 16px internal padding.
- **Typography Layout:** Header contains `label-md` in `#64748B` accompanied by a contextual icon or mini sparkline. Primary figure uses `display-lg` (36px, Geist SemiBold) with tabular numbers.
- **Delta Indicator:** Compact badge incorporating upward/downward 12px chevron, color-coded with semantic emerald or rose container and text (`+12.4% vs last period`).

### Chips & Badges
- **Status Badges:** 20px total height, 4px border radius, 6px horizontal padding. Composed of an optional 6px circular dot and `label-sm` text. Examples:
  - Active: `#ECFDF5` background, `#059669` text, `#10B981` dot.
  - Review: `#FFFBEB` background, `#D97706` text, `#F59E0B` dot.
  - Failed: `#FFF1F2` background, `#E11D48` text, `#F43F5E` dot.
- **Filter Chips:** 28px height, `#FFFFFF` fill with `#E2E8F0` border, incorporating removable cross icon when active.

### Form Inputs & Controls
- **Text Field:** 36px height, `#FFFFFF` fill, 1px `#E2E8F0` border, 4px radius, `body-md` typography. Placeholder in `#94A3B8`. Focus: 1px border `#4F46E5` accompanied by `0 0 0 1px #4F46E5` ring.
- **Checkboxes & Radios:** 16x16px bounding box, 1px `#CBD5E1` border. Checked state uses solid `#4F46E5` fill with white check/dot icon.
- **Input Groups:** Prefix/suffix currency or domain labels are anchored in `#F1F5F9` containers with integrated inner borders.

### Navigation Patterns
- **Sidebar Rail:** `#0F172A` slate dark container or `#FFFFFF` light panel. Nav items have 36px height, 8px horizontal padding, 6px radius, containing 18px stroke icons and `body-md` label. Active route: `#EEF2FF` background with `#4F46E5` text and 3px solid primary indicator strip.
- **Command Palette:** Centered modal, 560px width, top-anchored search input (44px height), instant key-value filtering, structured grouped sections with monospaced keyboard shortcut badges (`Kbd` key with 1px border).