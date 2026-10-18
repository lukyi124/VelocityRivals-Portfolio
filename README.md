# Velocity Rivals 🏎️

### Off-Road Driving Prototype | Unreal Engine 5 | Blueprints

**Status:** v0.1 — Work in Progress  
**Focus:** Gameplay prototyping, procedural environment generation, level design, and real-time VFX

Velocity Rivals is a **playable off-road driving prototype** developed in Unreal Engine 5. The project explores vehicle controls, terrain creation, procedural placement of desert vegetation and rocks, visual navigation aids, and reactive water/mud effects.

The current version is a **free-driving demonstration**, **not yet a complete racing game**: checkpoints, lap tracking and race completion are planned for a future iteration.

## Screenshots

![Off-road terrain and circuit layout developed with Landscape Splines](screenshots/01-offroad-circuit.jpg)
*Terrain and route layout in the Unreal Editor (editing guides visible).*

| Procedural rocks | Procedural desert vegetation |
| --- | --- |
| ![Rocks scattered across the desert](screenshots/02-procedural-rocks.jpg) | ![Desert bushes placed with PCG](screenshots/03-desert-vegetation.jpg) |

> These are development screenshots. A gameplay demonstration video may be added later.

## Implemented systems

- **Vehicle gameplay (Blueprints):** drivable off-road vehicle, keyboard and on-screen driving controls, boost, and related UI indicators.
- **Terrain and route design:** sculpted desert landscape and a driving route shaped with Landscape Splines, without relying on a conventional asphalt road surface.
- **Navigation aids:** reusable Blueprint-based directional arrow actors to guide the driver at turns and junctions.
- **Procedural Content Generation (PCG):** placement of multiple desert plant and rock meshes within configurable volumes, with variation in density, scale and orientation.
- **Water and mud interactions:** reusable `BP_MudPuddle` actor with a water surface, trigger overlap events, and Niagara splash spawning when the player vehicle enters the trigger.
- **World-building iteration:** continuous adjustments to terrain, prop placement and visibility based on playtesting.

## Technical highlights

| Area | Tools / techniques |
| --- | --- |
| Engine | Unreal Engine 5 |
| Gameplay scripting | Visual scripting with Blueprints |
| Terrain | Landscape, sculpting, Landscape Splines |
| Procedural placement | PCG Graph, Surface Sampler, Transform Points, Static Mesh Spawner |
| Particle effects | Niagara System, burst emission, splash particles |
| User interface | Unreal Motion Graphics / Widgets |
| Content integration | Third-party assets from Fab, adapted and assembled into a playable level |

### What I worked on

I implemented and configured the playable driving prototype, designed the off-road terrain and route, created procedural vegetation and rock placement workflows, set up the directional arrow Blueprint, and built the mud/water trigger-and-splash interaction. The focus has been on learning how Unreal Engine systems connect in a working project, rather than simply placing static assets.

## Current scope and next steps

**Available in v0.1:** free driving around the desert track, vehicle controls and HUD, environment dressing, directional signs, and experimental water/mud splash effects.

**Planned for later versions:** checkpoints, laps and race results; expanded vehicle audio and ground feedback; improved driving surface details; further optimization and polish.

## Project availability

This repository is a **portfolio showcase** containing documentation and development screenshots. The full Unreal Engine project is **not included in this public repository**, in part because it relies on third-party assets subject to their own licenses.

## Asset attribution and rights

The vehicle and multiple environment meshes, materials and other assets were sourced from external packs, including assets distributed through **Fab**. All rights to third-party content remain with their respective creators. My contributions are the project setup, Blueprint logic and integrations, level design, environment assembly, and PCG/Niagara configuration described above.

See [ASSET_CREDITS.md](ASSET_CREDITS.md) for details and the ongoing asset attribution checklist. Screenshots are for portfolio presentation only.

---

*Personal learning and portfolio project. Not affiliated with or endorsed by Epic Games.*
