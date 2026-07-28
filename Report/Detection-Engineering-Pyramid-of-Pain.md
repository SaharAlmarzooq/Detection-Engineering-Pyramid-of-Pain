# Detection Engineering – Pyramid of Pain

## Objective

The objective of this project was to improve malware detection by moving from simple Indicators of Compromise (IOCs) toward detecting attacker behaviors and techniques.

The project follows the Pyramid of Pain concept, demonstrating why detecting attacker TTPs is significantly more effective than relying solely on hashes, IP addresses, or domains.

---

## Detection Progression

### Level 1 – File Hash Detection

- Detected malware using file hashes (SHA256).
- High confidence detection.
- Easily bypassed by recompiling the malware.

---

### Level 2 – IP Address Blocking

- Blocked outbound communication to the attacker infrastructure.
- Effective against known infrastructure.
- Easily bypassed by changing public IP addresses.

---

### Level 3 – Domain Blocking

- Prevented communication using malicious domain names.
- More resilient than IP blocking.
- Still bypassed through new domains.

---

### Level 4 – Host Artifact Detection

- Detected malicious registry modifications.
- Used host-based telemetry with Sigma rules.
- Increased attacker cost.

---

### Level 5 – Beaconing Detection

- Identified periodic outbound HTTPS beaconing.
- Focused on suspicious communication behavior.
- More resilient than IOC-based detections.

---

### Level 6 – TTP Detection

- Detected common attacker discovery commands.
- Focused on adversary behavior instead of malware artifacts.
- Highest value detection according to the Pyramid of Pain.

---

## Key Takeaways

- IOC-based detection is useful but easily evaded.
- Behavioral detections significantly increase attacker effort.
- Sigma rules provide a flexible method for portable detections.
- Detection Engineering should prioritize behaviors over indicators whenever possible.
