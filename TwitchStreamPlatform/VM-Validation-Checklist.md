# VM Validation Checklist – Linux Streaming Platform

## Purpose

This checklist defines the **virtual machine–specific validation process** for the
Linux streaming platform.

All build steps are executed according to the canonical build document:

[[Build-Checklist-Linux-Streaming-Platform]]

This checklist focuses on **validation, isolation, rollback, and recovery** in a VM
context and does not redefine build logic.

---

## Scope of VM Validation

VM validation is used to:
- Safely test build steps before bare‑metal deployment
- Isolate failures caused by third‑party software
- Capture repeatable recovery points
- Validate automation readiness

This checklist assumes:
- Hyper‑V is used as the VM host
- VM snapshots (checkpoints) are available
- The generalized build checklist is followed in order

---

## VM Baseline Preparation

- [ ] VM created with appropriate CPU, memory, and storage
- [ ] Networking configured (NAT / bridged as required)
- [ ] VM boots successfully
- [ ] Initial snapshot taken (Pre‑Build Baseline)

✅ VM Checkpoint: **Pre‑Build Baseline**

---

## Build Execution Validation

The following sections correspond directly to steps in the **Build Checklist**.
For each phase, the build checklist is executed and then validated here.

---

## 1. Base OS & Updates Validation

**Reference:**  
Build Checklist §1–§2

- [ ] Zorin OS install completed successfully
- [ ] System updates applied without errors
- [ ] Reboot succeeds
- [ ] Desktop usable

✅ VM Checkpoint: **Post‑OS‑Update Baseline**

✅ Recovery Action:  
Rollback to Pre‑Build Baseline if OS instability occurs.

---

## 2. SSH & PowerShell Validation

**Reference:**  
Build Checklist §3–§4

- [ ] SSH service active and accessible
- [ ] Root SSH login blocked
- [ ] PowerShell launches successfully
- [ ] PowerShell usable for non‑root automation

✅ VM Checkpoint: **Remote Access Enabled**

✅ Recovery Action:  
Rollback to Post‑OS‑Update Baseline.

---

## 3. Security Hardening Validation

**Reference:**  
Build Checklist §5

- [ ] Hardened configuration applied
- [ ] SSH and PowerShell remain functional
- [ ] Desktop usability preserved

✅ VM Checkpoint: **Security Baseline Hardened**

✅ Recovery Action:  
Rollback to Remote Access Enabled.

---

## 4. ZeroTier Validation

**Reference:**  
Build Checklist §6

- [ ] ZeroTier installed and running
- [ ] Node joins designated network
- [ ] Connectivity verified
- [ ] Reboot persistence confirmed

✅ VM Checkpoint: **ZeroTier Functional**

✅ Recovery Action:  
Rollback to Security Baseline Hardened.

---

## 5. Synergy Validation

**Reference:**  
Build Checklist §7

- [ ] Synergy installs and launches
- [ ] Input sharing functional over ZeroTier
- [ ] No unintended access observed

✅ VM Checkpoint: **Operator Control Functional**

✅ Recovery Action:  
Rollback to ZeroTier Functional.

---

## 6. OBS Core Validation

**Reference:**  
Build Checklist §8.1

- [ ] OBS launches reliably
- [ ] Scenes and profiles functional
- [ ] Recording/streaming works

✅ VM Checkpoint: **OBS Core Baseline**

✅ Recovery Action:  
Rollback to Operator Control Functional.

---

## 7. OBS WebSocket Validation

**Reference:**  
Build Checklist §8.2

- [ ] WebSocket enabled with authentication
- [ ] Remote control functional over ZeroTier
- [ ] Stream and scene control validated

✅ VM Checkpoint: **OBS Remote Control Enabled**

✅ Recovery Action:  
Rollback to OBS Core Baseline.

---

## 8. NDI Validation

**Reference:**  
Build Checklist §9

- [ ] NDI source visible and stable
- [ ] Gaming system video received

✅ VM Checkpoint: **NDI Functional**

✅ Recovery Action:  
Rollback to OBS Remote Control Enabled.

---

## 9. VBAN Audio Validation

**Reference:**  
Build Checklist §10

- [ ] VBAN stream received
- [ ] VBAN selectable in OBS
- [ ] Audio stable and synced

✅ VM Checkpoint: **VBAN Audio Functional**

✅ Recovery Action:  
Rollback to NDI Functional.

---

## 10. whisper.cpp Validation (Optional / Advanced)

**Reference:**  
Build Checklist §11

- [ ] whisper.cpp builds successfully
- [ ] Real‑time transcription operates
- [ ] Integration does not destabilize system

✅ VM Checkpoint: **Whisper Functional**

✅ Recovery Action:  
Rollback to VBAN Audio Functional.

---

## 11. Extended Stability Validation

- [ ] OBS runs for extended session
- [ ] No crashes or freezes
- [ ] Reboots preserve configuration
- [ ] Snapshots remain restorable

✅ VM Checkpoint: **VM Validation Complete**

---

## VM Validation Outcome

☐ VM build validated successfully  
☐ VM build failed – rollback required

### Failure Notes
- ______________________________________
- ______________________________________

---

## Notes

Use this section to record VM‑specific observations, host limitations, or issues
that may not apply to bare‑metal deployment.# VM Validation Checklist – Zorin OS 18 Streaming Platform

## Purpose

This checklist defines the validation criteria required before migrating the
Linux-based streaming platform from **virtual machine testing** to **bare-metal
deployment**.

It is intentionally structured to capture **configuration changes** so the
environment can later be recreated via a **playbook or shell script**.

Virtual machine validation is performed using **Hyper‑V on a Windows 10 Pro host**.

---

## Validation Scope

This checklist focuses on **functional correctness, stability, recoverability, and
reproducibility**. Performance tuning is out of scope until bare-metal deployment.

---

## 1. Base Operating System Installation

- [ ] Zorin OS 18 installs successfully
- [ ] System boots reliably
- [ ] Desktop environment loads correctly
- [ ] Network connectivity functions
- [ ] VM snapshots can be created and restored

### Configuration Changes Noted
- Installation options selected
- Disk layout chosen
- Network configuration method

✅ Pass Criteria:  
Base OS is usable and recoverable.

---

## 2. System Updates & Core Configuration

- [ ] All system updates install successfully
- [ ] Reboot completes without errors
- [ ] Desktop remains functional
- [ ] No third‑party software installed yet

### Configuration Changes Noted
- Update mechanisms enabled
- Auto-update policies configured
- System reboot behavior

✅ Pass Criteria:  
Updated system remains stable.

---

## 3. Remote Access – SSH Enablement (Required)

SSH is enabled early to support remote administration and automation.

- [ ] OpenSSH server installed
- [ ] SSH enabled to start on boot
- [ ] SSH access verified from trusted host
- [ ] Root SSH login disabled
- [ ] Firewall restricts SSH access

### Configuration Changes Noted
- SSH daemon configuration files
- Authentication methods
- Firewall rules added
- User access restrictions

✅ Pass Criteria:  
Secure remote shell access available.

---

## 🔐 4. Operating System Security Hardening

- [ ] Non-root user enforced
- [ ] Root interactive login disabled
- [ ] Password policies set
- [ ] Screen lock enabled
- [ ] Time synchronization active
- [ ] Firewall default-deny posture
- [ ] Unused services disabled

### Configuration Changes Noted
- Security policy files modified
- Services disabled or masked
- Firewall defaults
- User/group changes

✅ Pass Criteria:  
Security hardening does not break usability.

---

## 🌐 5. ZeroTier Point-to-Point VPN (Required)

- [ ] ZeroTier installed and running
- [ ] Enabled at boot
- [ ] Node joined to network
- [ ] Node authorized
- [ ] Connectivity verified

### Configuration Changes Noted
- ZeroTier network ID
- Service enablement
- Firewall allowances
- Network interface behavior

✅ Pass Criteria:  
Secure private connectivity works reliably.

---

## ⌨️ 6. Synergy 3 – Keyboard / Mouse Sharing (Required)

- [ ] Synergy installs successfully
- [ ] Application launches
- [ ] Host/client roles configured
- [ ] Input transitions smooth
- [ ] Operates over ZeroTier securely

### Configuration Changes Noted
- Synergy configuration files
- Port usage
- Autostart settings
- Network dependencies

✅ Pass Criteria:  
Input sharing improves workflow safely.

---

## 🎛️ 7. OBS Studio Validation (Critical)

### 7.1 Core OBS Functionality

- [ ] OBS installs successfully
- [ ] OBS launches reliably
- [ ] Scenes and sources created
- [ ] Streaming or recording works
- [ ] Configuration persists across reboot

### Configuration Changes Noted
- OBS config directory paths
- Scene and profile names
- Autostart behavior

---

### 🔐 7.1.b Backup & Recovery – OBS Core

- [ ] OBS config backed up
- [ ] VM snapshot taken
- [ ] Restore verified

✅ Restore Point: **OBS Core Baseline**

---

### 7.2 OBS WebSocket / Remote Control (Critical Subsystem)

- [ ] WebSocket enabled
- [ ] Authentication enabled
- [ ] Custom credentials configured
- [ ] Reachable over ZeroTier
- [ ] Scene switching works remotely
- [ ] Stream control works remotely

### Configuration Changes Noted
- WebSocket port
- Authentication settings
- Firewall rules
- Remote access scope

---

### 🔐 7.2.b Backup & Recovery – OBS WebSocket

- [ ] OBS config updated
- [ ] VM snapshot taken
- [ ] Restore validated

✅ Restore Point: **OBS WebSocket Enabled**

---

## 8. NDI Video Validation (Critical)

- [ ] NDI installed
- [ ] Source visible in OBS
- [ ] Gaming system video received
- [ ] Video stable over time

### Configuration Changes Noted
- NDI plugin versions
- Source naming conventions
- Network requirements

---

### 🔐 8.b Backup & Recovery – NDI

- [ ] OBS config backed up
- [ ] VM snapshot taken
- [ ] Restore validated

✅ Restore Point: **NDI Functional**

---

## 🎧 9. Audio Routing – VBAN (Critical)

- [ ] VBAN receiver installed
- [ ] Stream discoverable
- [ ] VBAN selectable in OBS
- [ ] Audio meters functional
- [ ] Audio stable and synced

### Configuration Changes Noted
- VBAN endpoints
- Audio device mappings
- OBS source settings

---

### 🔐 9.b Backup & Recovery – VBAN

- [ ] Audio config backed up
- [ ] VM snapshot taken
- [ ] Restore validated

✅ Restore Point: **VBAN Audio Functional**

---

## 🧠 10. whisper.cpp – Real-Time Speech-to-Text (Advanced)

- [ ] whisper.cpp builds
- [ ] Model files downloaded
- [ ] Real-time transcription works
- [ ] Subtitles usable
- [ ] Profanity filtering viable
- [ ] Resource usage acceptable

### Configuration Changes Noted
- Build flags
- Model versions
- Runtime invocation
- Integration points

---

### 🔐 10.b Backup & Recovery – whisper.cpp

- [ ] Build artifacts documented
- [ ] VM snapshot taken
- [ ] Restore validated

✅ Restore Point: **Whisper STT Functional**

---

## 11. Stability & Usability

- [ ] System responsive under load
- [ ] No recurring crashes
- [ ] Suspend/resume works
- [ ] Reboots do not break setup

✅ Pass Criteria:  
System usable for regular operation.

---

## 12. Documentation & Playbook Readiness

- [ ] All configuration changes recorded
- [ ] Restore points labeled
- [ ] Manual steps identified
- [ ] Automation candidates noted

✅ Pass Criteria:  
Environment can be rebuilt deterministically.

---

## Bare-Metal Migration Decision

☐ Approved for Bare-Metal Deployment  
☐ Blocked – Issues Remain

Blocking Issues:
- ______________________________________
- ______________________________________

---

## Notes & Observations

Capture lessons learned and future improvements.
