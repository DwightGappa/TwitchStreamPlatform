---
layout: default
title: "Build Checklist – Linux Streaming Platform (Zorin OS 18)"
permalink: /docs/validation/build-checklist/
---

<div class="panel panel-highlight">

## Purpose

This checklist defines the **canonical build process** for the Linux-based
streaming platform. It is intentionally environment-agnostic and can be
applied to:

<ul>
  <li>Virtual machine builds</li>
  <li>Bare-metal deployments</li>
  <li>System rebuilds</li>
  <li>Automated provisioning (scripts/playbooks)</li>
</ul>

All validation activities should reference this checklist.

</div>

---

<div class="panel">
  <div class="panel-header">
    Build Scope
  </div>

  This checklist focuses on **correctness, stability, security, and
  reproducibility**. Performance tuning is explicitly out of scope until
  after bare-metal deployment.
</div>

---

<div class="panel">
  <div class="panel-header">
    1. Base Operating System Installation
  </div>

  <ul>
    <li>[ ] Zorin OS 18 installs successfully</li>
    <li>[ ] System boots reliably</li>
    <li>[ ] Desktop environment loads correctly</li>
    <li>[ ] Network connectivity functions</li>
    <li>[ ] Disk layout finalized</li>
  </ul>

  ✅ Outcome: Base OS is usable.
</div>

---

<div class="panel">
  <div class="panel-header">
    2. System Updates & Core Configuration
  </div>

  <ul>
    <li>[ ] All system updates installed</li>
    <li>[ ] Reboot completes successfully</li>
    <li>[ ] Desktop remains functional</li>
    <li>[ ] Automatic updates configured as desired</li>
  </ul>

  ✅ Outcome: System is current and stable.
</div>

---

<div class="panel">
  <div class="panel-header">
    3. Remote Access – SSH Enablement (Required)
  </div>

  SSH is enabled to support remote administration and automation.

  <ul>
    <li>[ ] OpenSSH server installed</li>
    <li>[ ] SSH enabled at boot</li>
    <li>[ ] SSH access verified</li>
    <li>[ ] Root SSH login disabled</li>
    <li>[ ] Firewall restricted to trusted access</li>
  </ul>

  ✅ Outcome: Secure remote shell access available.
</div>

---

<div class="panel">
  <div class="panel-header">
    4. PowerShell Installation (Required)
  </div>

  PowerShell is installed to support cross-platform automation and scripting.

  <ul>
    <li>[ ] PowerShell installs successfully</li>
    <li>[ ] PowerShell launches without errors</li>
    <li>[ ] Installed version documented</li>
    <li>[ ] Available to non-root users</li>
  </ul>

  ✅ Outcome: PowerShell available for automation.
</div>

---

<div class="panel">
  <div class="panel-header">
    🔐 5. Operating System Security Hardening
  </div>

  <ul>
    <li>[ ] Non-root user enforced</li>
    <li>[ ] Password policies applied</li>
    <li>[ ] Screen lock enabled</li>
    <li>[ ] Time sync active</li>
    <li>[ ] Firewall default-deny posture</li>
    <li>[ ] Unused services disabled</li>
  </ul>

  ✅ Outcome: Reasonable security baseline applied.
</div>

---

<div class="panel">
  <div class="panel-header">
    🌐 6. ZeroTier Point-to-Point VPN
  </div>

  <ul>
    <li>[ ] ZeroTier installed and running</li>
    <li>[ ] Enabled at boot</li>
    <li>[ ] Node joined to network</li>
    <li>[ ] Node authorized</li>
    <li>[ ] Stable connectivity verified</li>
  </ul>

  ✅ Outcome: Secure private connectivity available.
</div>

---

<div class="panel">
  <div class="panel-header">
    ⌨️ 7. Synergy 3 – Keyboard / Mouse Sharing
  </div>

  <ul>
    <li>[ ] Synergy installed and launches</li>
    <li>[ ] Host/client roles configured</li>
    <li>[ ] Input transitions smooth</li>
    <li>[ ] Operates over ZeroTier only</li>
  </ul>

  ✅ Outcome: KVM-style input control operational.
</div>

---

<div class="panel">
  <div class="panel-header">
    🎛️ 8. OBS Studio (Critical Application)
  </div>

### 8.1 Core OBS Functionality

  <ul>
    <li>[ ] OBS installs successfully</li>
    <li>[ ] OBS launches reliably</li>
    <li>[ ] Scenes and sources created</li>
    <li>[ ] Recording/streaming works</li>
    <li>[ ] Configuration persists across reboot</li>
  </ul>

### 8.2 OBS WebSocket / Remote Control (Critical)

  <ul>
    <li>[ ] WebSocket enabled</li>
    <li>[ ] Authentication enabled</li>
    <li>[ ] Custom credentials set</li>
    <li>[ ] Reachable over ZeroTier</li>
    <li>[ ] Scene & stream control works remotely</li>
  </ul>

  ✅ Outcome: OBS and Remote Control operational.
</div>

---

<div class="panel">
  <div class="panel-header">
    9. NDI Video Input
  </div>

  <ul>
    <li>[ ] NDI installed</li>
    <li>[ ] NDI source visible in OBS</li>
    <li>[ ] Video received from gaming system</li>
    <li>[ ] Video stable</li>
  </ul>

  ✅ Outcome: NDI video operational.
</div>

---

<div class="panel">
  <div class="panel-header">
    🎧 10. Audio Routing – VBAN
  </div>

  <ul>
    <li>[ ] VBAN receiver installed</li>
    <li>[ ] Stream discovered</li>
    <li>[ ] VBAN selectable in OBS</li>
    <li>[ ] Audio synced and stable</li>
  </ul>

  ✅ Outcome: VBAN audio functional.
</div>

---

<div class="panel">
  <div class="panel-header">
    🧠 11. whisper.cpp – Real-Time Speech-to-Text (Advanced)
  </div>

  <ul>
    <li>[ ] whisper.cpp built</li>
    <li>[ ] Models installed</li>
    <li>[ ] Real-time transcription works</li>
    <li>[ ] Subtitle output viable</li>
    <li>[ ] Profanity filtering feasible</li>
  </ul>

  ✅ Outcome: Local STT viable.
</div>
