https://github.com/CosmicIndustries/Meditation-room/blob/main/sacred_chamber_v4.html

# Meditation-room
<a href="https://raw.githubusercontent.com/CosmicIndustries/Meditation-room/refs/heads/main/Screenshot_20260531_164558_Privacy%20Browser.jpg"><img src="https://raw.githubusercontent.com/CosmicIndustries/Meditation-room/refs/heads/main/Screenshot_20260531_164558_Privacy%20Browser.jpg"><img src=""></img></a>


https://raw.githubusercontent.com/CosmicIndustries/Meditation-room/refs/heads/main/Screenshot_20260531_164558_Privacy%20Browser.jpg


# Sacred Chamber — Zora's Domain

A single-page **Three.js meditation chamber** that combines chakra-based interaction, procedural sacred-geometry padmas/yantras, animated water, crystal pillars, mudra sculptures, Web Audio tones, and multiple camera modes into an immersive browser scene.

This is currently a **prototype / concept build**: a self-contained HTML file with embedded CSS and JavaScript.

## Quick Start

Save the project as:

```text
index.html
```

Then run:

```bash
python3 -m http.server 8000
```

Open:

```text
http://localhost:8000
```

## Core Features

* Seven chakra-aligned crystal pillars
* Interactive chakra activation
* Procedural 3D padma / yantra generation
* SVG chakra button icons
* Animated shader water chamber
* Web Audio chakra tones and generated water ambience
* Orbit, top-down, mudra, and VR-style view modes
* Mouse, touch, keyboard, and UI button controls

## Controls

| Action            | Control                              |
| ----------------- | ------------------------------------ |
| Activate chakra   | Click a pillar or bottom chakra icon |
| Deactivate chakra | Click the active chakra again        |
| Orbit camera      | Drag mouse / touch-drag              |
| Zoom              | Mouse wheel                          |
| Cycle view mode   | Press `V` or click the view button   |
| Toggle audio      | Click the music note button          |
| Hover tooltip     | Move mouse over chakra pillars       |

# Healing Lands

A single-page **Three.js meditation journey** across 42 procedural biomes, companion to Sacred Chamber but built around a different mood: where Sacred Chamber is a solemn underground water temple, Healing Lands is an open, empowering outdoor journey lit by a campfire, in whichever realm you choose to sit in.

Before you begin, pick a realm from four categories — **Terrestrial**, **Aquatic**, **Air & Fantasy**, and **Other Realms** (scale-shifted and otherwise fictional-scapes: macro, micro, nano, stratosphere, and more) — 10, 10, 10 and 12 biomes respectively, 42 in all, from Pine Forest and Desert Dunes to Nebula Drift and Quantum Foam. The flagship **Coastal Shore** biome (the original "Healing Sands" scene) keeps its own bespoke ocean/sand shaders; every other realm is rendered by a shared, data-driven environment engine — procedural sky, ground and (where appropriate) water, theme-tinted low-poly decor, and a theme-matched ambient particle layer (snow, spores, bubbles, ash, fireflies, dust, and more) — so the same ritual plays out believably anywhere from a mountain summit to a dreamscape.

The session opens with no fire lit — just the chosen realm, a sunrise or sunset sky (picked from the real time of day), to be watched quietly. When you kindle the fire, its light takes on the colour of the active chakra, and the sky, ground and water shift to match: the environment leans toward the chakra's **complementary** colour while the fire itself carries the chakra's true hue, so the whole scene reads as one complementary colour harmony anchored on the flame. From there the session steps progressively through 4–6 chakras (configurable), each with its own solfeggio tone, before settling into a closing afterglow.

The solfeggio tone for the active chakra directly modulates the generated soundscape: its frequency sets the wind's filter brightness (itself biased per biome, from a hushed underwater rumble to an exposed ridge's open hiss), its brainwave-entrainment rate sets how fast any water swells, and both brighten shoreline spray as the chakras rise, in biomes that have a shoreline.

Also supports **WebXR VR headsets**: an "Enter VR" button appears automatically on any browser/device that reports `immersive-vr` support, and head tracking takes over looking around once you're in the headset.

This is a self-contained HTML file, same build philosophy as Sacred Chamber.

## Quick Start

```bash
python3 -m http.server 8000
```

Open:

```text
http://localhost:8000/healing-lands.html
```

## Core Features

* 42 procedural biomes across four categories (Terrestrial, Aquatic, Air & Fantasy, Other Realms), picked from the entry screen before each session
* Prelude phase — unlit campfire, just the chosen realm and the sky, before any chakra is active
* Kindling the fire starts a 4–6 step progressive chakra journey (configurable length, step count, and direction — rising Root→Crown or grounding Crown→Root)
* Sky, ground and water (where present) recolour in a complementary-colour relationship to the active chakra, with the firelight carrying the pure chakra hue
* Shared day/night cycle generated procedurally per biome from the real device clock, not a fixed arc
* Procedural ground and optional water per biome, theme-tinted low-poly decor (rocks, crystals, spikes, pillars, rings), and a theme-matched ambient particle layer
* The flagship Coastal Shore biome keeps its original bespoke ocean (wind-driven swell, shoreline foam, sun glint) and sand (grain, swash) shaders
* Web Audio wind, breeze, and (on water-bearing biomes) wave-swell and spray layers, all modulated by the active chakra's solfeggio frequency and brainwave rate, plus a fire-crackle layer once lit
* Optional WebXR VR support with head tracking
* Afterglow close — fire settles to embers once the journey completes

## Controls

| Action              | Control                              |
| ------------------- | ------------------------------------ |
| Choose a realm       | Tap a category tab, then a biome card, on the entry screen |
| Kindle the fire      | Click the "Kindle the Fire" pill     |
| Adjust session       | Gear icon (top-left) before lighting the fire — locks once the journey starts |
| Mute / unmute        | Click the note icon (top-right)      |
| Enter VR             | "Enter VR" button (bottom-right), shown only if your browser/headset supports it |
| Glance around        | Drag mouse / touch-drag (limited, seated view), or head tracking in VR |
| Zoom                 | Mouse wheel                          |
| Restart              | "Begin Again" button during the afterglow |
