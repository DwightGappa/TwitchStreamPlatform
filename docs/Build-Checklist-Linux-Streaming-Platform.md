# Build Checklist – Linux Streaming Platform (Zorin OS 18)

## Purpose

This checklist defines the **canonical build process** for the Linux-based streaming
platform. It is intentionally environment-agnostic and can be applied to:

- Virtual machine builds
- Bare-metal deployments
- System rebuilds
- Automated provisioning (scripts/playbooks)

All validation activities should reference this checklist.

---

## Build Scope

This checklist focuses on **correctness, stability, security, and reproducibility**.
Performance tuning is explicitly out of scope until after bare-metal deployment.

---

## 1. Base Operating System Installation

- [ ] Zorin OS 18 installs successfully
- [ ] System boots reliably
- [ ] Desktop environment loads correctly
- [ ] Network connectivity functions
- [ ] Disk layout finalized

### Configuration Changes Noted
- Installer options selected
- Disk partitioning choices
- Network configuration method

✅ Outcome:  
Base OS is usable.

---

## 2. System Updates & Core Configuration

- [ ] All system updates installed
- [ ] Reboot completes successfully
- [ ] Desktop remains functional
- [ ] Automatic updates configured as desired

### Configuration Changes Noted
- Update policies
- Reboot behavior
- Package sources enabled

✅ Outcome:  
System is current and stable.

---

## 3. Remote Access – SSH Enablement (Required)

SSH is enabled to support remote administration and automation.

- [ ] OpenSSH server installed
- [ ] SSH enabled at boot
- [ ] SSH access verified
- [ ] Root SSH login disabled
- [ ] Firewall restricted to trusted access

### Configuration Changes Noted
- SSH daemon config changes
- Authentication methods
- Firewall rules

✅ Outcome:  
Secure remote shell access available.

---

## 4. PowerShell Installation (Required)

PowerShell is installed to support cross-platform automation and scripting.

- [ ] PowerShell installs successfully
- [ ] PowerShell launches without errors
- [ ] Installed version documented
- [ ] Available to non-root users

### Configuration Changes Noted
- PowerShell install source
- Version installed
- Path integration

✅ Outcome:  
PowerShell available for automation.

---

## 🔐 5. Operating System Security Hardening

- [ ] Non-root user enforced
- [ ] Password policies applied
- [ ] Screen lock enabled
- [ ] Time sync active
- [ ] Firewall default-deny posture
- [ ] Unused services disabled

### Configuration Changes Noted
- Modified policy files
- Services disabled/masked
- Firewall defaults

✅ Outcome:  
Reasonable security baseline applied.

---

## 🌐 6. ZeroTier Point-to-Point VPN

- [ ] ZeroTier installed and running
- [ ] Enabled at boot
- [ ] Node joined to network
- [ ] Node authorized
- [ ] Stable connectivity verified

### Configuration Changes Noted
- Network ID
- Interface behavior
- Firewall allowances

✅ Outcome:  
Secure private connectivity available.

---

## ⌨️ 7. Synergy 3 – Keyboard / Mouse Sharing

- [ ] Synergy installed and launches
- [ ] Host/client roles configured
- [ ] Input transitions smooth
- [ ] Operates over ZeroTier only

### Configuration Changes Noted
- Config files
- Ports used
- Autostart behavior

✅ Outcome:  
KVM-style input control operational.

---

## 🎛️ 8. OBS Studio (Critical Application)

### 8.1 Core OBS Functionality

- [ ] OBS installs successfully
- [ ] OBS launches reliably
- [ ] Scenes and sources created
- [ ] Recording/streaming works
- [ ] Configuration persists across reboot

### Configuration Changes Noted
- Config directory paths
- Profiles and scenes
- Autostart settings

✅ Outcome:  
OBS functional.

---

### 8.2 OBS WebSocket / Remote Control (Critical)

- [ ] WebSocket enabled
- [ ] Authentication enabled
- [ ] Custom credentials set
- [ ] Reachable over ZeroTier
- [ ] Scene & stream control works remotely

### Configuration Changes Noted
- Port number
- Auth configuration
- Firewall rules

✅ Outcome:  
Remote OBS control operational.

---

### 🔐 Backup & Recovery Checkpoint – OBS

- [ ] OBS configs backed up
- [ ] Restore path validated

✅ Restore Point: **OBS Baseline**

---

## 9. NDI Video Input

- [ ] NDI installed
- [ ] NDI source visible in OBS
- [ ] Video received from gaming system
- [ ] Video stable

### Configuration Changes Noted
- Plugin versions
- Source names
- Network dependencies

✅ Outcome:  
NDI video operational.

✅ Restore Point: **NDI Functional**

---

## 🎧 10. Audio Routing – VBAN

- [ ] VBAN receiver installed
- [ ] Stream discovered
- [ ] VBAN selectable in OBS
- [ ] Audio synced and stable

### Configuration Changes Noted
- VBAN endpoints
- OBS audio mappings

✅ Outcome:  
VBAN audio functional.

✅ Restore Point: **VBAN Audio Functional**

---

## 🧠 11. whisper.cpp – Real-Time Speech-to-Text (Advanced)

- [ ] whisper.cpp built
- [ ] Models installed
- [ ] Real-time transcription works
- [ ] Subtitle output viable
- [ ] Profanity filtering feasible

### Configuration Changes Noted
- Build flags
- Model versions
- Invocation method

✅ Outcome:  
Local STT viable.

✅ Restore Point: **Whisper Functional**

---

## 12. Stability & Usability

- [ ] System stable under use
- [ ] No recurring crashes
- [ ] Reboots do not break setup

✅ Outcome:  
System usable for daily operation.

---

## 13. Build Reproducibility

- [ ] All config changes recorded
- [ ] Restore points labeled
- [ ] Manual steps identified
- [ ] Automation candidates noted

✅ Outcome:  
System can be rebuilt deterministically.