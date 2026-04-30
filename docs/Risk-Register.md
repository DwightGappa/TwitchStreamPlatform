# Risk Register

<div class="panel info">
<strong>Status:</strong> Active · Maintained  
<br>
<strong>Phase:</strong> Pre‑Execution · Change Control Enforced
</div>

---

## Purpose

This register identifies and tracks technical, operational, and procedural
risks associated with the Windows‑to‑Linux streaming platform migration.
Risks are recorded prior to execution and updated as validation progresses.

---

## Active Risks

| Risk ID | Description                               | Impact | Likelihood |
| ------  | ----------------------------------------- | ------ | ---------- |
| R‑001   | Linux driver incompatibility with capture | High   | Medium     |
|         | or audio hardware                         |        |            |
| R‑002   | Third‑party streaming software regression | High   | Medium     |
| R‑003   | Audio routing complexity increases        | Medium | Medium     |
|         | operational error                         |        |            |
| R‑004   | Performance degradation under live        | Medium | Low        |
|         | streaming load                            |        |            |
| R‑005   | OS updates introduce instability          | Medium | Low        |
|         | mid‑migration                             |        |            |

---

## Mitigation Strategy and Status

| Risk ID | Mitigation Strategy                       | Status   |
| ------  | ------------------------------------------| -------- |
| R‑001   | Validate hardware support in a            | Open     |
|         | controlled VM environment prior           |          |
|         | to execution                              |          |
| R‑002   | Validate OBS, NDI, and audio routing      | Open     |
|         | tooling before platform migration         |          |
| R‑003   | Document audio architecture and           | Open     |
|         | validate alternatives during testing      |          |
| R‑004   | Establish baseline performance metrics    | Open     |
|         | during VM validation                      |          |
| R‑005   | Use an LTS‑based OS with a controlled     | Mitigated|
|         | update cadence                            |          |

---

## Risk Evaluation Criteria

<div class="panel neutral">
<strong>Impact</strong> indicates the severity of operational or functional
failure.  
<br>
<strong>Likelihood</strong> reflects probability based on prior experience.  
<br>
<strong>Status</strong> reflects tracking state, not resolution completeness.
</div>

---

## Review and Change Control

<div class="panel neutral">
<ul>
<li>Risks are reviewed before entering each migration phase</li>
<li>New risks are added as discoveries occur</li>
<li>Status changes require documentation updates</li>
<li>Closed risks remain for historical traceability</li>
</ul>
</div>
