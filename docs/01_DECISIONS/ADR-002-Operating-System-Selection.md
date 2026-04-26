# ADR-002 – Operating System Selection (Streaming Platform)

## Status
Accepted

## Decision

Select **Zorin OS 18**, based on **Ubuntu LTS 24.04**, as the target operating system
for the dedicated streaming/compositing computer.

This operating system will be used for:
- Initial virtual machine validation
- Subsequent bare‑metal deployment after testing

---

## Context

The current streaming platform operates on **Windows 10**, which reaches end of
support in **October 2026**. The existing system relies on several third‑party streaming
and audio tools (e.g., OBS, NDI, audio routing software) that are sensitive to operating
system changes.

Previous Linux experimentation has shown that third‑party streaming software can
break easily due to:
- Dependency changes
- Kernel updates
- Package version drift

Hardware availability and budget constraints were explicitly considered as part of the
platform selection process.

As a result, the replacement operating system must prioritize:
- Long‑term stability
- Predictable update behavior
- A mature package ecosystem
- Low friction for transitioning from a Windows‑based workflow

---

## Options Considered

### Windows 11
- ✅ Familiar environment
- ✅ Existing streaming tooling compatibility
- ❌ Requires dedicating an additional computer for streaming
- ❌ Existing Windows 11 2‑in‑1 laptop is shared with other users and unavailable
- ❌ Purchasing an additional dedicated computer is not financially feasible
- ❌ Does not align with long‑term migration and learning objectives

**Outcome:**  
Windows 11 was not pursued due to hardware availability and cost constraints. While
technically viable, it does not currently provide a realistic or sustainable path forward
for a dedicated streaming system.

---

### Vanilla Ubuntu LTS
- ✅ Strong stability and ecosystem
- ✅ Long‑term support guarantees
- ❌ Requires more manual configuration for desktop usability
- ❌ Higher transition overhead from Windows workflows

---

### Zorin OS 18 (Ubuntu LTS–Based)
- ✅ Built on Ubuntu LTS 24.04
- ✅ Long‑term support and predictable updates
- ✅ Desktop environment designed for Windows transition
- ✅ Reduced friction for daily usability
- ✅ Built‑in tooling to ease migration (e.g., OneDrive integration)

---

## Decision Rationale

Zorin OS 18 was selected because it balances **enterprise‑grade Linux stability** with a
desktop experience optimized for Windows users. This reduces operational friction
during testing while preserving the benefits of a stable Linux platform.

By leveraging Ubuntu LTS under the hood, the platform benefits from:
- Broad hardware compatibility
- Extensive community and vendor documentation
- Proven OBS Studio support

This selection supports the project goal of validating a Linux‑based streaming platform
without introducing unnecessary usability complexity.

---

## Consequences

### Positive
- Stable, LTS‑backed foundation for long‑term use
- Faster iteration during virtual machine testing
- Reduced learning curve during Windows → Linux transition
- Sustainable path beyond Windows 10 end‑of‑support

### Negative / Risks
- Third‑party streaming tools may still break or require workarounds
- Zorin‑specific abstractions may obscure some underlying Ubuntu behavior
- Additional validation required during VM → bare‑metal migration

These risks are accepted and intentionally documented as part of the case study.

---

## Follow‑Up Actions

- Validate Zorin OS 18 in a virtual machine
- Test OBS, NDI video, and audio routing workflows
- Document compatibility gaps and mitigations
- Assess readiness for bare‑metal deployment