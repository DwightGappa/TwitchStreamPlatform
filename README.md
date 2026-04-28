# TwitchStreamPlatform

![Status: Work in Progress](https://img.shields.io/badge/status-work%20in%20progress-yellow)

## Overview

**TwitchStreamPlatform is a deliberately documented, end-to-end project demonstrating the design, planning, and execution of a Linux-based live streaming platform.**

The technical implementation is real, but the **primary deliverable is the process itself**—how work is scoped, planned, executed, tracked, and documented. This repository serves as a **systems and project management case study**, not simply a codebase or how-to guide.

The focus is on:

- infrastructure planning and architecture
- disciplined execution and traceability
- automation and repeatability
- documentation as a first-class output

This project is intended to be reviewed holistically, from initial context through final synthesis, as a single coherent body of work.

## Professional Context

This project is intentionally framed to demonstrate professional growth from an **IT Support background into system ownership and infrastructure-focused work**.

Rather than showcasing isolated technical skills, the repository emphasizes:

- systems thinking over task execution
- decision-making under constraints
- operational discipline
- end-to-end project accountability

The structure, tooling, and documentation style reflect real-world enterprise environments where clarity, auditability, and communication are as important as implementation.

A non-technical outreach purpose exists for the platform, but it is acknowledged only at a high level; the **technical and professional focus remains squarely on systems and project execution**.

## Documentation

📄 **Live Documentation (Work in Progress):**  
<https://dwightgappa.github.io/TwitchStreamPlatform/>

The repository remains the system of record; the documentation site provides
a reader‑friendly view of the evolving case study.

## Repository

**Source Repository:**  
<https://github.com/DwightGappa/TwitchStreamPlatform>

This repository contains the complete project record, including:

- documentation and context
- architecture and tooling decisions
- automation scripts
- execution tracking
- planning artifacts
- draft and final case study materials

Git is used as an **audit history**, not as a deployment mechanism.  
All artifacts required to understand or review the project live within this repository.

✅ _LinkedIn Featured–ready summary:_  
GitHub repository documenting a Linux-based streaming platform as a project management and systems case study, with documentation and process treated as core deliverables.

## Project Structure

The repository is organized to clearly separate **human-readable documentation**, **machine-readable data**, and **supporting artifacts**.

```text
TwitchStreamPlatform/
├─ docs/                   # Canonical project documentation (Markdown, Git tracked)
│  ├─ 00_CONTEXT/          # Project overview, goals, scope
│  ├─ 01_DECISIONS/        # Architecture & tooling decisions
│  ├─ 02_TICKETS/          # Human-readable work summaries
│  ├─ 03_STATUS/           # Current status and timeline
│  ├─ 04_CASE_STUDY/       # Draft and final case study
│  └─ 99_ARCHIVE/          # Historical or deprecated notes
│
├─ scripts/               # PowerShell automation
├─ tickets/               # Machine-readable execution data
├─ diagrams/              # Architecture and flow diagrams
│  ├─ source/             # Visio (.vsdx)
│  └─ export/             # Rendered images (.png, .svg)
│
├─ project/               # Microsoft Project planning files (.mpp)
├─ README.md
└─ .gitignore
```

A visual representation of the structure is included for quick orientation:  
diagrams/export/TwitchStreamPlatform_Folder_Structure.png

## Design Principles

This repository is intentionally structured to mirror **real-world project and infrastructure management practices**, prioritizing clarity and reviewability over minimalism.

### Documentation as a Deliverable

Documentation is treated as a **first-class output**, not a retrospective activity.

### Clear Separation of Concerns

Human-readable documentation, machine-readable execution data, automation scripts, and planning artifacts are intentionally kept separate.

### Single Source of Truth

The repository root represents the **project boundary**.

### Tooling Mirrors Enterprise Environments

Tools were selected to reflect common enterprise workflows rather than hobby-specific stacks.

### Phase-Agnostic Structure

Folder and file names avoid phase-specific language so the project can evolve naturally.

### Reviewability Over Cleverness

Structure, naming, and documentation favor clarity and intent over novelty.

## How to Review This Repository

This repository is intended to be reviewed as a **project management and systems case study**, not just a code repository.

Review order:

1. docs/00_CONTEXT
2. docs/01_DECISIONS
3. tickets/ and docs/02_TICKETS
4. docs/03_STATUS
5. diagrams/ and project/
6. docs/04_CASE_STUDY

### Tooling

- PowerShell
- Git
- Visual Studio Code
- Microsoft Visio
- Microsoft Project

## Status

Project structure and documentation framework are established. Execution tracking is ready to begin.

## License / Notes

No license has been applied at this time. Licensing will be evaluated if the project is published or reused externally.
