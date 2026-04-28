# ADR-001: Documentation Model

## Status

Accepted

## Context

This project is being intentionally documented as a **work in progress** to support
reviewability, learning, and reproducibility. The project involves transitioning a
functioning system from Windows to Linux, with validation performed first in a virtual
environment and later recreated on physical hardware.

Because the primary deliverable of this project is the **process**, documentation must
capture not only the technical outcome, but also:

- context and intent,
- decisions and rationale,
- current state and progress,
- and lessons learned as the work unfolds.

The documentation model must support incremental updates, be human‑readable,
version‑controlled, and suitable for both technical and non‑technical review.

## Decision

The project will use a **Markdown‑first, Git‑backed documentation model** with clear
separation between documentation artifacts and execution artifacts.

Specifically:

- Markdown (`.md`) files are the system of record for all project documentation
- Documentation lives inside the project repository and is version‑controlled with Git
- Documentation is written **as work is performed**, not retroactively
- Selected documentation is published via GitHub Pages to support external review
- The repository remains the authoritative system of record
- Git commit history serves as an audit trail of progress and decision‑making

Microsoft 365 Copilot may be used as a **guided support tool** to improve clarity and
structure of documentation, but all planning, decisions, and technical work remain
