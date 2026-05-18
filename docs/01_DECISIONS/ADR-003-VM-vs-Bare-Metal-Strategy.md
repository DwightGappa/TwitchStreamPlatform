---
layout: default
title: "ADR‑003: VM vs Bare‑Metal Validation Strategy"
permalink: /docs/decisions/adr-003/
---

<div class="phase-banner">
  <strong>Status:</strong> Accepted<br>
  <strong>Change Control:</strong> Required · Applies to All Phases
</div>

---

## Decision

<div class="panel">
  <div class="panel-header">
    Validation Strategy
    <span class="status status-approved">Accepted</span>
  </div>

  Validate the streaming platform on **Zorin OS 18** using a **virtual machine
  (VM)** before performing a **bare‑metal installation** on the dedicated
  streaming/compositing computer.

  Bare‑metal deployment will occur only after core streaming workflows are
  confirmed functional in the VM environment.
</div>

---

## Context

<div class="panel">
  <div class="panel-header">
    Fragility and Risk
  </div>

  The streaming platform depends on multiple third‑party components (e.g., OBS,
  NDI, audio routing utilities) that have previously demonstrated fragility in
  Linux environments.

  Given:
  <ul>
    <li>Limited hardware available for replacement</li>
    <li>The need to preserve a working Windows setup during testing</li>
    <li>Risk of extended downtime if third‑party software fails</li>
  </ul>

  A staged validation approach is required to reduce operational risk.
</div>

Virtual machine validation will be performed using **Hyper‑V on a Windows 10
Pro host**. Hyper‑V is included with Windows 10 Pro and is already used
extensively for testing and experimentation.

Hyper‑V was selected because it is natively integrated, offers strong
performance, and reflects real‑world virtualization platforms. This also
provides an opportunity to reinforce practical virtualization experience.

---

## Options Considered

<div class="panel">
  <div class="panel-header">
    Direct Bare‑Metal Installation
    <span class="status status-superseded">Rejected</span>
  </div>

  <ul>
    <li>✅ Simplifies hardware stack</li>
    <li>✅ Eliminates virtualization overhead</li>
    <li>❌ High risk of prolonged downtime if validation fails</li>
    <li>❌ Difficult rollback without full OS reinstallation</li>
  </ul>
</div>

---

<div class="panel">
  <div class="panel-header">
    VM‑First Validation
    <span class="status status-approved">Selected</span>
  </div>

  <ul>
    <li>✅ Isolates experimentation from production hardware</li>
    <li>✅ Enables snapshot‑based rollback and recovery</li>
    <li>✅ Preserves working streaming environment during testing</li>
    <li>❌ Requires re‑validation after migration to bare metal</li>
  </ul>
</div>

---

## Decision Rationale

<div class="panel">
  <div class="panel-header">
    Strategic Rationale
  </div>

  A VM‑first validation strategy was selected to minimize risk while testing a
  new Linux‑based streaming platform that depends on fragile software.

  Using Hyper‑V allows validation to occur:
  <ul>
    <li>Without disrupting existing workflows</li>
    <li>With fast recovery from failed experiments</li>
    <li>In an environment representative of common enterprise tooling</li>
  </ul>

  Only after functional stability is demonstrated will the project proceed to
  bare‑metal installation.
</div>

---

## Acceptance Criteria for Bare‑Metal Migration

<div class="panel">
  <div class="panel-header">
    Success Criteria
  </div>

  Bare‑metal deployment will proceed only after the following are verified:
  <ul>
    <li>OBS Studio launches reliably and can produce a stream</li>
    <li>NDI video capture functions as expected</li>
    <li>Audio routing workflow is viable</li>
    <li>Webcam input is usable</li>
    <li>System stability is acceptable during typical usage windows</li>
  </ul>
</div>

---

## Consequences

<div class="panel">
  <div class="panel-header">
    Expected Outcomes
  </div>

  <ul>
    <li>Reduced risk of extended downtime</li>
    <li>Safer validation of third‑party software</li>
    <li>Clear isolation of failure modes</li>
    <li>Reusable documentation of migration steps</li>
    <li>Practical, real‑world virtualization experience</li>
  </ul>
</div>

---

## Follow‑Up Actions

<div class="panel">
  <ul>
    <li>Create and configure a Zorin OS 18 virtual machine in Hyper‑V</li>
    <li>Validate streaming workflows against acceptance criteria</li>
    <li>Document issues, mitigations, and stability observations</li>
    <li>Revisit this decision prior to bare‑metal deployment</li>
  </ul>
</div>
