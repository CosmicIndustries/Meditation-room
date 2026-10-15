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

### Rendering

Kept deliberately "N64-era": flat low-poly primitives, no photorealism, no external textures or 3D assets — but with a handful of real, cheap rendering techniques layered on top of that aesthetic rather than against it:

* Real shadow mapping off the sun (soft PCF shadows cast by decor and the campfire onto the ground)
* A height-differential "bump" normal on the ground, computed analytically from the same noise that displaces it, so lighting reads the terrain's relief instead of a flat plane
* A small procedurally-painted, mip-mapped splat-bitmap texture blended into the ground, so fine detail stops shimmering near the horizon the way pure analytic shader noise does
* A hand-rolled single-pass composite (no external postprocessing library): a cheap few-tap bloom around bright pixels, plus a per-pixel dither on the output — the same trick the N64 used to fake extra colour depth on its 21-bit framebuffer, here smoothing banding instead
* Lowered-roughness materials so directional sunlight actually produces visible specular highlights on rocks/decor

True volumetric ray-marching was deliberately left out — it's a real cost center that would hurt mobile framerate across 42 biomes for a look this style doesn't need; the bloom + dither composite delivers most of the same "it looks considered" payoff far more cheaply.

### Audio

Wind, breeze, and (on water-bearing biomes) wave-swell/spray layers, all modulated by the active chakra's solfeggio frequency and brainwave rate, plus a fire-crackle layer once lit. The fire crackle and wave/spray layers are genuinely spatialized: Web Audio's `PannerNode` with `panningModel:'HRTF'` convolves each source against a built-in head-related impulse response (the real, in-browser equivalent of binaural/HRIR processing), with the `AudioListener` updated from the camera every frame — so they audibly localize, and re-pan live as you turn your head in VR. OS-level surround drivers (Dolby Atmos, Windows Sonic, Razer Surround) aren't reachable from a webpage at all; this is the real browser-native alternative, not an imitation of those.

### Determinism

Scene **layout** (decor placement/sizes, the cloud field, the gull flock, each biome's initial ambient-particle scatter) is seeded, not `Math.random()` — the same biome renders the same arrangement every time you pick it, rather than a fresh jumble on every reload. Ongoing **animation** (flame flicker, ember/smoke spawn timing, wind/wave/crackle audio texture) is intentionally left on true randomness, since a fire that flickered identically every session would read as fake.

### Next-gen biofeedback input (experimental)

A small panel (heart icon, top-right) stubs out next-level interfaces for a meditation app:

* **Heart rate** and **pulse oximeter** — real, standard Web Bluetooth GATT services (`heart_rate` / `0x1822`), genuinely connectable to real hardware wherever Web Bluetooth is available. A connected heart rate subtly paces the fire's flicker to your real heartbeat.
* **BCI / EEG** — there's no universal Bluetooth (or any browser) standard for consumer brain-computer interfaces, so this is a clearly-labelled stub: a simulated alpha/theta signal demonstrates the integration point; swap the interval for a real device SDK's callback (Muse, Emotiv, OpenBCI) to go live.
* **Haptics** — pulses whatever real output the browser can already reach (a connected gamepad's rumble motors, or a phone's vibration motor); ticks once per chakra stage transition once tested.

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
* Web Audio wind, breeze, and (on water-bearing biomes) wave-swell and spray layers, all modulated by the active chakra's solfeggio frequency and brainwave rate, plus a fire-crackle layer once lit and genuine HRTF binaural spatialization on the fire/wave sources
* Real shadow mapping, height-differential ground lighting, a mip-mapped splat texture, and a cheap bloom+dither composite pass — kept to the N64 aesthetic, not fighting it
* Seeded, deterministic scene layout per biome (decor/clouds/gulls/particles) — true randomness stays reserved for ongoing animation, where it belongs
* Experimental biofeedback-input stubs: real Web Bluetooth heart-rate/pulse-oximeter support, a BCI/EEG demo stub, and haptic pulses
* Optional WebXR VR support with head tracking
* Afterglow close — fire settles to embers once the journey completes

## Controls

| Action              | Control                              |
| ------------------- | ------------------------------------ |
| Choose a realm       | Tap a category tab, then a biome card, on the entry screen |
| Kindle the fire      | Click the "Kindle the Fire" pill     |
| Adjust session       | Gear icon (top-left) before lighting the fire — locks once the journey starts |
| Mute / unmute        | Click the note icon (top-right)      |
| Biofeedback input (experimental) | Heart icon (top-right) |
| Enter VR             | "Enter VR" button (bottom-right), shown only if your browser/headset supports it |
| Glance around        | Drag mouse / touch-drag (limited, seated view), or head tracking in VR |
| Zoom                 | Mouse wheel                          |
| Restart              | "Begin Again" button during the afterglow |
