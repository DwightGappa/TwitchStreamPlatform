# ADR-004 Documentation and Editor Tooling

## Status

Accepted

---

## Decision

Use Visual Studio Code as the primary editor for managing all project documentation, scripts, and execution artifacts.

Markdown files tracked in Git are the system of record. Editor choice does not own or define the repository structure.

---

## Context

This project relies on documentation as a first class operational artifact, including:

- Architecture decision records
- Build and validation checklists
- Execution tickets
- Status tracking and recovery notes

Early project planning used Obsidian for Markdown editing and navigation. As the project moved from conceptual planning into hands on execution, several constraints became apparent.

Specifically:

- Editor controlled concepts such as vault identity were coupled to filesystem structure
- Renaming or restructuring documentation introduced unintended folder changes
- Execution phase work required tight integration between documentation, scripts, logs, and Git history

The project focus shifted from exploratory note taking to deterministic execution, auditability, and reproducibility. This required an editor that treats the filesystem and Git as authoritative and immutable unless explicitly changed.

---

## Options Considered

### Obsidian

- Markdown first storage
- Strong support for exploratory note taking
- Backlinks and graph based navigation

Limitations identified during execution readiness:

- Tight coupling between editor state and filesystem structure
- Implicit ownership of the documentation root
- Limited integration with scripting and execution workflows

Outcome:
Obsidian was deprioritized once execution began due to filesystem determinism and tooling boundary concerns.

---

### Visual Studio Code

- Treats the filesystem as authoritative
- Native Git integration for diff, blame, and commit history
- First class support for PowerShell and automation scripts
- Single workspace for documentation, scripts, and logs
- Established proficiency and long term use for PowerShell development

Outcome:
Visual Studio Code was selected as the primary editor for all project artifacts.

---

## Consequences

### Positive

- Clear separation between documentation content and editing tools
- Stable and predictable repository structure
- Improved integration between documentation and execution tooling
- Strong alignment with infrastructure as code workflows

### Neutral

- Loss of editor specific features such as graph views
- These features were not required for execution or review

### Guardrails

- Markdown remains editor agnostic
- No documentation depends on editor specific metadata or formats
- Git remains the sole audit and history mechanism

---

## Notes

Obsidian may still be used informally for read only review or ad hoc exploration, but it is not part of the project execution toolchain.

This decision reflects the transition from planning to execution and supports long term reproducibility and reviewability.
