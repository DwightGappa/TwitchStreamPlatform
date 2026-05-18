---
layout: default
title: "ADR‑004: Documentation and Editor Tooling"
permalink: /docs/decisions/adr-004/
---

<div class="phase-banner">
  <strong>Status:</strong> Accepted<br>
  <strong>Change Control:</strong> Required · Applies to All Phases
</div>

---

## Decision

<div class="panel">
  <div class="panel-header">
    Editor Selection
    <span class="status status-approved">Accepted</span>
  </div>

  Use Visual Studio Code as the primary editor for managing all project
  documentation, scripts, and execution artifacts.
</div>

Markdown files tracked in Git are the system of record. Editor choice does
not own or define the repository structure.

---

## Context

<div class="panel">
  <div class="panel-header">
    Operational Requirements
  </div>

  This project relies on documentation as a first class operational artifact,
  including:

  <ul>
    <li>Architecture decision records</li>
    <li>Build and validation checklists</li>
    <li>Execution tickets</li>
    <li>Status tracking and recovery notes</li>
  </ul>
</div>

Early project planning used Obsidian for Markdown editing and navigation. As
the project moved from conceptual planning into hands-on execution, several
constraints became apparent. Specifically:

- Editor controlled concepts (vault identity) were coupled to filesystem
- Renaming or restructuring introduced unintended folder changes
- Execution required tight integration between docs, scripts, and Git

The project focus shifted to deterministic execution and auditability. This
required an editor that treats the filesystem and Git as authoritative.

---

## Options Considered

<div class="panel">
  <div class="panel-header">
    Obsidian
    <span class="status status-superseded">Rejected</span>
  </div>

  <ul>
    <li>✅ Markdown first storage</li>
    <li>✅ Strong support for exploratory note taking</li>
    <li>❌ Tight coupling between editor state and filesystem</li>
    <li>❌ Limited integration with execution workflows</li>
  </ul>
</div>

---

<div class="panel">
  <div class="panel-header">
    Visual Studio Code
    <span class="status status-approved">Selected</span>
  </div>

  <ul>
    <li>✅ Treats the filesystem as authoritative</li>
    <li>✅ Native Git integration (diff, blame, history)</li>
    <li>✅ First class support for PowerShell and automation</li>
    <li>✅ Established proficiency for script development</li>
  </ul>
</div>

---

## Consequences

<div class="panel">
  <div class="panel-header">
    Expected Outcomes
  </div>

  <ul>
    <li>Clear separation between documentation and editing tools</li>
    <li>Stable and predictable repository structure</li>
    <li>Improved integration with execution tooling</li>
    <li>Alignment with infrastructure as code workflows</li>
  </ul>
</div>

### Neutral

<div class="panel">
  <ul>
    <li>Loss of editor specific features such as graph views</li>
    <li>These features were not required for execution or review</li>
  </ul>
</div>

### Guardrails

<div class="panel">
  <ul>
    <li>Markdown remains editor agnostic</li>
    <li>No documentation depends on editor specific metadata or formats</li>
    <li>Git remains the sole audit and history mechanism</li>
  </ul>
</div>

---

## Notes

<div class="panel">
  <div class="panel-header">
    Usage Notes
  </div>

  Obsidian may still be used informally for read only review, but it is not
  part of the project execution toolchain.
</div>

This decision reflects the transition from planning to execution and supports
long term reproducibility and reviewability.
