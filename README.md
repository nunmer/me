# me.steppe.run

A personal site built as a single isometric 3D room. You orbit it and click the
objects on the desk instead of scrolling a page. Every section of a normal
portfolio lives as something physical: the monitors are the jobs, the shelf is
the side projects, the pegboard is the skills, the mail tray is the contact
details, and the gear corner is the endurance sports.

One self-contained `index.html`. Three.js r128 from a CDN is the only
dependency. No build step, no framework, no bundler.

## The performance idea

The constraint was that it had to hold up on very old integrated graphics
without giving up the lighting. The approach:

**Nothing in the scene is a light.** A five-source rig (desk lamp, monitor
spill, shelf LED strip, pegboard clip lamp, floor bounce) plus hemispheric
ambient and fake corner occlusion is evaluated once at startup and written into
per-vertex colours. Everything then renders with `MeshBasicMaterial`, so the
fragment shader does no lighting maths at all. The rig is free at runtime, which
means it can be as elaborate as it needs to be.

Everything else follows from that:

- All static geometry merges into one mesh, so the floor, both walls, the desk,
  the chair, the lamp, the shelf, the pegboard and every bit of clutter cost a
  single draw call. Whole scene is about 30.
- Vertex normals are consumed during the bake and then discarded, since nothing
  downstream needs them. Six floats per vertex instead of nine.
- The render buffer scales itself between 0.45x and 1.0x from measured frame
  time. Fill rate is what old GPUs run out of first, so the page trades pixels
  and never geometry or lighting.
- Rendering is on demand. On a machine that does not get ambient animation, an
  untouched room renders nothing at all and the loop parks.
- Known-weak GPUs are detected up front and start coarser, without dust motes.
- No post-processing, no shadow maps, no `backdrop-filter`. The panels use
  layered translucency instead of blur, and the background is a CSS gradient
  behind a transparent canvas, so it never touches the GPU.

Camera state is kept in spherical coordinates rather than on the camera object,
so every constraint is enforced before the camera moves. No drag or framing
animation can put you through the floor or behind a wall.

Without WebGL, the same content renders as a typeset reading version.

## Layout

- `index.html` — the whole site
- `CONTENT.md` — the copy, written before the build
- `DESIGN.md` — the spatial concept and build sequence

Content is a plain JS object keyed by object id, so editing the writing never
means touching the geometry code.
