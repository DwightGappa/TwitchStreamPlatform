---
layout: default
title: Project Overview
permalink: /docs/context/project-overview/
---

<div class="panel panel-highlight">

**Case Study Theme:** Change‑Controlled Migration Playbook

This project is documented as a managed Windows‑to‑Linux migration,
emphasizing explicit decisions, risk tracking, phased execution, and
validation rather than undocumented iteration.

</div>

---

<div class="panel">

## Purpose

TwitchStreamPlatform is a deliberately documented, end‑to‑end project
focused on designing, testing, and migrating a dedicated Twitch
streaming environment from an initial Windows‑based proof‑of‑concept to
a stable Linux production system.

The primary goal is to enable reliable Twitch streaming while
minimizing impact on a separate gaming PC. The technical platform is
real, but the **primary deliverable is the process**: how the system is
planned, validated, migrated, and documented in a repeatable, reviewable
way.

This project serves as a professional case study demonstrating system
ownership, infrastructure planning, third‑party software validation, and
documentation‑driven execution.

</div>

---

<div class="panel">

## Background & Current State

Gameplay runs on a dedicated gaming computer. Based on prior research and
experience, a **separate streaming computer** is preferred to reduce
performance impact on gameplay.

The current proof‑of‑concept setup includes:

- OBS with **NDI** for game capture from the gaming computer
- A dedicated streaming / compositing computer
- A legacy Windows 10 streaming system using:

</div>
