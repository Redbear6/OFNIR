### Game‑agnostic foundation

Even though Phase 1 targets Elden Ring first, the core should stay game‑agnostic wherever practical:

- The project model (projects, assets, relationships, conflicts, validation, snapshots) should not hard‑code Elden Ring assumptions when a generic concept will do.
- Game‑specific behavior should live in containers or modules layered on top of the shared core (for example, an “Elden Ring container” that plugs in formats, validators, and tool windows).
- Cross‑game support later (e.g. Elden Ring + Crimson Desert in one workspace) should be a matter of loading multiple containers into the same core, not rewriting the core for each game.

This keeps Phase 1 honest to its immediate use case while preserving a clean path to the “multi‑game modding suite/container” vision.