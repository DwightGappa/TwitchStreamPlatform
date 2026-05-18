---
layout: default
title: "VM Validation Checklist – Linux Streaming Platform"
permalink: /docs/validation/vm-checklist/
---

<div class="panel panel-highlight">

## Purpose

This checklist defines the **virtual machine–specific validation process** for
the Linux streaming platform.

All build steps are executed according to the canonical build document:
[Build Checklist – Linux Streaming Platform](/docs/validation/build-checklist/)

This checklist focuses on **validation, isolation, rollback, and recovery** in
a VM context and does not redefine build logic.

</div>

---

<div class="panel">
  <div class="panel-header">
    Scope of VM Validation
  </div>

  VM validation is used to:
  <ul>
    <li>Safely test build steps before bare‑metal deployment</li>
    <li>Isolate failures caused by third‑party software</li>
    <li>Capture repeatable recovery points</li>
    <li>Validate automation readiness</li>
  </ul>

  This checklist assumes Hyper‑V is used as the host and VM snapshots
  are available.
</div>

---

## VM Baseline Preparation

<div class="panel">
  <ul>
    <li>[ ] VM created with appropriate CPU, memory, and storage</li>
    <li>[ ] Networking configured (NAT / bridged as required)</li>
    <li>[ ] VM boots successfully</li>
    <li>[ ] Initial snapshot taken (Pre‑Build Baseline)</li>
  </ul>

  ✅ VM Checkpoint: <strong>Pre‑Build Baseline</strong>
</div>

---

## Build Execution Validation

The following sections correspond to steps in the **Build Checklist**.
For each phase, the checklist is executed and then validated here.

---

<div class="panel">
  <div class="panel-header">
    1. Base OS & Updates Validation
  </div>

  **Reference:** Build Checklist §1–§2

  <ul>
    <li>[ ] Zorin OS install completed successfully</li>
    <li>[ ] System updates applied without errors</li>
    <li>[ ] Reboot succeeds</li>
    <li>[ ] Desktop usable</li>
  </ul>

  ✅ VM Checkpoint: <strong>Post‑OS‑Update Baseline</strong>
</div>

---

<div class="panel">
  <div class="panel-header">
    2. SSH & PowerShell Validation
  </div>

  **Reference:** Build Checklist §3–§4

  <ul>
    <li>[ ] SSH service active and accessible</li>
    <li>[ ] Root SSH login blocked</li>
    <li>[ ] PowerShell launches successfully</li>
    <li>[ ] PowerShell usable for non‑root automation</li>
  </ul>

  ✅ VM Checkpoint: <strong>Remote Access Enabled</strong>
</div>

---

<div class="panel">
  <div class="panel-header">
    3. Security Hardening Validation
  </div>

  **Reference:** Build Checklist §5

  <ul>
    <li>[ ] Hardened configuration applied</li>
    <li>[ ] SSH and PowerShell remain functional</li>
    <li>[ ] Desktop usability preserved</li>
  </ul>

  ✅ VM Checkpoint: <strong>Security Baseline Hardened</strong>
</div>

---

<div class="panel">
  <div class="panel-header">
    4. ZeroTier Validation
  </div>

  **Reference:** Build Checklist §6

  <ul>
    <li>[ ] ZeroTier installed and running</li>
    <li>[ ] Node joins designated network</li>
    <li>[ ] Connectivity verified</li>
    <li>[ ] Reboot persistence confirmed</li>
  </ul>

  ✅ VM Checkpoint: <strong>ZeroTier Functional</strong>
</div>

---

<div class="panel">
  <div class="panel-header">
    5. Synergy Validation
  </div>

  **Reference:** Build Checklist §7

  <ul>
    <li>[ ] Synergy installs and launches</li>
    <li>[ ] Input sharing functional over ZeroTier</li>
    <li>[ ] No unintended access observed</li>
  </ul>

  ✅ VM Checkpoint: <strong>Operator Control Functional</strong>
</div>

---

<div class="panel">
  <div class="panel-header">
    6. OBS Core Validation
  </div>

  **Reference:** Build Checklist §8.1

  <ul>
    <li>[ ] OBS launches reliably</li>
    <li>[ ] Scenes and profiles functional</li>
    <li>[ ] Recording/streaming works</li>
  </ul>

  ✅ VM Checkpoint: <strong>OBS Core Baseline</strong>
</div>

---

<div class="panel">
  <div class="panel-header">
    7. OBS WebSocket Validation
  </div>

  **Reference:** Build Checklist §8.2

  <ul>
    <li>[ ] WebSocket enabled with authentication</li>
    <li>[ ] Remote control functional over ZeroTier</li>
    <li>[ ] Stream and scene control validated</li>
  </ul>

  ✅ VM Checkpoint: <strong>OBS Remote Control Enabled</strong>
</div>

---

<div class="panel">
  <div class="panel-header">
    8. NDI Validation
  </div>

  **Reference:** Build Checklist §9

  <ul>
    <li>[ ] NDI source visible and stable</li>
    <li>[ ] Gaming system video received</li>
  </ul>

  ✅ VM Checkpoint: <strong>NDI Functional</strong>
</div>

---

<div class="panel">
  <div class="panel-header">
    9. VBAN Audio Validation
  </div>

  **Reference:** Build Checklist §10

  <ul>
    <li>[ ] VBAN stream received</li>
    <li>[ ] VBAN selectable in OBS</li>
    <li>[ ] Audio stable and synced</li>
  </ul>

  ✅ VM Checkpoint: <strong>VBAN Audio Functional</strong>
</div>

---

<div class="panel">
  <div class="panel-header">
    10. whisper.cpp Validation (Optional / Advanced)
  </div>

  **Reference:** Build Checklist §11

  <ul>
    <li>[ ] whisper.cpp builds successfully</li>
    <li>[ ] Real‑time transcription operates</li>
    <li>[ ] Integration does not destabilize system</li>
  </ul>

  ✅ VM Checkpoint: <strong>Whisper Functional</strong>
</div>
