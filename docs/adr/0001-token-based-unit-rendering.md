---
status: accepted
---

# Token-based unit rendering on an isometric board

The battle grid is rendered isometric, but Master and Natial units are not modeled or hand-animated as isometric characters. The team has no dedicated artist and produces 2D art via AI image generation, which cannot reliably hold a consistent character across multiple angles or animation frames — a hard requirement for directional isometric sprites (whether hand-drawn or pre-rendered from 3D). Units are instead represented as flat, camera-facing "token" portraits (a single AI-generated illustration per unit, cropped to a chip) placed on the isometric tiles; movement, attacks, and hits are expressed through code-driven animation (tweened position, scale punches, particles) rather than drawn frames. Board tiles and terrain are sourced separately (asset packs or procedural), decoupled from the AI illustration pipeline.

## Considered Options

- 3D models rendered in real time from an orthographic camera, or pre-rendered to sprites — rejected: requires 3D modeling/rigging skill the team doesn't have.
- Hand-drawn directional 2D isometric sprites — rejected: scales worst with content volume and isn't compatible with single-shot AI illustration generation.
- img-to-3D AI conversion (e.g. Meshy, Tripo3D) of the AI illustrations — deferred as a future experiment; current quality/rigging maturity too inconsistent to commit to now.

## Consequences

Switching to fully animated, directionally-consistent unit art later requires rebuilding the rendering pipeline (token compositing → sprite/3D pipeline), not just adding assets.
