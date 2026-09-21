# Personal Website — Design Concept

Status: Concept locked, pending build. This doc defines the spatial concept, interaction model, content mapping, visual style, and build sequence for the site.

---

## Concept

**"The Workshop"** — a single isometric 3D diorama room, rendered in Three.js, that the visitor freely orbits and explores by clicking objects rather than scrolling through pages. The room is a stylized loft/studio corner: a desk with monitors, a project shelf, a tool wall, a corkboard, small framed/background details. Every piece of content from CONTENT.md lives as a physical object in the room instead of a page section.

The goal: the site feels like a place, not a document. A visitor "walks in," looks around, and picks what to examine — the way you'd look around someone's actual desk.

---

## Camera & Navigation

- **Mode:** Free orbit camera (OrbitControls), constrained — no flipping below the floor plane, min/max zoom distance locked so the room always reads as a diorama, not open space.
- **Default state:** A fixed "establishing" angle on load — three-quarter isometric view of the whole room, nothing zoomed in.
- **Object interaction:**
  - Hover → soft outline/glow on the hovered object, cursor changes to a pointer.
  - Click → camera eases (smooth interpolation, ~0.8–1.2s) into a framed close-up of that object.
  - A content panel slides in from the side (glassmorphic/translucent overlay, doesn't fully obscure the 3D scene behind it) with the actual text content for that object.
  - "Back" control (explicit arrow/button, plus click-elsewhere-in-void) eases the camera back to the default establishing shot and dismisses the panel.
- **No first-person movement, no WASD, no pointer-lock** — orbit + click only, so it works cleanly with a plain mouse and doesn't demand any onboarding/tutorial.

---

## Content → Object Mapping

| Content section | Object in the room | Notes |
|---|---|---|
| Hero / About | Framed piece on the wall or an open notebook on the desk | First thing in the default view — establishes identity before anything else |
| Experience (ForteBank, Snoonu) | Monitor cluster on the desk (multiple screens) | Each screen/monitor = one role or sub-section; click a screen to open that role's panel |
| Independent Projects | Shelf or pegboard of small objects, one per project | Visual state communicates status (see Visual Style below) |
| Skills | Tool wall / pegboard, or bookshelf with labeled spines | Grouped by category (Languages, Backend & Infra, Data Engineering, AI/ML) |
| Education | Small framed diploma | Background detail, not a focal point — understated placement |
| Contact | Phone or mail tray object on the desk | Click opens a simple panel with email/GitHub/LinkedIn links |
| Endurance Sports | Gear corner — a propped bike (S-Works SL9), a pair of running shoes (EVO SL) by the door, a small medal/trophy hook | A lighter, personal counterpoint to the desk/work objects; medals hang as physical objects, one per race result |

---

## Visual Style

- **Geometry:** Low-poly, flat-shaded primitives, hand-built in Three.js code (no external 3D model imports — geometry is composed from boxes, cylinders, and simple extrusions). This reads as an intentional aesthetic choice, not an unfinished asset.
- **Lighting:** One warm key light (desk lamp) as the dominant source, soft ambient fill for the rest of the room, subtle dust/particle motes in the lamp's light cone for atmosphere.
- **Background:** Dark void or soft gradient behind the room — keeps focus on the diorama, reinforces the "one contained space" feeling.
- **Project status states** (on the shelf/pegboard objects):
  - **In Progress** — subtle glow/emissive material, small animated detail (e.g. a spinning fan icon or blinking light)
  - **Coming Soon** — wireframe/blueprint-style material, half-built silhouette
  - **Concept** — flat sketch/paper texture pinned to a corkboard, not a 3D object at all
- **Color palette:** TBD in a follow-up pass — likely a warm neutral room (wood/desk tones) against a cool dark background, so screens and glowing elements pop.

---

## Tech Stack

- **Rendering:** Three.js (r128, loaded as UMD `<script>` from cdnjs — no ES module imports, single self-contained HTML file)
- **Controls:** Three.js OrbitControls (constrained), custom raycasting for hover/click detection on objects
- **UI overlay:** Plain HTML/CSS panels layered over the canvas (glassmorphic style), not part of the 3D scene
- **Content:** Sourced from CONTENT.md — text lives in a JS data object mapped to object IDs, not hardcoded into geometry-building code, so content edits don't require touching the 3D logic
- **Delivery:** Single self-contained HTML file, published as an Artifact

---

## Build Sequence

1. **Shell** — empty room geometry, camera, lighting, constrained OrbitControls. Confirm the feel before investing in object detail.
2. **Desk + monitor cluster** — Experience content wired up, click/hover/panel interaction proven end-to-end on this one object first.
3. **Project shelf/pegboard** — all independent projects, including the three visual status variants.
4. **Skills wall** — tool wall or bookshelf, grouped by category.
5. **Remaining details** — About/notebook, Education frame, Contact object.
6. **Polish pass** — lighting refinement, hover/transition easing, panel animation timing, color palette finalization.

---

## Open Decisions (for next pass)

- Final color palette for room + lighting
- Exact object each piece of content lives on visually (e.g. is Experience one monitor with tabs, or three separate screens?)
- Whether a subtle ambient sound/loop is in scope
- Mobile fallback behavior (per earlier discussion: desktop-first, mobile just needs to function — likely a simplified/static fallback rather than a scaled-down 3D scene)
