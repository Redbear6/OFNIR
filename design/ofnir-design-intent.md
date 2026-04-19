# OFNIR Design Intent and Product Scope

## Overview

OFNIR is a tactical Elden Ring modding workspace intended to become a project-centered source of truth for understanding, comparing, validating, and managing interconnected assets across multiple file domains.

The immediate goal is not to replace every specialized utility in a single release. The near-term goal is to establish a shared application shell, workspace model, project model, analysis layer, and comparison workflow first, then expand through interlocking toolsets over time.

That phased approach fits the current modding reality, where archive handling, maps, params, text, event scripts, animation work, and model work are often split across separate tools and pipelines.

## Problem Statement

Current Elden Ring modding workflows lack a unified source of truth for understanding how edits in one file domain affect related assets in another domain.

Community tools are capable but fragmented. Some tools are strong at map or param work, others at archive packaging, others at event scripts, and many advanced domains still require tool-hopping or external applications.

As a result, modders often cannot easily answer questions such as how a change in one asset affects linked params, text, references, materials, validation state, or downstream packaging. OFNIR should address that gap by organizing work around projects, relationships, comparisons, conflict detection, and cross-file visibility rather than around isolated file editors alone.

## Design Intent

The design intent is to create a tactical, high-legibility workspace that feels deliberate, modular, and operational rather than decorative.

The interface should communicate confidence and technical clarity through hierarchy, zoning, density control, and consistent interaction rules instead of relying on terminal nostalgia or excessive visual noise.

The desired emotional tone is mission control for modding: focused, serious, information-rich, and practical. The tactical look should support usability, not overpower it.

## Core product framing

OFNIR should be framed as a workspace and suite foundation, not as a single monolithic editor.

The core value of the product is not merely opening files. The core value is helping modders understand relationships, compare alternatives, validate assumptions, detect conflicts, and keep project knowledge organized in one place.

The first release should therefore emphasize shared infrastructure and working logic over breadth of domain-specific editing.

## UX principles

### Tactical clarity

The workspace should prioritize fast scanning, explicit hierarchy, stable anchors, and low-friction orientation.

The user should not need to hunt for the current task state. The interface should make it clear what they are working on, what tool window is active, what comparison or analysis context is in effect, and what actions are available when that distinction matters.

### Source of truth

Every project should have a central structure that records file relationships, status, conflicts, recent changes, snapshots, and relevant metadata.

The UI should make dependency and impact relationships visible so that edits are understood in context rather than in isolation.

### Modular growth

The product should be built as a suite-capable foundation with interlocking toolsets rather than as a monolith.

This allows the common frame, workspace logic, project model, comparison systems, validation systems, and analysis tools to mature first while domain-specific editors are added in phases.

### Human-readable technicality

The interface should remain technically literate without collapsing into all-monospace aesthetics.

Technical density is welcome where useful, but hierarchy, readability, spacing, and typography should keep the product approachable during long sessions.

## Visual direction

The default visual system should use a dark tactical palette with restrained accents, clear border hierarchy, matte surfaces, and readable text.

Theme presets can exist for alternate preferences, including more retro-terminal styles, but the default should prioritize readability and eye comfort over novelty.

The visual system should support long-duration use, dense comparison work, and fast scanning.

## Workspace model

OFNIR is a workspace-first application.

The app should establish or restore project context at startup so the user does not need repeated project reminders during routine work. Context indicators should appear when ambiguity exists, not as permanent noise.

The workspace should support multiple first-class tool windows for editing, comparison, validation, analysis, references, and related project operations.

These tool windows can be docked, floated, snapped, grouped, minimized, hidden, or arranged side by side depending on task needs. Layout position does not define importance.

Analysis, validation, references, compare, and conflict handling are not subordinate side features. They are core working toolsets within the OFNIR suite.

## Terminology

To keep the language consistent, Phase 1 should prefer the following terms:

- Workspace: the overall active work area of the app.
- Tool window: a movable, dockable, minimizable, or floating working surface for a specific task.
- View: a specific representation such as compare view, editor view, validation view, or analysis view.
- Dialog: a blocking prompt used only when a required choice or confirmation is needed.

The earlier “pane” terminology can be retained as historical shorthand in old notes, but current design language should prefer “tool window” and “workspace.”

## Interaction model

The interaction model should be workspace-first and modeless by default.

Tools should open into the workspace as tool windows wherever possible instead of routing routine work through blocking modal chains.

Dialogs should be reserved for missing context, destructive confirmations, or narrow setup decisions rather than ordinary navigation.

The interaction model should support:

- Docking and floating tool windows.
- Snapping and optional grouping or locking behavior.
- Minimizing, hiding, and reopening tool windows.
- Pull-down menus and context menus for projects, files, tools, and field-specific actions.
- Persistent filters and active-context indicators where they actually aid orientation.
- Compare and diff-oriented workflows that can remain visible while the user continues working.

## Tool window behavior

Tool windows should behave as first-class working tools, not as disposable sidebars.

When docked, a tool window participates in the workspace layout and does not maintain independent always-front behavior.

When floating, a tool window should remain above the OFNIR workspace while the app is active, but it should not become an operating-system-wide always-on-top window.

The focused floating tool window should rise above other floating tool windows, and docking a tool window should return it to layout-managed stacking.

## Product foundation

The first build should focus on the foundation rather than complete editor parity for all target file types.

The initial milestone should establish a reusable application shell and project model that every future domain editor or game container can plug into.

Foundation deliverables include:

- Common application shell and workspace model.
- Theme and preset framework.
- Project create, open, restore, and file browser behavior.
- Pull-down and context menu structure.
- Tool window system.
- Linked Analysis toolset.
- Comparison and diff framework.
- Conflict detection and resolution surfaces.
- Validation and warning systems.
- Local-first storage and optional future cloud or AI integration points.
- Export, backup, and destructive-action safeguards.

## Core platform functions

The core platform functions are more strategically important than any single domain editor in isolation.

These include:

- Project management.
- File browsing and navigation.
- Diff and compare.
- Conflict detection.
- Linked Analysis.
- Validation.
- Audit trail and traceability.
- Import and export.
- Snapshot and restore behavior.

## Phase 1 functional scope

Phase 1 should build the common shell, workspace logic, project model, file browser, Linked Analysis, compare and diff framework, validation surface, and basic early-value workflows.

The first implementation should focus on high-value shared capabilities before attempting deep parity across every format or replacing mature external tools.

### Early-phase domains

Phase 1 should concentrate on a limited set of early-value areas such as:

- CSV, params, rows, and fields.
- FMG and FMG.DCX text resources.
- Archive-oriented workflows such as DCX, BND, and TPF handling.
- JSON, Python, and general project notes where they serve as workflow glue.
- Reusable diff and validation layers.

## External tool strategy

OFNIR should not try to immediately displace every mature specialist tool.

A more durable strategy is to let OFNIR become the coordination layer first: the place where projects are organized, differences are understood, dependencies are surfaced, and decisions are made.

Specialized editing can then expand selectively where the integrated experience offers clear value beyond current tool fragmentation. External tool launch hooks are compatible with this approach.

## Game-agnostic foundation

Although Phase 1 is deliberately exercised against Elden Ring first, the foundation should remain game-agnostic wherever practical.

The core concepts of projects, assets, relationships, conflicts, comparisons, validation, snapshots, and auditability should not be hard-coded to a single title when a general concept will do.

Game-specific behavior should live in containers, modules, or toolsets layered on top of the shared core.

This supports the long-term vision of OFNIR as a multi-game modding suite/container in which multiple game contexts can be loaded under a shared source-of-truth framework.

## Long-term vision

Roadmap Mile 100 is for OFNIR to evolve into a multi-game modding suite/container that can host multiple game packs or containers at once under a common source-of-truth core.

In that vision, a user could load an Elden Ring container alongside a Crimson Desert container and work across both in one workspace using the same project, comparison, validation, and relationship logic instead of juggling unrelated tools and mental models.

Phase 1 does not attempt to deliver that breadth immediately, but the architecture and language should avoid painting the product into a single-game corner.

## Phased delivery

### Phase 1: Foundation

Build the common shell, workspace and tool window system, theme framework, project model, file browser, Linked Analysis, compare and diff framework, validation surface, and basic CSV, FMG, and archive workflows.

### Phase 1.5: Workflow acceleration

Add drag-and-drop and similar direct-manipulation accelerators after the underlying open, import, and compare flows are already stable.

### Phase 2: Domain integration

Deepen param and text maturity, add script and event integration, map inspection and compare support, richer conflict resolution, and stronger dependency views.

### Phase 3: Advanced editors

Expand into deeper animation, model, material, texture, Havok, audio, and richer visual tooling where the integrated approach clearly adds value.

## Risks and constraints

The biggest risk is over-scoping the first release by treating the entire ecosystem as a single immediate deliverable.

The second risk is trying to replace mature domain-specific tools before the foundation layer is proven.

Another risk is allowing old layout terminology to drag the product back toward a main-editor-plus-sidebars mental model when the actual design intent is a workspace of first-class tool windows.

## Working conclusion

OFNIR is strongest when framed not as one editor for every file type immediately, but as a tactical project workspace and suite foundation that gives modders a stable source of truth across fragmented tools and interconnected assets.

The build order should therefore prioritize the shell, workspace logic, project model, compare and diff workflows, analysis, validation, conflict handling, and early high-value domains before attempting total editor coverage across the full format list.