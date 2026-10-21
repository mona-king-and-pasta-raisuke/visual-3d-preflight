# Case Study: Interactive Coral Growth

This anonymized case study records the systemic failures that led to the Visual 3D Preflight workflow. It contains no original model files, licensed scans, or private project source.

## Initial goal

Create an interactive underwater scene in which coral colonies grow, respond to flow, attach to rendered rock surfaces, and accept user-created branches.

## Why repeated visual fixes failed

The early process evaluated appearance from a primary camera before defining world-space support, contact, topology, morphology, and deformation contracts. Each visible defect received a local visual patch, but the shared geometry system remained unchanged.

Representative failures included:

- broad roots validated by one center sample;
- bases clipped by a horizontal plane rather than rebuilt against the real support;
- mature colonies spaced by root centers while their crowns overlapped;
- new branches stored in a different coordinate or deformation path from the parent;
- child radius and branching grammar unrelated to the local parent structure;
- separate closed meshes overlapped to imitate fusion;
- global flow vectors collapsing local branching angles into parallel lines;
- procedural child surfaces failing to inherit the parent's phenotype;
- hidden capacity and reconstruction limits producing silent failure or invalid geometry;
- validation performed only from the hero camera.

## Systemic response

The workflow was reorganized around six contracts:

1. **Physical scene:** support graph, contact region, legal embedding, forbidden intersections, and mature-volume clearance.
2. **Morphology:** axis architecture, recursion, allometry, taper, curvature, terminals, and surface phenotype.
3. **Interaction:** current visible hit geometry, metric snapping, capacity, rejection reasons, and atomic commits.
4. **Motion:** one authoritative force source, parent-local attachments, fixed roots, and bounded hierarchical response.
5. **Performance:** explicit maximum complexity, finite buffers, detectable overflow, and approved degradation.
6. **Review:** fixed seeds, revealing cameras, regression invariants, and a frozen set of accepted systems.

## General lesson

When the same visual area needs several rounds of cosmetic adjustment, stop tuning the image. Identify the unverified physical or structural assumption, expose it numerically and from a revealing camera, then correct the shared system before returning to materials and lighting.

