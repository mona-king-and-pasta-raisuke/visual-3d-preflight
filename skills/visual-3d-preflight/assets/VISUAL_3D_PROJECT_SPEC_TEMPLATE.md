# [Project Name] Visual 3D Specification

Status: Draft  
Owner:  
Last updated:  

## 1. Target experience

- What the user sees:
- What the user can do:
- First visible response time:
- Mature or completed time:
- Highest-priority visual trait:
- Explicit non-goals:

## 2. References and anti-references

| Source | Adopt | Reject | Evidence or measurement |
| --- | --- | --- | --- |
|  |  |  |  |

- Silhouette contract:
- Hierarchy and branching contract:
- Scale-ratio contract:
- Surface phenotype contract:
- Motion contract:

## 3. World and scale

- World unit:
- Model origin:
- Root or support anchor:
- Bounds and center of mass:
- Asset-local → instance-local → world transform:
- Picking geometry state:
- Collision geometry state:
- Scale, orientation, curvature, and displacement limits:

## 4. Physical-scene invariants

### Support graph

| Object | Supported by | Required contact region | Gap/embedding tolerance | Follow behavior |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

### Legal contact and fusion

- 

### Forbidden intersections

- 

### Mature-volume clearance

- 

## 5. Morphology profiles

Repeat for each generated or extensible type.

### [Profile name]

- Primary-axis model:
- Branch hierarchy and recursion:
- Branch interval and angle distribution:
- Directional persistence and asymmetry:
- Radius inheritance and taper:
- Curvature and planarity:
- Terminal behavior:
- Surface phenotype:
- Maximum depth, tips, segments, volume, and bounds:
- Required fixed seeds:

## 6. Interaction contract

- Eligible hit geometry:
- Exact hit evidence:
- Snap distance and target rules:
- Successful result:
- Rejection reasons and user feedback:
- Capacity and maximum + 1 behavior:
- Atomic or progressive topology update:

## 7. Motion and growth contract

- Authoritative force source:
- Fixed region:
- Response by arc length and hierarchy:
- Parent/child synchronization:
- Local-frame and branch-angle preservation:
- Permanent growth bias:
- Post-deformation collision rules:

## 8. Asset, material, and lighting strategy

- Buy/build/reuse decision:
- Licenses and sources:
- Procedural-geometry responsibility:
- Scan/model responsibility:
- Texture/displacement/shader responsibility:
- Default exposure and readability baseline:
- Loading, ready, failed, and fallback visuals:

## 9. Performance budget

- Target devices and FPS:
- Triangle, draw-call, texture, and memory budget:
- CPU and GPU update budget:
- Per-instance and per-topology-edit budget:
- Maximum instances and topology complexity:
- Reconstruction/CSG/SDF/BVH schedule and cache:
- Overflow, rejection, delay, and degradation behavior:

## 10. Automated acceptance

| Invariant | Threshold | Test or diagnostic | Representative scene |
| --- | --- | --- | --- |
| Support gap/embedding |  |  |  |
| Forbidden intersections |  |  |  |
| Mature clearance |  |  |  |
| Scale/radius/angle/bounds |  |  |  |
| Finite geometry and buffers |  |  |  |
| Capacity and maximum + 1 |  |  |  |
| Performance |  |  |  |

## 11. Visual QA matrix

- Fixed cameras: normal, side, low-angle, top, close-up.
- Lifecycle: initial, changing/growing, mature, maximum capacity.
- Locations: root, thick region, fine region, terminal, edge, near-miss.
- Structures and fixed seeds:
- Motion inputs: still, sustained, reverse, disturbance.
- Counts: single, multiple, threshold spacing, maximum, maximum + 1.
- Quality tiers:
- States: loading, ready, failed, reload, recovery.

## 12. Frozen set

Record each human-approved system or visual trait and its regression gate.

| Frozen item | Acceptance evidence | Reopen condition |
| --- | --- | --- |
|  |  |  |

## 13. Known approximations

| Approximation | Bound and risk | Pending/failing invariant | Removal plan |
| --- | --- | --- | --- |
|  |  |  |  |

## 14. Definition of ready

- [ ] References and anti-references are structurally annotated.
- [ ] Support, spaces, legal contact, and forbidden contact are explicit.
- [ ] Every generated class has a morphology profile.
- [ ] Asset versus procedural responsibilities are decided.
- [ ] Normal and revealing views are fixed.
- [ ] Maximum complexity and performance budgets are defined.
- [ ] At least five likely failures have planned tests.

## 15. Definition of done

- [ ] Numerical invariants pass.
- [ ] Focused regressions and the full required test/build gate pass.
- [ ] Required cameras and lifecycle states pass visual QA.
- [ ] Maximum complexity, failure, reload, and recovery pass.
- [ ] No new console error, warning, NaN, overflow, or partial commit exists.
- [ ] Frozen systems retain their accepted behavior.
- [ ] Human review explicitly passes the result.
