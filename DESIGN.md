---
name: Sophiel Pizarra
description: Proposed visual direction for Sophiel's Parent and Child screens: a slate ground, a state-coloured frame, and a floating bar. Mockup only, not ported to the app.
colors:
  light-ground: "#EEF1F4"
  light-panel: "#FFFFFF"
  light-panel2: "#E3E8ED"
  light-ink: "#121E2A"
  light-mut: "#4F6071"
  light-accent: "#3E5F7D"
  dark-ground-pizarra: "#0A1119"
  dark-panel-pizarra: "#131D28"
  dark-ground-grafito: "#1C1B1A"
  dark-panel-grafito: "#262523"
  dark-ground-carbon: "#202224"
  dark-panel-carbon: "#2A2C2F"
  dark-ink: "#E6EDF3"
  dark-mut: "#97A9BA"
  dark-accent-blue: "#8FB4D6"
  dark-accent-sand: "#D9C3A0"
  state-protegido-frame: "#1E3A54"
  state-off-frame: "#383C42"
  state-stop-amber-frame: "#7A3A00"
  state-stop-honey-frame: "#F6C25E"
  state-stop-saffron-frame: "#D98E1C"
  state-gap-frame: "#8A1C24"
  dark-protegido-tonal-hero: "#353D43"
  dark-stop-amber-hero: "#4A2C12"
  dark-gap-hero: "#4A1D22"
  dark-off-hero: "#2A2D31"
typography:
  display:
    fontFamily: "Geist, system-ui, sans-serif"
    fontWeight: 700
  body:
    fontFamily: "Geist, system-ui, sans-serif"
    fontWeight: 400
rounded:
  dock: "34px"
spacing:
  dock-inset: "12px"
  dock-bottom: "14px"
components:
  dock:
    backgroundColor: "{colors.light-panel}"
    rounded: "{rounded.dock}"
    height: "68px"
---

# Design System: Sophiel Pizarra

> Mockup of a proposed direction. The shipped app is described by the repository's `DESIGN.md` (light theme only, Esmeralda and Moss). This file records what the mockup `sophiel-pizarra.html` does today, so the choices can be argued with and ported later.

## Overview

**Creative North Star: "The Slate Frame"**

The state of protection is a frame, not a décor. Every screen sits on a cool slate ground, and the only thing that changes colour with the state is the frame around the content: the strip at the top of Inicio and the floating bar at the bottom. Content never changes colour with the state, so a Parent can read the status from across the room and then ignore the colour when reading the numbers.

Sophiel is an on-device safety layer for a child's phone. The Parent checks it occasionally and needs to trust it at a glance. The Child should barely notice it. The Pizarra direction gives both a quiet ground, one state strip, and no decorative colour. The app's name, copy, and Spanish wording are unchanged (see CONTEXT.md and the "tapado" rule in the app's own DESIGN.md).

Two themes exist: **Gris claro** (light, the default) and **Oscuro** (dark). Dark mode is not an inversion: each state has its own dark frame, and the ground can be one of three candidates.

**Key Characteristics:**
- A cool slate ground in light mode; a choice of three near-black grounds in dark mode.
- The state colours only the frame (strip and bar). Content keeps its own colours.
- A floating bar with four tabs (Inicio, Historial, Apps, Ajustes) over the content.
- Geist throughout, bold for display, semibold for labels.
- Dark frames are tonal: each state's hue mixed into the ground at a low ratio.

## Colors

A slate family with one state colour per frame. Light and dark are separate ramps, not an inversion.

### Primary
- **Slate Accent** (#3E5F7D, light; #8FB4D6 dark): the accent for links, the selected segment, and the Del estado option in dark mode. Used on text and fills that need to read as "active", never as decoration.

### Frames (state)
Each state paints the frame only. Light mode frames are full-saturation; dark mode frames are tonal.
- **Protegido** (`#1E3A54`): slate. Dark (Actual) keeps `#1E3A54`. Dark (Tonal) uses `#353D43`, the slate accent at 22% into the ground.
- **Listo / off** (`#383C42`): graphite. Dark (Actual): `#2A2D31`.
- **Se detuvo** (amber `#7A3A00`; honey `#F6C25E`; saffron `#D98E1C`): the stopped state. Three candidate frames, chosen with "Color de «Se detuvo»". Dark (Actual): amber `#4A2C12`; honey and saffron are darkened to `#8A6A2E` and `#7A5216`.
- **Interrumpida** (`#8A1C24`): broken protection. Dark (Actual): `#4A1D22`.

### Neutrals
- **Ground** (light `#EEF1F4`; dark `#0A1119` Pizarra, `#1C1B1A` Grafito cálido, `#202224` Carbón): the page behind everything. Dark grounds are never pure black.
- **Panel** (light `#FFFFFF`; dark `#131D28` Pizarra, `#262523` Grafito, `#2A2C2F` Carbón): cards and the bar.
- **Panel 2** (light `#E3E8ED`; dark `#1D2B3A`, `#33312E`, `#37393D`): the inner surfaces and skeletons.
- **Ink** (light `#121E2A`; dark `#E6EDF3`, `#EDE9E3`, `#E8EAEC`).
- **Muted** (light `#4F6071`; dark `#97A9BA`, `#ABA59C`, `#A4A8AE`).

### Named Rules
**The Frame Rule.** The state colours the strip and the bar, and nothing else. A coloured card or number is a lie on this screen, because the content does not change with the state.

**The Tonal Dark Rule.** In Oscuro, a state's frame is its accent mixed into the ground at 16–28%. Saturation drops with the mix, and the hue stays readable. Use the "Tonal" option for this; "Actual" keeps the earlier, more saturated dark frames.

**The One Temperature Rule.** A dark frame, the bar, and the content accent must share the ground's temperature. Warm grounds take warm tints; cool grounds take cool ones. The "Del estado" accent option exists because a sand accent on a slate frame breaks this rule.

## Typography

**Display Font:** Geist (with system-ui, sans-serif)
**Body Font:** Geist
**Label Font:** Geist, semibold

**Character:** a tight modern grotesk. Bold display sizes carry the state word ("Protegido", "Se detuvo"); semibold carries labels and tabs; regular carries descriptions.

### Hierarchy
- **Display** (bold 700): the state word on the frame, the count on Hoy.
- **Headline** (semibold 600): screen titles.
- **Title** (semibold 600): row titles and app names.
- **Body** (regular 400): descriptions and the helper line under a state.
- **Label** (semibold 600): tabs, chips, and button text.

### Named Rules
**The One Word Rule.** The Spanish word for covered content is "tapado" everywhere, inherited from the app.

## Layout

A single column inside a phone frame. The state frame sits at the top of Inicio, followed by a two-tile row (Hoy and Últimos 7 días), then a list of apps. The floating bar sits 12px from the sides and 14px from the bottom, is 68px tall, and has a 34px radius. Its four tabs are equal width.

## Elevation & Depth

Flat with a faint lift in light mode (`0 1px 2px #121E2A12, 0 4px 14px -8px #121E2A26`). In dark mode the lift becomes a 1px inset hairline in the panel colour (`0 0 0 1px #E6EDF314`). The floating bar is the only element with a larger shadow (`0 14px 30px -12px #000a`), because it floats above the content.

### Named Rules
**The Hairline Rule.** In dark mode, depth comes from a 1px hairline, not a shadow. The bar's hairline takes the state colour at 28%.

## Shapes

Rounded rectangles throughout. The floating bar is a pill (34px radius). Cards and tiles use the app's tile language: soft corners, no hard edges.

## Components

### Floating bar
- **Shape:** 34px radius, 68px tall, 12px inset from the sides, 14px from the bottom.
- **Fill (light):** the frame colour at 62% opacity with `backdrop-filter: blur(22px) saturate(0.6)`.
- **Fill (dark):** the ground with a 9% tint of the state colour, `backdrop-filter: blur(22px) saturate(0.5)`, and a 1px hairline at 28% of the state colour.
- **Active tab:** a filled pill in the tab's active colour; inactive tabs use the frame's secondary text.

### State frame (strip)
- **Glow:** a radial gradient from the top right. On Se detuvo, the glow is 52% in light mode; in dark mode it is 24% and fades out at 82%, so it reads as warmth, not a spot.
- **Cause chip:** light mode 16% of the glow colour; dark mode 7% of the state's secondary colour.
- **Button:** the frame's primary button uses the state's `hsig` fill with the frame's dark text.

### Chips and option rows
- **Option rows** (Fondo, Estados, Acento, Color de «Se detuvo») are pill chips in a row. The selected chip is inverted (light fill, dark text in dark mode).

## Do's and Don'ts

### Do:
- **Do** keep the state colour on the frame and the bar only.
- **Do** tint dark frames by mixing the state accent into the ground at 16–28%.
- **Do** keep one temperature per screen: the ground, the frame, the bar, and the content accent.
- **Do** keep the navbar at 52–62% opacity over content, so its labels still read over the app list.

### Don't:
- **Don't** paint content, numbers, or cards in a state colour.
- **Don't** use a warm accent on a cool frame, or the reverse.
- **Don't** use pure black for a dark ground.
- **Don't** let the dark glow become a hot spot. Keep it soft and wide.
- **Don't** treat the mockup as shipped. Porting to the app needs its own decision entry (see the memory note `ui-redesign-direction`).

## Options in the mockup

These are the choices the side panel offers. The defaults are in brackets.

- **Tema:** [Gris claro] or Oscuro.
- **Fondo del tema oscuro:** [Pizarra], Grafito cálido, or Carbón.
- **Estados en tema oscuro:** [Actual] (saturated dark frames) or Tonal (mixed into the ground).
- **Acento en tema oscuro:** [Del fondo] (the ground's accent) or Del estado (the state's hue).
- **Color de «Se detuvo»:** [Ámbar], Miel, or Azafrán.
- **Estado de la protección:** Protegido, Listo, Se detuvo, or Interrumpida.

## Open items

- The Tonal frames for Miel and Azafrán have been generated but not screenshotted.
- Dark-mode Interrumpida and Listo were checked by computed colour, not by screenshot.
- Dark mode has not been checked on any ground other than Grafito for the Del estado accent.
- The `.impeccable/design.json` sidecar is not written: this folder is not a project root.
