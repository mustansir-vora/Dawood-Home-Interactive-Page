# Dawood Home Interactive Page

A self-contained, browser-based **3D architectural visualization (ArchViz) walkthrough** of a two-story residence (`27'-8" × 53'-0"` plot footprint) built with **Three.js (r160)** and **Tailwind CSS**.

Explore both floors in first-person at an accurate `5'-10"` (`1.78 m`) human eye level, walk seamlessly up and down the U-shaped staircase, adjust ceiling heights in real time, switch lighting moods, and teleport to any room from the interactive blueprint mini-map.

---

## Features

### Interactive Walkthrough & Navigation
- **First-Person Exploration (`5'-10"` Eye Level):** Smooth collision-sliding movement through doorways, passages, verandah, terrace, and across all 18 steps of the U-shaped staircase.
- **Interactive Blueprint Mini-Map:** Live 2D floor plan in the top-right HUD displaying room labels, dimensions, your current position and viewing cone, a floor preview toggle (`Show FF` / `Show GF`), and **click-to-teleport** into any room.
- **Live Room & Elevation Readout:** Automatically identifies the room and its dimensions as you move (or reports staircase elevation percentage while climbing).
- **Multi-Device Controls:** Supports keyboard + mouse drag, Pointer Lock FPS mouse look, and an on-screen touch D-pad + touch drag on mobile/tablet devices.

### Real-Time Architectural Controls
- **Dynamic Ceiling Height (`8'-6"` to `14'-0"`):** Adjust clear floor-to-ceiling height in `3"` increments via slider, `−` / `+` stepper buttons, or quick presets (`9'-0"`, `10'-0"`, `11'-0"`, `12'-0"`). Rebuilds walls, doors, windows, stairs, ceiling fixtures, and the first-floor slab height live while keeping you grounded in place.
- **Three Lighting Ambience Modes:**
  - **Daylight:** Clear gradient sky dome, bright directional sunlight with soft shadows, and crisp environment reflections.
  - **Golden Hour:** Low-angle warm sunset light streaming across the interior floors.
  - **Evening Lights:** Deep twilight sky highlighting the warm 3000K interior lighting, recessed ceiling panels, and cove strips.
- **Fixture Toggles:**
  - **Lights:** Toggle recessed `8" × 8"` square LED ceiling lamps, 3000K false-ceiling cove strips, and interior point lights.
  - **Fans:** Smoothly spin up or stop the 3-blade walnut and bronze ceiling fans.
- **Floor Switcher:** Jump directly between the **Ground Floor** (Living Room) and **First Floor** (Family Seating).

### Procedural PBR Materials & Detailing
All textures (albedo, bump, and roughness maps) and environment maps (`PMREMGenerator`) are generated procedurally on HTML5 canvases at startup—no external image or 3D model assets required:
- **Flooring:** Glossy `2' × 2'` Alabaster White Carrara vitrified porcelain tiles in living spaces, matte anti-skid stone tiles in toilets, and matte sandstone-grey tiles on the verandah and open terrace.
- **Walls & Ceilings:** Warm ivory interior plaster with baked vertical ambient occlusion, `4"` contrasting skirting with shadow-gap line, ceramic dado wall tiles in toilets, and gypsum false ceilings with a `1"` dark perimeter shadow-gap reveal and recessed cove lighting.
- **Joinery & Fixtures:** Walnut/teak flush doors with brushed stainless steel lever handles and hinges, dark anodized aluminum sliding windows with polished black granite sills and exterior chhajjas, U-shaped granite-tread staircase with steel balusters and teak handrails, wall-mounted split AC indoor units (`24°` LED display), and modular electrical switchboards.
- **Exterior Environment:** Raised `1'-6"` plinth with black granite entrance steps, paved driveway, compound boundary walls, lawn, shade trees, and palm trees.

---

## Architectural Floor Plan (`27'-8" × 53'-0"`)

### Ground Floor
| Space | Dimensions |
| --- | --- |
| Living Room | `19'-3" × 14'-0"` |
| L-Shaped Verandah | `20'-9" × 6'-0"` (front) + `6'-10" × 20'-6"` (east) |
| Kitchen & Passage | `12'-5" × 11'-0"` |
| Central Lobby | `9'-0" × 4'-9"` |
| NW Bedroom | `12'-10" × 14'-0"` |
| NE Bedroom | `12'-10" × 14'-0"` |
| West Toilet | `8'-3" × 5'-0"` |
| East Toilet | `8'-0" × 5'-0"` |
| Under-Stair Toilet | `9'-2" × 3'-9"` |
| Under-Stair Store & Staircase Hall | U-shaped 3-flight staircase (18 risers) |

### First Floor
| Space | Dimensions |
| --- | --- |
| Family Seating & Hall | `12'-5" × 11'-0"` |
| Open Terrace | `20'-9" × 14'-6"` (with `3'-6"` parapet & granite coping) |
| Central Lobby | `9'-0" × 4'-9"` |
| NW Bedroom | `12'-10" × 14'-0"` |
| NE Bedroom | `12'-10" × 14'-0"` |
| West Toilet | `8'-3" × 5'-0"` |
| East Toilet | `8'-0" × 5'-0"` |

---

## Controls

| Input | Action |
| --- | --- |
| `W` `A` `S` `D` or `↑` `←` `↓` `→` | Walk forward / strafe / backward |
| `Shift` | Move faster |
| `Q` / `E` | Turn camera left / right |
| Click & Drag | Look around |
| `Space` or **FPS Look** button | Toggle Pointer Lock mouse look (`ESC` to exit) |
| `M` | Collapse / expand the blueprint mini-map |
| Click on Mini-Map | Teleport to the selected room |
| Touch Drag + On-Screen D-Pad | Look and walk on touch devices |

---

## Running Locally

The project is contained in a single [`index.html`](./index.html) file and loads **Three.js (`0.160.0`)**, **Tailwind CSS**, and the **Inter** font from CDNs, so an internet connection and a WebGL-capable browser are required.

Serve the folder over a local HTTP server (recommended for ES module loading and Pointer Lock support):

```bash
# Using Python 3
python3 -m http.server 8080

# Or using Node.js
npx serve .
```

Then open `http://localhost:8080` in your browser.

---

## Project Structure

```text
.
├── index.html   # Complete 3D WebGL ArchViz engine, procedural PBR textures & Tailwind HUD
└── README.md    # Project documentation
```
