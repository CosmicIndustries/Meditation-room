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

# Healing Sands

A single-page **Three.js beach meditation**, companion to Sacred Chamber but built around a different mood: where Sacred Chamber is a solemn underground water temple, Healing Sands is an open, empowering shoreline journey lit by a campfire.

The session opens with no fire lit — just an ocean, a sunrise or sunset sky (picked from the time of day), and the sand, to be watched quietly. When you kindle the fire, its light takes on the colour of the active chakra, and the sky, ocean and sand shift to match: the environment leans toward the chakra's **complementary** colour while the fire itself carries the chakra's true hue, so the whole scene reads as one complementary colour harmony anchored on the flame. From there the session steps progressively through 4–6 chakras (configurable), each with its own solfeggio tone, before settling into a closing afterglow.

The solfeggio tone for the active chakra directly modulates the generated beach soundscape: its frequency sets the wind's filter brightness, its brainwave-entrainment rate sets how fast the waves swell, and both brighten the shoreline spray as the chakras rise.

This is a self-contained HTML file, same build philosophy as Sacred Chamber.

## Quick Start

```bash
python3 -m http.server 8000
```

Open:

```text
http://localhost:8000/healing-sands.html
```

## Core Features

* Prelude phase — unlit campfire, just the tide and the sky, before any chakra is active
* Kindling the fire starts a 4–6 step progressive chakra journey (configurable length, step count, and direction — rising Root→Crown or grounding Crown→Root)
* Sky, ocean and sand recolour in a complementary-colour relationship to the active chakra, with the firelight carrying the pure chakra hue
* Procedural ocean (wind-driven swell, shoreline foam, sun glint), grained sand, drifting embers and smoke
* Web Audio wind, breeze, wave-swell and spray layers, all modulated by the active chakra's solfeggio frequency and brainwave rate, plus a fire-crackle layer once lit
* Afterglow close — fire settles to embers once the journey completes

## Controls

| Action              | Control                              |
| ------------------- | ------------------------------------ |
| Kindle the fire      | Click the "Kindle the Fire" pill     |
| Adjust session       | Gear icon (top-left) before lighting the fire — locks once the journey starts |
| Mute / unmute        | Click the note icon (top-right)      |
| Glance around        | Drag mouse / touch-drag (limited, seated view) |
| Zoom                 | Mouse wheel                          |
| Restart              | "Begin Again" button during the afterglow |
