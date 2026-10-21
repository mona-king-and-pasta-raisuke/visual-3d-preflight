# Visual 3D Failure Catalog

Use the symptom column as a lookup key. Confirm the failed invariant before applying a remedy.

| Symptom | Frequent systemic cause | Prevention or correction | Required evidence |
| --- | --- | --- | --- |
| Object begins too large | Only mature scale was specified | Define birth scale, mature scale, and growth curve | Timed screenshots and bounds assertions |
| Growth or interaction feels unresponsive | Cadence is disconnected from experience time | Define first-visible-feedback and completion windows | Timed interaction QA |
| Default scene is unreadably dark | Lighting was tuned only for mood or a manual setting | Define default exposure, black level, and subject legibility | Default-state screenshots |
| Organic surface looks plastic or computer-generated | Regular tubes and procedural noise carry all form and detail | Decide scan/model/procedural responsibilities early | Close-up comparison with target references |
| Root or attachment floats | Support uses a proxy plane or curve instead of rendered geometry | Query the rendered support mesh and validate a contact region | Gap/embedding gate plus low-angle view |
| Base looks horizontally cut | A shared clipping plane substitutes for anatomy | Reconstruct a local base that converges to the real attachment | Side, low, and silhouette checks |
| Base retains dangling fragments | Lower geometry was compressed but not topologically rebuilt | Define a root rebuild region and minimum residual-feature size | Extreme low-angle inspection |
| Base looks pasted on or shifted toward camera | Camera-depth bias conceals bad contact | Derive depth from support geometry | Side occlusion and depth-order checks |
| Attachment and visible support disagree | Picking, placement, and rendering use different geometry states | Share one current world-space hit and transform chain | Click replay and support-graph diagnostics |
| Mature objects overlap | Placement checks only root-center distance | Reserve mature crown or swept volume | Mature-volume clearance test |
| Flow particles are too faint or slow | Solver strength and visual legibility are coupled | Specify physical and visual advection/opacity separately | Still, reverse, and sustained-input QA |
| Flow does not affect individual branches | Only the whole object moves or history is invisible | Sample one field per active structure with hierarchical response | Directional input comparison |
| New growth sticks to the background | Parent and child use different coordinate or deformation paths | Store parent-local attachment and recompute from the parent each frame | Motion close-up and relative-root drift test |
| New branch disconnects from the parent | Two closed meshes merely touch | Use shared topology, a bounded local reconstruction, or a continuous field | Connectivity, close-up, and low-angle evidence |
| Capacity silently stops at N | Hidden allocation or business limit | Declare capacity and visible rejection reasons | Maximum and maximum + 1 regression |
| New growth does not branch naturally | A straight or generic Y generator ignores morphology | Drive recursion and branching from the parent profile and local structure | Graph statistics and fixed-seed comparison |
| Child thickness ignores the parent | A fixed root radius is used | Estimate the real parent cross-section and apply bounded allometry | Thick-parent and thin-parent cases |
| A ball, knot, or ring appears at the joint | Spheres, repeated kernels, or caps fill the seam | Generate a joint only for a true topology node | Node-type regression and close-up |
| Stem appears segmented or beaded | Each segment is independently capped or discontinuous | Use continuous centerline, radius interpolation, and shared surface | Curvature, tangent, radius, and normal continuity |
| Child becomes a hair-thin line | Scale inheritance is absent or taper is too aggressive | Constrain root, child, and terminal radii relative to parent level | Allometry tests |
| Branches become parallel | A global vector or upward bias overrides local angles | Rotate local frames with bounded response | Pre/post-force branch-angle floor |
| Added branch has the wrong surface | Only color or broad material was inherited | Inherit micro-branches, relief, roughness, and response profile | Same-organism close-up comparison |
| A near-miss click grows from empty space | Screen-near vertices or stale proxies are accepted | Resolve only to current, visible, foremost triangles within a metric snap radius | Hidden-surface and near-click regressions |
| Added morphology differs from the parent | Only a class name selects generic parameters | Gate on global phenotype and local morphology | Parent-by-location seed matrix |
| Added branch looks like a separate object | Closed surfaces overlap without local replacement | Remove or replace the old local surface and fuse parent and child together | Junction topology and revealing highlight |
| Unrelated branches melt together | Implicit field is too wide or collisions occur after commit | Restrict fusion zones and validate capsule/mesh clearances first | Segment-triangle and capsule-capsule tests |
| Mesh disappears or contains NaN | Reconstruction buffers are fixed below real complexity | Size capacity from input, detect overflow, and commit atomically | Maximum-complexity build and finite bounds |
| Load failure displays an ugly substitute | Loading, ready, and failed states are conflated | Specify state visibility and approved fallback behavior | Three-state visual test and reload |
| Hero view looks correct but side view fails | Validation is composition-specific | Require normal, side, low, top, and close-up gates | Fixed camera matrix |

## Classification shorthand

- **G** — geometry, support, clearance, collision, bounds.
- **T** — topology, hierarchy, morphology, continuity.
- **M** — motion, force, deformation, growth response.
- **S** — surface, material, light, exposure.
- **I** — interaction, picking, state, capacity, feedback.
- **P** — performance, resource loading, buffers, degradation.

A screenshot may expose more than one category. Diagnose each invariant separately instead of adding one multi-purpose visual patch.
