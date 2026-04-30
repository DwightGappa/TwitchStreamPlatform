# ADR‑002: Operating System Selection (Streaming Platform)

<div class="phase-banner">
  <strong>Status:</strong> Accepted<br>
  <strong>Change Control:</strong> Required · Applies to All Phases
</div>

---

## Decision

<div class="panel">
  <div class="panel-header">
    Operating System Selection
    <span class="status status-approved">Accepted</span>
  </div>

  Select <strong>Zorin OS 18</strong>, based on
  <strong>Ubuntu LTS 24.04</strong>, as the target operating
  system for the dedicated streaming and compositing computer.
</div>

The selected operating system will be used for:

- Initial validation in a virtual machine
- Subsequent bare‑metal deployment following successful testing

---

## Context

<div class="panel">
  <div class="panel-header">
    Background and Constraints
  </div>

  The current streaming platform operates on
  <strong>Windows 10</strong>, which reaches end of support in
  <strong>October 2026</strong>. The existing system relies on
  third‑party streaming and audio tooling that is sensitive to
  operating system changes.
</div>

Prior experimentation with Linux platforms has demonstrated
increased failure risk due to:

- Dependency changes
- Kernel updates
- Package version drift

Hardware availability and budget constraints were explicitly
considered. Any replacement operating system must therefore
prioritize:

- Long‑term stability
- Predictable update behavior
- A mature package ecosystem
- Minimal friction transitioning from a Windows‑based workflow

---

## Options Considered

<div class="panel">
  <div class="panel-header">
    Windows 11
    <span class="status status-superseded">Rejected</span>
  </div>

  <ul>
    <li>✅ Familiar environment</li>
    <li>✅ Existing streaming tooling compatibility</li>
    <li>❌ Requires an additional dedicated computer</li>
    <li>
      ❌ Existing Windows 11 laptop unavailable for
      exclusive use
    </li>
    <li>
      ❌ Additional hardware purchase not financially
      feasible
    </li>
    <li>
      ❌ Does not align with long‑term migration
      objectives
    </li>
  </ul>

  <strong>Outcome:</strong> Rejected due to hardware availability
  and cost constraints.
</div>

---

<div class="panel">
  <div class="panel-header">
    Vanilla Ubuntu LTS
    <span class="status status-draft">Not Selected</span>
  </div>

  <ul>
    <li>✅ Strong stability guarantees</li>
    <li>✅ Mature and well‑supported package ecosystem</li>
    <li>❌ Higher configuration overhead</li>
    <li>
      ❌ Less streamlined desktop experience for hybrid
      streaming workflows
    </li>
  </ul>
</div>

---

<div class="panel">
  <div class="panel-header">
    Zorin OS 18 (Ubuntu LTS 24.04)
    <span class="status status-approved">Selected</span>
  </div>

  <ul>
    <li>✅ Built on Ubuntu LTS stability base</li>
    <li>✅ Predictable update model</li>
    <li>
      ✅ Desktop experience optimized for Windows
      transitions
    </li>
    <li>
      ✅ Reduced configuration friction for streaming
      workloads
    </li>
  </ul>
</div>

---

## Consequences

<div class="panel">
  <div class="panel-header">
    Expected Outcomes
  </div>

  Selecting Zorin OS 18 establishes a stable Linux baseline
  suitable for controlled validation and eventual production
  deployment while minimizing operational risk during the
  Windows‑to‑Linux migration.
</div>

---

## Notes

<div class="panel">
  <div class="panel-header">
    Change Control Notes
  </div>

  This operating system selection is binding for all validation
  and deployment phases unless explicitly superseded by a future
  ADR.
</div>
