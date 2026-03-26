# Design System Document: Vision AI Industrial Automation

## 1. Overview & Creative North Star
**Creative North Star: The Precision Observer**
This design system is engineered to feel like a high-performance optical instrument. Moving away from generic "dashboard" templates, it adopts a **High-Precision HUD (Heads-Up Display)** aesthetic. The system breaks the traditional rigid grid through intentional asymmetry, where data-heavy panels are balanced by expansive, breathable "vision" areas. By utilizing layered depth and tonal shifts rather than structural lines, we create an environment that feels like a sophisticated, digital extension of the industrial floor—authoritative, calm, and hyper-functional.

---

## 2. Colors
Our palette is rooted in a deep tech-noir foundation, using high-contrast Mint Green accents to draw the eye to critical AI-detected anomalies and system status.

### The "No-Line" Rule
To maintain a premium, seamless interface, **1px solid borders are prohibited for sectioning.** Structural boundaries must be defined solely through background color shifts or subtle tonal transitions. For example, a sidebar should sit on `surface_container_low` while the main feed rests on the base `surface` color.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. We use the Material surface tiers to define importance without visual clutter:
*   **Base Layer:** `surface` (#121414) for the main application background.
*   **Structural Sections:** `surface_container_low` (#1a1c1c) for primary navigation or sidebar zones.
*   **Content Cards:** `surface_container` (#1e2020) for grouping related data.
*   **Active Overlays:** `surface_container_highest` (#333535) for momentary focus or active selection.

### The "Glass & Gradient" Rule
To elevate the "HUD" feel, floating elements (like camera controls or AI status bubbles) should use **Glassmorphism**. Apply `surface_variant` with a 60% opacity and a `20px` backdrop-blur. 
*   **Signature Polish:** Main CTAs should not be flat. Use a subtle linear gradient from `primary` (#74d9b6) to `primary_container` (#002f22) at a 135-degree angle to provide a sense of "glow" and industrial soul.

---

## 3. Typography
We utilize a dual-font strategy to balance technical authority with operational readability.

*   **Display & Headlines (Space Grotesk):** This typeface provides the "industrial-tech" character. Its geometric apertures and wide stance mimic high-end telemetry displays. Use `display-lg` for critical throughput numbers and `headline-sm` for section titles.
*   **Body & Labels (Inter):** Chosen for its exceptional legibility in low-light industrial environments. `body-md` is the workhorse for system logs, while `label-sm` (all-caps with 0.05em tracking) is used for metadata and hardware IDs.
*   **Hierarchy Note:** Always lead with data. In a Vision AI context, the "Number" is the headline; the "Description" is the subtitle.

---

## 4. Elevation & Depth
Depth is achieved through **Tonal Layering** rather than traditional drop shadows.

*   **The Layering Principle:** Instead of shadows, stack surfaces. Place a `surface_container_highest` card on a `surface_container` background to create a natural "lift."
*   **Ambient Shadows:** For floating modals only, use extra-diffused shadows. 
    *   *Value:* `0px 12px 32px rgba(0, 0, 0, 0.4)`
    *   Shadows must be tinted with the `surface_tint` to ensure they feel like part of the environment, not a separate layer.
*   **The "Ghost Border" Fallback:** If a border is required for high-contrast accessibility, use the `outline_variant` token at **15% opacity**. Never use 100% opaque borders.

---

## 5. Components

### Buttons
*   **Primary:** Mint Green gradient (`primary` to `primary_container`). Use `rounded-sm` (0.125rem) for a sharp, precision-tooled look.
*   **Secondary:** Ghost style. No fill, `outline` at 20% opacity, `primary` text.
*   **Tertiary:** Text-only, using `title-sm` with 0.1rem letter spacing for an editorial feel.

### Input Fields
*   **Industrial Style:** No bottom line or full box. Use a `surface_container_high` fill with a `sm` (0.125rem) top-right and bottom-left corner radius, keeping the other two corners square (`none`) to mimic a technical bracket.
*   **States:** On focus, the background shifts to `surface_container_highest` with a `primary` glow (2px outer blur).

### Chips (AI Classifiers)
*   **Selection Chips:** Use `secondary_container` with `on_secondary_container` text. 
*   **Action Chips:** Floating `glassmorphism` style with a subtle `outline_variant` "Ghost Border."

### Cards & Lists (The Divider-Free Rule)
*   **Rule:** Forbid the use of divider lines. 
*   **Execution:** Separate list items using `spacing-4` (0.9rem) of vertical whitespace. To group items, use a subtle background shift to `surface_container_low`.

### Specialized AI HUD Components
*   **Bounding Box:** Use `primary` (#74d9b6) with a 1px weight. Add "corner brackets" that are 2px thick to emphasize the "Vision" focus.
*   **Confidence Meter:** A horizontal bar using a gradient from `primary` to `transparent`, housed within a `surface_container_lowest` track.

---

## 6. Do's and Don'ts

### Do
*   **DO** use asymmetric layouts. Place critical AI telemetry on the left and a large, unencumbered video feed on the right.
*   **DO** use "Micro-Interactions." When an AI object is detected, the corresponding data card should subtly shift from `surface_container` to `surface_container_high`.
*   **DO** respect the `spacing-8` (1.75rem) "Safe Zone" around the logo and main navigation elements.

### Don't
*   **DON'T** use rounded corners above `md` (0.375rem). The industrial aesthetic requires "Precision Sharpness"; overly rounded buttons feel like consumer apps, not professional tools.
*   **DON'T** use pure white (#ffffff) for text. Always use `on_surface` (#e2e2e2) to reduce eye strain in dark industrial control rooms.
*   **DON'T** use standard "Warning Red" for errors unless critical. Use `tertiary` (#e6c09d) for "Caution" to maintain the sophisticated color harmony.