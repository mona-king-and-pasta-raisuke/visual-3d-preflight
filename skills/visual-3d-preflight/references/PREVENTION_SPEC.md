# Visual 3D Rework-Prevention Protocol

Use this protocol to turn an aesthetic target into inspectable physical, structural, interactive, and operational requirements. It applies to interactive scenes, procedural objects, growth systems, grafts or attachments, deformed meshes, and model-based visual experiences.

## 1. Translate visual language into contracts

Words such as “natural,” “photographic,” “soft,” or “not computer-generated” are directions, not acceptance criteria. Translate them into:

- silhouette architecture and occupied volume;
- axis hierarchy, branch grammar, recursion, asymmetry, and curvature;
- length and radius ratios by structural level;
- surface phenotype such as smoothness, grain, spines, hair, pores, or mineral relief;
- support and attachment mode;
- fixed and deformable regions;
- force response and propagation by hierarchy;
- required camera distances and revealing angles.

Annotate every target reference with what must be copied and every anti-reference with what must be avoided. Rank silhouette, physical relationship, surface, color, and motion so tradeoffs are explicit.

## 2. Establish the input package

### References and anti-references

Provide enough images or models to cover full shape, attachment, topology, surface close-up, and behavior. A reference folder without structural annotations is incomplete.

### Metric and coordinate contract

Declare:

- world units and model scale;
- model origin, root, center of mass, bounds, and interaction anchor;
- asset-local, instance-local, organism-local, world, view, and screen conversions;
- the geometry state used by rendering, picking, collision, shadows, and deformation;
- allowed scale, radius, rotation, tilt, curvature, and displacement.

Name coordinates semantically. Avoid persistent ambiguous names such as `point` or `position` where the space matters.

### Support graph

For each visible object, record:

- its supporting object or surface;
- the region that must contact;
- permitted gap and embedding;
- forbidden overlaps;
- how it follows a moving or deforming support;
- behavior when the support is missing or fails to load.

A broad root, plate, pad, foot, or bracket needs a contact-region test. A single center sample does not prove contact.

### Morphology profile

Each generated or extensible class needs its own profile:

- axis model: persistent leader, dichotomous, lateral, radial, fan, or irregular;
- branching interval and angle distributions;
- main-axis and side-axis directional persistence;
- recursion rules and terminal behavior;
- radius inheritance and taper per level;
- curvature, planarity, three-dimensional spread, and asymmetry;
- surface phenotype and its scale hierarchy;
- maximum depth, tips, segments, volume, and spatial extent.

Reject generation when the required profile is absent. A generic Y-tree is not a safe fallback.

### Asset and material strategy

Make a buy/build/reuse decision before procedural modeling:

- Is a licensed scan or model already suitable in topology and scale?
- Does the target depend on captured surface irregularity?
- What belongs to procedural geometry, a scan shell, textures, displacement, or shader detail?
- Does motion require deformable topology or only a rigid/limited deformation binding?
- Are license, source, triangle count, UVs, normals, compression, and offline availability acceptable?

If photographic naturalism is a priority, evaluate real capture early instead of treating it as a late rescue.

### Interaction contract

For each action, define:

- eligible visible geometry;
- the exact hit evidence;
- whether snapping is permitted and its maximum metric distance;
- the surface or topology entity to which snapping resolves;
- whether the result is a new object, topology change, or state change;
- capacity and failure reason codes with visible feedback;
- immediate versus progressive geometry creation and its cost.

Screen proximity alone is not attachment evidence. Resolve to the foremost visible, currently deformed, real surface.

### Motion and growth contract

Declare:

- the authoritative force field or solver;
- real-time deformation versus permanent growth bias;
- fixed root or support region;
- response by arc length and hierarchy;
- whether parents and descendants sample the same field;
- how original branch angles and local frames survive direction changes;
- post-deformation collision and clearance requirements.

Avoid adding a global force vector directly to every branch direction. Use local-frame rotations or bounded response so structure does not collapse into parallel lines.

### Performance contract

Set target devices, frame rate, geometry, draw-call, texture, memory, CPU, and GPU budgets. Include per-instance and per-topology-edit budgets. For CSG, SDF, marching cubes, BVH, or mesh reconstruction, define when work occurs, what is cached, how capacity is derived from input complexity, and whether excess work is rejected, deferred, or degraded.

Never permit overflow, out-of-bounds reads, NaN, or partially committed geometry as a degradation mode.

## 3. Required implementation order

### Phase 0 — requirements freeze

Deliver target and anti-reference annotations, priority order, devices, camera matrix, interaction story, and failure states.

Gate: product, visual, and implementation owners describe the same failure conditions.

### Phase 1 — physical greybox

Implement scale, support, contact, clearance, root/attachment, bounds, and multi-instance spacing without final materials.

Gate: numerical reports are clear and normal, side, low-angle, and top views all pass.

### Phase 2 — topology and morphology

Implement silhouette, hierarchy, taper, terminals, local fusion, and phenotype ownership.

Gate: every architecture, coarse and fine parent region, root/mid/tip interaction, fixed seed, and maximum capacity has coverage.

### Phase 3 — interaction and motion

Add picking, snapping, growth, deformation, following, capacity, and rejection feedback.

Gate: input, state, and rendered outcome have repeatable causality; descendants do not detach or move through a separate path.

### Phase 4 — material and lighting

After geometry is locked, add roughness, color, translucency or scattering approximations, relief, exposure, and atmosphere.

Gate: defaults are readable, close highlights do not reveal seams, and the lowest quality tier preserves structural identity.

### Phase 5 — stress and failure

Test maximum scene complexity, resource failure, reload, service recovery, graphics-context events, and low-performance hardware.

Gate: no silent rejection, partial mesh, unapproved fallback, NaN, overflow, or unrecoverable state.

### Phase 6 — human review

Present one bounded decision at a time and keep accepted systems frozen.

Gate: the reviewer explicitly accepts, rejects, or requests a handoff. Automated success does not imply visual acceptance.

## 4. Geometry and topology rules

### Legal contact and fusion

Allow overlap only within declared root/contact regions or true shared topology nodes. Scale the allowed fusion region from local geometry and cap it. Graph adjacency does not exempt an entire segment from collision.

### Forbidden contact

Fail candidates that intersect a support outside the contact region, an existing extension, a nonadjacent segment, a forbidden scene object, or another surface merely because a wide implicit field joined them.

### Candidate commit sequence

For each generated element:

1. Generate candidate direction, length, and radius from the morphology profile, local frame, and current force.
2. Query the current deformed support or parent surface.
3. Check candidate-versus-scene and candidate-versus-existing clearance.
4. Check nonadjacent self-clearance.
5. Check world bounds, volume, tip, segment, instance, and memory budgets.
6. Try only a small number of profile-consistent alternatives.
7. Terminate or visibly reject when none pass.
8. Commit graph, mesh, simulation, and render state atomically only after success.

### Continuity

Check separately:

- positional continuity of centerlines or shared topology;
- tangent continuity so one tube does not appear inserted into another;
- radius continuity derived from the parent cross-section;
- surface continuity without rings, balls, caps, or cracks;
- normal continuity under revealing highlights;
- motion continuity: the root follows the parent and relative bending increases away from it;
- phenotype continuity: surface detail and branching statistics belong to the same profile.

## 5. QA matrix

Use fixed seeds and fixed camera presets. At minimum, cross the dimensions below that are affected by the change:

| Dimension | Minimum coverage |
| --- | --- |
| Camera | normal, side, low-angle, top, close-up |
| Lifecycle | initial, growing/changing, mature, maximum capacity |
| Location | root, thick region, fine region, terminal, edge, near-miss |
| Structure | each morphology profile with at least one fixed seed |
| Motion | still, sustained direction, reversal, disturbance or circular input |
| Count | single, multiple, threshold spacing, maximum, maximum + 1 |
| Quality | highest and lowest supported tier |
| State | loading, ready, failed, reload, recovery |

## 6. Numerical and operational gates

Check when applicable:

- support gap and embedding;
- attachment lateral drift;
- projected contact in multiple cameras;
- mature-volume clearance, not only root-center distance;
- collision outside true topology nodes;
- scale, angle, displacement, radius, curvature, and world bounds;
- finite positions, normals, bounds, and buffers;
- tip, segment, instance, topology-edit, mesh, and memory budgets;
- asset loading and approved fallback states;
- frame-time behavior at representative maximum complexity.

Every diagnosed visible bug should produce a focused regression or runtime invariant. Before handoff, run the repository's required focused tests, full test gate, strict typecheck, production build, browser views, diagnostics, console check, and performance gate.

## 7. Change control

- Record human-approved traits as a frozen set.
- Classify new feedback before changing code.
- State impact on frozen systems and rerun their regressions.
- Fix the owning rule for all seeds and future instances, not one screenshot.
- Reject camera-specific constants unless the feature is explicitly camera-space.
- After three failed visual variants, stop parameter tuning and test the underlying assumption.
- Label, bound, and test every temporary approximation.

## 8. Definition of ready

Implementation may start only when:

- targets and anti-targets are structurally annotated;
- support, coordinate spaces, and legal/illegal contact are explicit;
- every required generated class has a morphology profile;
- captured, purchased, reused, and procedural responsibilities are decided;
- normal and revealing views are defined;
- maximum complexity and performance budgets are defined;
- at least five likely failure modes have planned tests.

## 9. Definition of done

The result is complete only when:

- required views show no floating, clipping, false fusion, unintended intersection, patch, joint ball, or seam;
- structure, scale, surface, and motion follow the chosen references as one coherent profile;
- interactions hit real visible geometry and expose rejection or capacity states;
- motion uses the declared force source without detachment or angular collapse;
- maximum complexity has no overflow, NaN, unacceptable slowdown, or partial commit;
- loading, failure, reload, and recovery do not reveal unapproved substitutes;
- automated checks, build gates, multi-view QA, and human review all pass.
