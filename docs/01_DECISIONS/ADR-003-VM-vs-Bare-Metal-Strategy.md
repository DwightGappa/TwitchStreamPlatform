# ADR-003 – Virtual Machine vs Bare‑Metal Validation Strategy

## Status
Accepted

## Decision

Validate the streaming platform on **Zorin OS 18** using a **virtual machine (VM)** before
performing a **bare‑metal installation** on the dedicated streaming/compositing computer.

Bare‑metal deployment will occur only after core streaming workflows are confirmed
functional in the VM environment.

---

## Context

The streaming platform depends on multiple third‑party components (e.g., OBS, NDI,
audio routing utilities) that have previously demonstrated fragility in Linux
environments.

Given:
- Limited hardware available for immediate replacement
- The need to preserve an operational Windows‑based streaming setup during testing
- The risk of extended downtime if third‑party software fails after OS migration

A staged validation approach is required to reduce operational and recovery risk.

Virtual machine validation will be performed using **Hyper‑V on a Windows 10 Pro host**.
Hyper‑V is included with Windows 10 Pro and is already used extensively in the existing
environment for testing and experimentation.

Hyper‑V was selected for VM validation because:
- It is natively integrated into the Windows kernel
- It offers strong performance characteristics compared to desktop hypervisors
- It is well‑suited for repeated test‑and‑reset workflows
- It reflects real‑world virtualization platforms commonly used in IT environments

This also provides an opportunity to reinforce practical virtualization experience
relevant to production IT support and infrastructure roles.

---

## Options Considered

### Direct Bare‑Metal Installation
- ✅ Simplifies hardware stack
- ✅ Eliminates virtualization overhead
- ❌ High risk of prolonged downtime if validation fails
- ❌ Difficult rollback without full OS reinstallation
- ❌ No isolation for experimentation or failure analysis

---

### VM‑First Validation with Later Bare‑Metal Deployment
- ✅ Isolates experimentation from production hardware
- ✅ Enables snapshot‑based rollback and recovery
- ✅ Preserves a working streaming environment during testing
- ✅ Supports controlled iteration and documentation
- ❌ Adds temporary setup complexity
- ❌ Requires re‑validation after migration to bare metal

---

## Decision Rationale

A VM‑first validation strategy was selected to minimize risk while testing a new
Linux‑based streaming platform that depends on fragile third‑party software.

Using Hyper‑V allows validation to occur:
- Without disrupting existing workflows
- With fast recovery from failed experiments
- In an environment representative of common enterprise tooling

Only after functional stability is demonstrated in the VM will the project proceed to
bare‑metal installation. This mirrors standard infrastructure migration practices and
supports disciplined, audit‑friendly execution.

---

## Acceptance Criteria for Bare‑Metal Migration

Bare‑metal deployment will proceed only after the following are verified in the VM:

- OBS Studio launches reliably and can produce a stream
- NDI video capture functions as expected
- Audio routing workflow is viable (native or alternative)
- Webcam input is usable
- System stability is acceptable during typical usage windows

Acceptance criteria may be refined as testing progresses.

---

## Consequences

### Positive
- Reduced risk of extended downtime
- Safer validation of third‑party software
- Clear isolation of failure modes
- Reusable documentation of migration steps
- Practical, real‑world virtualization experience

### Negative / Risks
- VM performance characteristics may differ from bare metal
- Hardware‑specific issues may surface post‑migration
- Additional effort required during validation phase

These risks are accepted to preserve platform reliability and recoverability.

---

## Follow‑Up Actions

- Create and configure a Zorin OS 18 virtual machine in Hyper‑V
- Validate streaming workflows against acceptance criteria
- Document issues, mitigations, and stability observations
- Revisit this decision prior to bare‑metal deployment