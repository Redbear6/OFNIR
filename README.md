# OFNIR

OFNIR is a tactical Elden Ring modding workspace focused on **projects, comparisons, and cross-file understanding** rather than being yet another single-purpose editor. It is meant to become a project-centered source of truth where you can see how your changes in one domain affect related assets elsewhere, without juggling a dozen separate tools and notes.

Right now this is an early-stage, design-heavy project: the initial goal is to build a strong foundation (shell, project model, compare and validation flows) before chasing full feature parity with existing community editors.

---

## Long‑term vision (Roadmap Mile 100)

The long‑term aim for OFNIR is to become a **multi‑game modding suite/container** built on a common “source of truth” core.

- The core concepts (project, asset, relationship, diff, validation, conflict, snapshot) are intentionally game‑agnostic.
- Game support is provided through containers or “packs” (for example, an Elden Ring container, a Crimson Desert container) that plug into that core.
- In the Mile 100 vision, you could load an Elden Ring container alongside a Crimson Desert container and work across both in one workspace, using the same compare, validation, and project concepts instead of juggling separate tools and mental models.

### Game‑agnostic foundation

Even though Phase 1 targets Elden Ring first, the core should stay game‑agnostic wherever practical:

- The project model (projects, assets, relationships, conflicts, validation, snapshots) should not hard‑code Elden Ring assumptions when a generic concept will do.
- Game‑specific behavior should live in containers or modules layered on top of the shared core (for example, an “Elden Ring container” that plugs in formats, validators, and tool windows).
- Cross‑game support later (e.g. Elden Ring + Crimson Desert in one workspace) should be a matter of loading multiple containers into the same core, not rewriting the core for each game.

This keeps Phase 1 honest to its immediate use case while preserving a clean path to the “multi‑game modding suite/container” vision.

---

## What OFNIR is (Phase 1)

Phase 1 is a **foundation release**, not an “all-in-one” editor. The focus is on building a reusable workspace that other domain tools can plug into over time.

Phase 1 aims to deliver:

- A desktop app shell with a project-centered workspace.
- A project model that knows about assets, relationships, and status.
- A file browser designed for Souls-style workflows (params, text, archives, etc.).
- Tool windows for editing, comparing, and analyzing data (dockable and floatable).
- Compare and diff workflows that actually respect how mods get made.
- Linked Analysis and validation surfaces that explain “what this change affects.”
- Basic CSV/param, FMG text, and archive packaging workflows.
- Safeguards for destructive actions, backup/export, and local-first storage.

If you’re looking for a drop-in replacement for every tool you already use, OFNIR will not be that in Phase 1—and that’s intentional.

---

## Roadmap at a glance

| Phase | Focus                                | Notes |
|-------|--------------------------------------|-------|
| Phase 1 | Foundation workspace                 | Shell, project model, file browser, tool windows, compare, Linked Analysis, validation, basic CSV/FMG/archive flows. |
| 1.5   | Workflow accelerators                 | Drag-and-drop for projects/files/compare/imports, small reopen and quality-of-life improvements layered on top of stable flows. |
| 2     | Domain integration and richer tooling | Deeper param/text maturity, script and map integration, stronger conflict resolution and dependency views, more advanced merge assistance. |
| 3+    | Advanced editors and visual tooling   | Animation, model, material, texture, audio, and scene-level tooling where it makes sense to build instead of just bridge. |

The short version: **make the workflow work first, then make it fast, then make it deep.**

---

## Design intent

OFNIR is meant to feel like “mission control for modding”: deliberate, dense, and legible rather than flashy. The UI direction emphasizes:

- Tactical clarity and stable layout anchors.
- A workspace-first model where tools open as **tool windows**, not endless modal dialogs.
- Clear separation between commentary, machine text, warnings, and editable values.
- Progressive disclosure of complexity rather than dumping everything on screen at once.

The product should be comfortable for long sessions and high-information work, especially around diffs and cross-file relationships.

---

## What this repo contains (right now)

At this stage the repo is mostly **design and planning** material. Expect to find:

- `docs/ofnir-phase-1.md` – detailed Phase 1 foundation spec (workspace, flows, tool window behavior, and scope).
- `design/` – higher-level design intent, UX principles, and roadmap notes.

Code will arrive once the foundation spec feels solid enough to build against.

If you are reading this very early, treat this project as an open notebook: issues and PRs that help clarify the spec and sharpen Phase 1 are welcome.

---

## License

This project is licensed under the **GNU General Public License (GPL)**. See the `LICENSE` file for details.

In plain language: you are free to use, study, share, and modify the software under the terms of the GPL, but derivative works must remain under a compatible copyleft license.

---

## Contributing

If you’re interested in helping:

- You can open issues to discuss:
  - workflow pain points in current Elden Ring modding,
  - ideas for compare, validation, and conflict resolution,
  - external tools that OFNIR should integrate with instead of replacing.
- You can propose changes to the Phase 1 spec in `docs/ofnir-phase-1.md` with PRs focused on:
  - clarifying behavior,
  - reducing scope creep,
  - or tightening acceptance criteria.

Implementation work will follow once the foundation is stable enough that writing code feels like executing a plan, not rewriting the plan every week.

---

## Status

Early design phase, no stable builds yet.

If you want to follow progress, watch this repo and keep an eye on updates to the Phase 1 spec and roadmap. As soon as there is something testable, it will be called out clearly in this README.


