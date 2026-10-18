# Velocity Rivals 🏎️

### Unreal Engine 5 · Off-Road Driving Prototype · Blueprints / PCG / Niagara

**Portfolio build: v0.1** · **Status: Work in progress** · **Mode: Free driving**

![Velocity Rivals buggy navigating a desert canyon in-game](screenshots/00-gameplay-hero.jpg)

> A playable off-road vehicle prototype set in a hand-sculpted desert environment. Built to explore **Blueprint gameplay systems**, **terrain and route design**, **procedural environment generation**, and **Niagara visual effects**.

## 🎬 Gameplay — 71-second highlight reel

[![Watch the Velocity Rivals gameplay video](screenshots/06-gameplay-route-arrows.jpg)](media/VelocityRivals_Gameplay_Demo_v01.mp4)

**▶ [Watch / download the gameplay demo (MP4)](media/VelocityRivals_Gameplay_Demo_v01.mp4)**

*Real capture from the playable prototype. Selected gameplay segments have been trimmed into a short reel. Video is silent because the original recording contained no audible sound. It shows the driving systems and environment; it does **not** claim to demonstrate a complete race or the mud splash interaction.*

## At a glance

| Category | Implemented in v0.1 |
| --- | --- |
| Genre | Off-road free-driving prototype |
| Vehicle | Playable buggy, keyboard input, on-screen control UI |
| HUD | Speed/gear readout, boost charge, engine temperature/overheat feedback |
| Level | Custom desert terrain, sculpted routes, Landscape Splines |
| Navigation | Reusable 3D directional arrow markers |
| Environment | PCG vegetation and rock scattering, varied mesh scale/rotation |
| VFX | Blueprint-triggered Niagara water/mud splash system |
| Current scope | Technical prototype; **no checkpoints or lap-completion system yet** |

## 🎮 Driving and route guidance

The free-driving build lets the player navigate a rugged sand route with slopes, dunes, rocks and directional markers. The vehicle UI communicates speed, gear and boost/temperature states. I iterated on the **scale and placement of obstacles** after playtesting to preserve visibility from the third-person vehicle camera.

![In-game off-road route with three blue directional signs](screenshots/06-gameplay-route-arrows.jpg)
*Route markers guide the player through intersections without a traditional asphalt racetrack.*

![Buggy gameplay on a desert route with boost visuals](screenshots/08-gameplay-boost.jpg)
*On-screen boost readiness and engine status provide driving feedback.*

## 🏜️ Building the environment

### 1. Terrain sculpting and off-road course layout

The environment uses **Landscape sculpting, smoothing and Landscape Splines** to create a natural-looking drivable route. I replaced the initial visible track mesh with a sand-based path and created elevated terrain to shape the playable space.

![Unreal Editor aerial view of the sculpted desert route](screenshots/01-offroad-circuit.jpg)
*Terrain and route layout during editor development (guides visible).*

![Route planning and arrow positioning in Unreal Editor](screenshots/05-directional-arrows-editor.jpg)
*In-editor route planning and reusable navigation markers.*

### 2. Procedural rocks and vegetation (PCG)

I configured **PCG Graphs and PCG Volumes** to populate parts of the desert. My graphs use **Get Landscape Data → Surface Sampler → Transform Points → Static Mesh Spawner** to place assets on the Landscape, with controllable density, randomized rotation, and scale variation.

![PCG rock distribution in Unreal Editor](screenshots/02-procedural-rocks.jpg)
*Rock meshes scattered and tuned within PCG volumes.*

![PCG plant distribution in Unreal Editor](screenshots/03-desert-vegetation.jpg)
*Desert vegetation placement and density tuned for the playable camera.*

![Driving through the sculpted canyon](screenshots/07-gameplay-canyon.jpg)
*The resulting environment from the vehicle camera.*

### 3. Water / mud puddle and Niagara splash interaction

I created a reusable **`BP_MudPuddle`** Actor with a water-surface mesh and a **`WaterTrigger`** overlap volume. On player entry, Blueprint compares the overlapping Actor with the player Pawn and spawns the **`NS_MudSplash`** Niagara effect.

![Mud puddle and Niagara spawn logic inside the Blueprint editor](screenshots/04-niagara-mud-trigger.jpg)
*Blueprint implementation captured in-editor. This interaction is implemented but is not clearly shown in the gameplay highlight reel.*

### 4. Blueprint vehicle gameplay / UI

This prototype integrates **Blueprint-based vehicle controls**, player input and UMG widgets. HUD feedback shown in the video includes the speed/gear readout and boost charge with engine overheating behavior. Keyboard and touch-style interface controls were prepared during the project.

![Vehicle viewed from behind in the prototype](screenshots/09-gameplay-vehicle.jpg)
*Playable off-road vehicle and in-game HUD.*

## 🛠️ Technical stack

**Unreal Engine 5** · **Blueprint Visual Scripting** · **Landscape / Splines** · **PCG** · **Niagara** · **UMG Widgets** · **Fab asset integration**

## 👨‍💻 What I contributed

- Assembled and iterated on the playable off-road driving experience and its Blueprint interactions.
- Sculpted and refined the desert terrain and planned the navigable routes.
- Configured PCG Graphs to populate regions with variation in vegetation and rocks.
- Implemented the reusable overlap-triggered water/mud Niagara interaction.
- Integrated route arrows and adjusted visual readability based on gameplay tests.
- Integrated external art assets from Fab. **The third-party meshes and textures are not my original 3D models.**

## 🧭 Next steps

This repository intentionally showcases **version 0.1**, not a finished racing game. Planned improvements include checkpoints, laps, race completion, better collision/boundary handling, surface response, audio, a more polished mud VFX pass, and optimization/performance profiling. **These are not presented as completed features.**

## 📂 Repository structure

```text
VelocityRivals-Portfolio/
├── README.md
├── ASSET_CREDITS.md
├── CV_PORTFOLIO_TEXT.md
├── GITHUB_UPLOAD_PT.md
├── screenshots/           # Captures of gameplay and editor workflows
└── media/
    └── VelocityRivals_Gameplay_Demo_v01.mp4
```

This is a **public portfolio showcase**, not the complete Unreal Engine source project or a downloadable packaged game. Importable third-party art assets are deliberately excluded. Read [asset and licensing notes](ASSET_CREDITS.md).

---

*Independent learning/portfolio project. Unreal Engine is an Epic Games product. This project is not affiliated with or endorsed by Epic Games or MotorStorm.*
