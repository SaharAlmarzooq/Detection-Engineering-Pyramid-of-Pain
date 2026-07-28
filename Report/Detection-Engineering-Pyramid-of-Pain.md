# 🛡️ Detection Engineering – Pyramid of Pain

## Executive Summary

This project demonstrates the practical application of Detection Engineering using the Pyramid of Pain framework. The objective was to progressively improve malware detection by moving beyond simple Indicators of Compromise (IOCs) toward identifying attacker behaviors and techniques that are significantly more difficult to evade.

Throughout the project, multiple malware samples were analyzed, and new detection methods were developed at each stage to increase the operational cost for the attacker.

---

# Pyramid of Pain Overview

The Pyramid of Pain describes how difficult it is for an attacker to change different indicators once defenders begin detecting them.

Lower-level indicators such as file hashes are easy to modify, while attacker behaviors and Tactics, Techniques, and Procedures (TTPs) require substantial effort to change.

This project demonstrates that progression through six different detection stages.

---

# Detection Journey

## Stage 1 — File Hash Detection

**Detection Method**
- SHA256 File Hash

**Purpose**
- Identify a known malicious executable.

**Strengths**
- Very high confidence.
- Minimal false positives.

**Weaknesses**
- Easily bypassed by recompiling or modifying the malware.

---

## Stage 2 — IP Address Detection

**Detection Method**
- Firewall Rule

**Purpose**
- Block outbound communication with attacker infrastructure.

**Strengths**
- Prevents communication with known servers.

**Weaknesses**
- Attackers can easily migrate to new IP addresses.

---

## Stage 3 — Domain Detection

**Detection Method**
- DNS Filtering

**Purpose**
- Detect malicious communication based on domain names.

**Strengths**
- More resilient than IP-based detection.

**Weaknesses**
- Attackers can register new domains.

---

## Stage 4 — Host Artifact Detection

**Detection Method**
- Sigma Rule
- Registry Monitoring

**Purpose**
- Detect attempts to disable Microsoft Defender Real-Time Protection.

**Observed Activity**
- Registry modification:
  - DisableRealtimeMonitoring = 1

**MITRE ATT&CK**
- T1562.001 — Impair Defenses

---

## Stage 5 — Behavioral Detection

**Detection Method**
- Network Beaconing Detection

**Purpose**
- Identify periodic outbound HTTPS connections typical of Command and Control (C2) communications.

**Observed Behavior**
- Repeated outbound connections
- Constant communication interval
- Small network packets

**MITRE ATT&CK**
- T1071 — Application Layer Protocol

---

## Stage 6 — TTP Detection

**Detection Method**
- Suspicious Process Creation
- Sigma Rules

**Purpose**
- Detect common discovery commands executed after initial compromise.

**Observed Commands**
- whoami
- hostname
- ipconfig
- systeminfo
- net user
- net localgroup

**MITRE ATT&CK**

- T1082 — System Information Discovery
- T1033 — System Owner/User Discovery
- T1016 — System Network Configuration Discovery

---

# Detection Engineering Lessons

Throughout this project, detection strategies became progressively more resilient.

Instead of relying only on static indicators, detection evolved toward identifying attacker behaviors and operational techniques.

This significantly increases the effort required for attackers to evade detection while improving defensive visibility.

---

# Skills Demonstrated

- Detection Engineering
- Sigma Rule Development
- Threat Hunting
- Windows Event Analysis
- Registry Monitoring
- Firewall Rule Creation
- DNS Filtering
- Behavioral Detection
- MITRE ATT&CK Mapping
- SOC Investigation

---

# Conclusion

The Pyramid of Pain provides a practical model for designing resilient detection strategies.

By progressing from simple IOCs toward behavioral and TTP-based detections, defenders can substantially increase attacker cost while improving long-term detection capabilities.

This project demonstrates how layered Detection Engineering techniques can strengthen Security Operations Center (SOC) monitoring and response capabilities.
