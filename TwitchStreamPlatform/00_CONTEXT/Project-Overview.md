# Project Overview

## Purpose

TwitchStreamPlatform is a deliberately documented, end‑to‑end project focused on
designing, testing, and migrating a dedicated Twitch streaming environment from an
initial Windows‑based proof‑of‑concept to a stable Linux production system.

The primary goal is to enable reliable Twitch streaming while minimizing impact on a
separate gaming PC. The technical platform is real, but the **primary deliverable is the
process**: how the system is planned, validated, migrated, and documented in a
repeatable, reviewable way.

This project serves as a professional case study demonstrating system ownership,
infrastructure planning, third‑party software validation, and documentation‑driven
execution.

---

## Background & Current State

Gameplay runs on a dedicated gaming computer. Based on prior research and
experience, a **separate streaming computer** is preferred to reduce performance impact
on gameplay.

The current proof‑of‑concept setup includes:
- OBS with **NDI** for game capture from the gaming computer
- A dedicated streaming/compositing computer
- A legacy Windows 10 streaming system using:
  - NDI video
  - VoiceMeeter / VBAN audio
  - A built‑in web camera

This setup functions today but relies on:
- Aging hardware
- Windows 10, which will reach end of support in October 2026

The platform therefore needs to be **replaced or migrated** to a supported operating
system.

---

## Project Objective

The objective of this project is to:

- Design and validate a **Linux‑based streaming environment**
- Migrate from Windows 10 to Linux **without breaking core streaming workflows**
- Document the process from:
  - Test virtual machine
  - To validated configuration
  - To bare‑metal production deployment

Special emphasis is placed on **third‑party software compatibility**, as prior Linux
testing has shown that streaming‑related tools (NDI, audio routing software, capture
utilities) can break easily across updates or environments.

---

## Selected Platform

The target operating system for this project is **Zorin OS 18**, based on **Ubuntu LTS
24.04**.

Zorin OS was selected due to:
- Long‑term support stability
- Ubuntu ecosystem compatibility
- A Windows‑familiar user experience
- Built‑in features to ease transition, including OneDrive integration

This choice is documented and revisited throughout the project as part of decision
tracking.

---

## Scope

### In Scope
- Linux operating system selection and validation
- Virtual machine testing of the streaming environment
- Migration path from VM to bare‑metal installation
- OBS Studio configuration and validation
- NDI video workflow testing
- Audio routing evaluation (e.g., VBAN or Linux‑native alternatives)
- Documentation of failures, breakage points, and mitigations
- Decision records and execution tracking
- Final case study synthesis

### Out of Scope
- Game performance benchmarking
- Twitch channel growth, branding, or monetization
- Viewer analytics or engagement optimization
- Game capture troubleshooting on the gaming computer itself

---

## Success Criteria

This project is considered successful when:

- A Linux‑based streaming environment is validated for daily use
- Core workflows (video, audio, compositing) function reliably
- Migration from test VM to bare metal is documented and repeatable
- Third‑party software constraints and workarounds are clearly recorded
- The repository tells a complete, auditable story from concept to deployment
- A final case study accurately reflects decisions, execution, and lessons learned

---

## Intended Audience

- Systems and infrastructure reviewers
- Technical hiring managers
- IT and operations professionals
- Peers evaluating documentation and platform migration discipline

This documentation assumes general technical familiarity but does not assume prior
knowledge of the project.

---

## How to Use This Repository

This repository is structured to be reviewed sequentially:

1. **Context** – Why the project exists and what problem it solves
2. **Decisions** – Key platform and tooling choices with rationale
3. **Tickets** – Human‑readable execution tracking
4. **Status** – Current project state and timeline
5. **Diagrams & Planning** – Architecture and migration artifacts
6. **Case Study** – Final synthesis and reflection

---

## Operating Rule

OneNote is for capture.  
Obsidian is the system of record.  
Git is the audit trail.  
Published documents are derived artifacts.