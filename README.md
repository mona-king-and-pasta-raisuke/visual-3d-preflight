# Visual 3D Preflight

> A geometry-first Codex and ChatGPT skill for preventing repeated visual rework in interactive and procedural 3D scenes.

[中文说明](#中文说明)

Visual 3D Preflight turns vague goals such as “natural,” “physically plausible,” or “not computer-generated” into explicit, testable contracts for:

- support and contact;
- collision and clearance;
- morphology and branching;
- attachment and topology continuity;
- motion and growth response;
- materials and surface phenotype;
- multi-view visual QA;
- performance and failure states.

Use it before implementation, or whenever repeated visual fixes suggest that the real problem is systemic geometry rather than styling.

This is not a renderer or a 3D model generator. It is a planning, implementation, diagnosis, and QA workflow.

## What problem does it solve?

Interactive 3D work often looks acceptable from one camera and then fails from another: roots float, attachments split, procedural branches intersect, motion detaches from the parent, surface identity changes, or a material patch conceals incorrect geometry.

This skill prevents that cycle by requiring physical-scene invariants before artistic polish and by using a **candidate → numerical validation → commit** workflow for generated geometry.

## Install with Codex

Ask Codex:

```text
Use $skill-installer to install:
https://github.com/mona-king-and-pasta-raisuke/visual-3d-preflight/tree/main/skills/visual-3d-preflight
```

Codex can then invoke the skill automatically when a task matches its scope, or you can invoke it explicitly with `$visual-3d-preflight`.

## Quick start

```text
Use $visual-3d-preflight to preflight an interactive coral growth scene.
Before implementation, define its support graph, contact regions, morphology
profiles, collision rules, motion contract, performance budget, and QA matrix.
```

For diagnosis:

```text
Use $visual-3d-preflight to diagnose why these generated branches look fused
and physically implausible. Identify the failed invariant before proposing a fix.
```

## What is included?

```text
skills/visual-3d-preflight/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── PREVENTION_SPEC.md
│   └── FAILURE_CATALOG.md
└── assets/
    └── VISUAL_3D_PROJECT_SPEC_TEMPLATE.md
```

- `SKILL.md` — the executable workflow and verification gates.
- `PREVENTION_SPEC.md` — detailed geometry-first project protocol.
- `FAILURE_CATALOG.md` — symptom-to-root-cause diagnostic reference.
- `VISUAL_3D_PROJECT_SPEC_TEMPLATE.md` — reusable pre-production specification.

## Core principles

1. Physical-scene truth comes before visual concealment.
2. Support, contact, collision, topology, and bounds are numerical contracts.
3. Picking, rendering, collision, and deformation use the same transformed geometry.
4. Procedural geometry is validated before it is committed.
5. Normal, side, low-angle, top, and close-up views are separate gates.
6. Every diagnosed visible defect leaves a regression test or runtime invariant.
7. Accepted systems remain frozen unless evidence justifies reopening them.

## 中文说明

Visual 3D Preflight 是一个适用于 Codex 与 ChatGPT 的 3D 视觉防返工 Skill。

它不会替你生成模型，而是把“自然”“符合物理逻辑”“不要电脑生成感”等模糊要求，转换成可以检查的支撑、接触、形态、碰撞、动态、多视角与性能规范。

适合用于：

- 互动或程序生成的 3D 场景；
- 生长、嫁接、附着与局部几何融合；
- 物体悬空、穿插、断裂或假融合问题；
- 母体与新增结构的形态、表面和运动继承；
- 需要减少视觉返工的 3D 项目开工检查。

## Case study

The anonymized coral-growth case study in [`examples/coral-growth-case-study.md`](examples/coral-growth-case-study.md) explains the repeated failure patterns that motivated the workflow. It contains no proprietary models or third-party scan assets.

## License

MIT. See [`LICENSE`](LICENSE).

