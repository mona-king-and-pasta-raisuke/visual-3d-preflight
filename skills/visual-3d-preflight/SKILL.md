---
name: visual-3d-preflight
description: Plan, build, diagnose, or review interactive and procedural 3D visuals with geometry-first physical invariants, morphology contracts, collision gates, multi-view QA, and performance checks. Use for 3D attachment, growth, deformation, generated topology, scene realism, or recurring visual rework; do not use for ordinary 2D graphics or unrelated UI styling.
---

# Visual 3D Preflight

Prevent repeated visual patching by turning references and physical expectations into testable scene contracts before polishing.

## Choose the workflow

- For a new scene, feature, or architecture change: read all of `references/PREVENTION_SPEC.md`, then copy and fill `assets/VISUAL_3D_PROJECT_SPEC_TEMPLATE.md` in the target project.
- For a visible defect, regression, or review: read the relevant sections of `references/PREVENTION_SPEC.md` and search `references/FAILURE_CATALOG.md` for the observed symptom before editing.
- For a small material-only change: confirm that geometry, support, topology, and motion are already accepted. Do not reopen them without evidence.

## State invariants before implementation

Write the following in the task update or durable project spec before changing visible geometry:

1. The support graph: what surface supports each object.
2. The required contact region and allowed gap or embedding.
3. Forbidden intersections and permitted fusion zones.
4. Scale, orientation, displacement, and world-bound limits.
5. Coordinate-space ownership for rendering, picking, collision, and deformation.
6. Motion or growth forces, fixed regions, and allowed response.
7. Required cameras, lifecycle states, quality tiers, and maximum-complexity case.

Do not invent exact thresholds when the project supplies none. Derive them from scene scale and references, record the assumptions, and make them adjustable.

## Work in this order

1. Convert target references and anti-references into measurable silhouette, branching, scale, surface, contact, motion, and camera constraints.
2. Decide early whether the target requires captured or purchased assets, procedural construction, or a hybrid. Do not force procedural geometry to imitate scan-level detail without evidence.
3. Establish metric geometry, support, contact, collision, and bounds.
4. Verify front, side, low-angle, top, and close-up projections.
5. Establish topology and morphology continuity.
6. Add picking, growth, deformation, and other interactions from the same current world-space geometry that is rendered.
7. Apply material, lighting, ambient occlusion, and artistic polish only after the geometry gates pass.
8. Test maximum complexity, failure states, reload, and performance.

For procedural generation, use **candidate → numerical validation → commit**. Reject or retry invalid candidates before they become visible geometry.

## Preserve physical truth

- Use real mesh intersections, closest-point queries, shape casts, signed-distance queries, or equivalent evidence where practical.
- Treat a center point as insufficient evidence for a broad attachment.
- Allow overlap only in explicitly defined contact or topology-fusion regions.
- Keep picking, rendering, collision, and deformation on the same transformed geometry state.
- Make descendants inherit the parent's local frame, scale laws, morphology profile, surface phenotype, and force field.
- Never use camera bias, an opaque patch, a shared clipping plane, shadow, or ambient occlusion as the sole fix for a geometry defect.

## Diagnose before patching

Classify each defect as geometry/support/collision, topology/morphology, motion/force, surface/material/light, interaction/state/capacity, or performance/resource.

Then:

1. Reproduce it with a fixed seed and the most revealing camera.
2. Identify the failed invariant and the shared system that owns it.
3. Fix all affected instances, not the screenshot coordinates.
4. Add one focused regression test or runtime invariant.
5. Re-run the accepted systems that the change could affect.

After three failed cosmetic variants, stop tuning. Test the most likely incorrect assumption with a numerical probe, alternate view, or minimal reproduction; replace the architecture if necessary.

## Protect accepted work

- Maintain a frozen set of human-approved systems and visual traits.
- State which frozen items a change can affect and run their regressions.
- Keep one active review question at a time when human judgment is required.
- Do not describe an approximation as physically correct. Bound it, document it, and leave a pending or failing invariant test.

## Verification gate

Use the repository's own commands and acceptance files when present. For geometry-affecting work, require at minimum:

- a focused regression for the discovered failure mode;
- finite positions, normals, bounds, and generated buffers;
- support gap/embedding and forbidden-intersection checks;
- scale, radius, angle, displacement, capacity, and world-bound checks;
- normal-view and revealing side or low-angle browser QA;
- console diagnostics with no new physical-scene violations, NaN, warnings, or errors;
- the smallest relevant tests during implementation, then the full required test/typecheck/build gate once before handoff;
- performance evidence at the declared maximum scene complexity.

Visual success cannot override a numerical failure, and numerical success cannot replace visual review.

## Deliverables

When the task is substantial, leave behind:

- a filled project visual-3D spec;
- explicit invariants and thresholds;
- fixed seeds and QA camera presets;
- regression tests or runtime diagnostics;
- a short frozen-set and known-approximation record;
- pass/fail evidence and the one next human review action, if any.
