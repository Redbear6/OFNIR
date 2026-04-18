OFNIR 

OFNIR Design Intent and Product Scope

1. Overview

OFNIR is envisioned as a tactical, multi-pane Elden Ring modding workspace inspired by the information-rich, editor-driven feel of Arma’s Eden Editor, but adapted to the realities of Souls-format modding and current community tooling. Its purpose is to become a project-centered source of truth that helps modders understand, compare, validate, and manage interconnected assets across multiple file domains instead of relying on fragmented point tools and ad hoc notes.

The immediate product goal is not to replace every existing specialized utility in a single release. The better strategic objective is to build a shared frame, pane system, project model, analysis layer, and comparison workflow first, then expand through interlocking mini-apps over time. That phased approach fits the current tool ecosystem, where archive handling, maps, params, text, event scripts, animation work, and model work are often split across separate community tools and pipelines.

Problem Statement
Current Elden Ring modding workflows lack a unified “source of truth” for understanding how edits in one file domain affect related assets in another domain.
 Community tools are capable but fragmented: Smithbox supports major editing workflows such as maps, params, text, and model-oriented tasks; WitchyBND and related archive workflows are used for unpacking and repacking; DarkScript3 focuses on event scripting productivity; and many advanced domains still require tool-hopping or external applications.

As a result, modders often cannot easily answer questions such as how a change in an event or sequence affects animation timing, linked params, text, materials, or associated assets in a holistic view.
 OFNIR should address that gap by organizing work around projects, relationships, comparisons, conflict detection, and cross-file visibility rather than around isolated file editors alone.

2. Design Intent
The design intent is to create a tactical, high-legibility workspace that feels deliberate, modular, and operational rather than decorative.
 The interface should communicate confidence and technical clarity through hierarchy, panel zoning, density control, and consistent interaction rules instead of relying on terminal nostalgia or excessive visual noise.

The desired emotional tone is “mission control for modding”: focused, serious, information-rich, and practical. The tactical look should support usability, not overpower it, which means careful contrast, persistent navigation, progressive disclosure, and clear separation between commentary, machine text, warnings, and editable values.

3. UX Principles
Tactical clarity
The workspace should prioritize fast scanning, explicit hierarchy, and stable layout anchors. Users should be able to identify what project is active, what file is selected, what pane is authoritative, and what actions are currently available without hunting across the interface.

4. Source of truth
Every project should have a central structure that records file relationships, status, conflicts, and recent changes. The UI should make dependency and impact relationships visible so that edits are understood in context rather than in isolation.

5. Modular growth
The product should be built as a suite-capable foundation with interlocking mini-apps rather than as a monolith. This allows the common frame, pane logic, project model, and analysis tools to mature first while domain-specific editors are added in phases.

6. Human-readable technicality
The interface should remain technically literate without collapsing into all-monospace aesthetics. The current typography rule supports that: Geist Sans for the app shell, Input Sans only for Linked Analysis, Input Mono for technical fragments within that analysis context, and Geist Mono for general code or machine-oriented panels.

7. Visual and Interaction Direction
The default visual system should use a dark tactical palette with restrained accents, clear border hierarchy, matte surfaces, and readable text. Theme presets can be provided for alternate preferences, including retro-terminal styles, but the default should prioritize readability and eye comfort over novelty.

The core layout should be multi-pane and project-oriented, with a persistent navigation rail, a main work surface, and one or more secondary panes for linked analysis, validation, references, or diff views. Panes should support move, hide, minimize, and snap behavior, with optional locking between panes so users can preserve task-specific arrangements while manipulating the broader workspace.

The interaction model should support:

Magnetic pane snapping and optional pane locking.

Collapsible and minimizable panes.

Pull-down menus and context menus for projects, files, tools, and field-specific actions.

Confirmed destructive actions, with optional user-controlled suppression for repeat confirmations.

Persistent filter chips and active-context indicators.

Split-pane comparison and diff-oriented workflows.


8. Product Foundation

The first build should focus on the foundation rather than complete editor parity for all target file types.

That means the initial milestone should establish a reusable application shell and project model that every future domain editor can plug into.

Foundation deliverables
Common frame and pane system.

Theme and preset framework.

Project and file browser.

Pull-down and context menu structure.

Linked Analysis pane.

Comparison and diff framework.

Conflict detection and resolution surface.

Validation and warning system.

Local-first storage and optional cloud/AI integration points.

Export, backup, and destructive-action safeguards.


9. Functional Scope
The long-term ambition is a multi-project workspace that can unpack, inspect, compare, edit, validate, and recombine many Elden Ring asset types across local or cloud-backed workflows, with or without AI assistance depending on user choice.
 However, the functional scope should be tiered so that the most valuable shared capabilities are built before the hardest domain-specific editors.


10. Core platform functions
Function	Purpose
Project management	Organize assets, metadata, status, and file relationships per project.
File browser	Navigate file domains, categories, and linked assets consistently.
Diff and compare	Compare one-to-one and one-to-many files, rows, or fields.
Conflict detection	Surface incompatible edits, duplicate IDs, and broken references.
Linked Analysis	Explain cross-file implications and relationships in context.
Validation	Warn about broken paths, references, merge issues, and risky edits.
Audit trail	Record what changed, when, and why.
Import/export	Save, package, archive, and restore project states.
These shared functions are the real foundation of the product and are more strategically important than any single domain editor in isolation.

11. File-Domain Roadmap
The file-domain roadmap should distinguish between domains that are realistic in early phases and those that should initially be bridged to external community tools.

a. Early-phase domains
Domain	Suggested scope	Notes
CSV / params / rows / fields	Structured editing, row highlighting, field compare, bulk edit, conflict resolution	Strong early value because params are central to many workflows.
FMG / FMG.DCX	View, edit, compare, search, and merge text resources	Text workflows are comparatively approachable and high-impact.
DCX / BND / TPF handling	Unpack, repack, dependency awareness, archive compare	DCX is a wrapper/compression format, so the product should emphasize packaging workflows rather than “editing DCX” directly.
JSON / Python / general notes	Internal editing, note-taking, helper scripts, metadata	Useful as glue between specialized systems.
Diff / validation layers	Reusable across all domains	High leverage feature set.

b. Mid-phase domains
Domain	Suggested scope	Notes
EMEVD / script workflows	Script compare, edit support, external-tool bridge, dependency context	DarkScript3 remains an important ecosystem reference.
MSB / map workflows	Inspection, compare, relationship mapping, bridge into map editing workflows	Smithbox already provides significant map support.
TAE workflows	Side-by-side compare, event sequence inspection, linked references	Animation workflows are valuable but more specialized.
FLVER / model pipelines	View relationships, compare assets, bridge to Blender-centered editing	FLVER remains the core model format in Souls workflows.
TPF / DDS texture workflows	Viewer, unpack/repack, compare, replace, export	Strong utility value in project context.

c. Late-phase or bridge-first domains
Domain	Suggested scope	Notes
HKS / HKX	Inspect, relate, bridge, partial editing where practical	Full authoring may be difficult and should be phased carefully.
Audio banks and FMOD assets	Inspect, compare, package, bridge	Specialized tooling and format complexity suggest later-phase work.
Full 3D visual editor	Shared scene view, dependency graph, preview, external bridge first	Ambitious and best treated as a long-term subsystem.
Material systems (.mtd, .matbin)	Inspect references, compare, map to FLVER/material relationships	Particularly relevant for Elden Ring’s material workflows.
Recommended Functional Additions

The following additions would make the product substantially stronger:

- Dependency graph view for cross-file references.
- Project snapshotting before destructive edits.
- Merge assistant for conflicting mods.
- Rule-based validation checks for duplicate IDs, invalid paths, and broken references.
- External tool launch hooks for workflows better handled in Smithbox, WitchyBND, Blender, or DarkScript3.
- AI assistance as an optional advisor, not a forced workflow.
- Bulk edit queues with preview and rollback.
- “Why did this change?” traceability tied to an audit log.
- Search that spans projects, files, rows, fields, and linked references.

These additions reinforce the core source-of-truth value proposition rather than pulling focus toward isolated novelty features.

Phased Delivery
Phase 1: Foundation
Build the common frame, pane system, theme system, project model, file browser, Linked Analysis, diff/compare framework, validation surface, and basic CSV/FMG/archive workflows.

Phase 2: Domain integration
Add param and text maturity, script/event integration, map inspection and compare support, richer conflict resolution, and stronger dependency views.

Phase 3: Advanced editors
Expand into deeper animation, model, material, texture, Havok, and audio domains, with increasing visual tooling and tighter cross-domain analysis.

---END---
