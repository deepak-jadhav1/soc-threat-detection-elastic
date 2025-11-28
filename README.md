# 🛡️ SOC Analyst Threat Detection Project — Elastic SIEM + Sysmon

This project demonstrates my hands-on ability to detect, analyze, and respond to security threats using **Elastic SIEM**, **Sysmon logs**, and **KQL-based threat hunting**.  
The objective of this lab is to simulate a real SOC workflow including log ingestion, detection engineering, alert creation, and IOC analysis.

---

## 🚀 Project Overview

This project replicates real-world SOC analyst tasks:

- Ingested Sysmon telemetry into Elastic SIEM  
- Performed threat hunting with KQL  
- Analyzed malicious PowerShell behavior  
- Detected malware download attempts  
- Investigated failed login brute-force attempts  
- Detected suspicious network traffic  
- Created SIEM detection rules  
- Extracted and analyzed IOCs  
- Produced a final incident summary  

This lab aligns with MITRE ATT&CK techniques:
- **T1059.001 – PowerShell**
- **T1105 – Ingress Tool Transfer**
- **T1110 – Brute Force**
- **T1040 – Network Traffic Analysis**

---

## 📥 1. Log Ingestion (Sysmon → Elastic)

Imported custom Sysmon logs into Elastic SIEM via:


Created index:



Verified events using Discover:
- Process creation (EventCode 1)
- Network connections (EventCode 3)
- Failed logins (4625)
- PowerShell script blocks (4104)

---

## 🔍 2. Threat Hunting Queries (KQL)


### ✔ Detection 1 — PowerShell EncodedCommand (Obfuscation)
### ✔ Detection 2 — Malware Download via DownloadString
### ✔ Detection 3 — Invoke-WebRequest Download Attempt
### ✔ Detection 4 — Failed Login Attempts
### ✔ Detection 5 — Suspicious Network Traffic (Sysmon EventCode 3)


---

## ⚡ 3. Detection Rule Creation (Elastic SIEM)

Created custom query rule:

**Rule name:**  


**Severity:** High  
**Risk Score:** 75  
**Index Pattern:** `sysmon-data`

Used rule preview to validate detection matches.

---

## 🧬 4. IOC Extraction & Analysis

### 🟥 Malicious IPs  
- **45.33.32.156**  
- **103.21.244.15**

### 🟥 Malicious URLs  
- `http://evil.com/x.ps1`  
- `http://malicious.example/test.ps1`

### 🟥 Malicious PowerShell Commands  
- EncodedCommand payload  
- `DownloadString()` malware loader  
- `Invoke-WebRequest` payload retrieval  

### 🟥 Authentication IOC  
- **EventCode 4625** — failed login attempts  

These IOCs demonstrate malware download behavior, obfuscated payload execution, and unauthorized access attempts.

---

## 📊 5. Screenshots

Include your screenshots in this section:  
- Detection 1: EncodedCommand  
- Detection 2: DownloadString  
- Detection 3: Invoke-WebRequest  
- Detection 4: 4625  
- Detection 5: Network Events  
- Detection Rule Preview  

---

## 📝 6. Incident Summary (What I Found)

An endpoint executed multiple suspicious PowerShell commands linked to malware download techniques.  
Outbound connections to known-malicious IPs were observed, along with unauthorized authentication attempts.  
A custom SIEM rule was engineered to detect this behavior automatically.

This project demonstrates full end-to-end detection engineering and SOC investigation skills.

---

## 🧰 Skills Demonstrated

- SIEM (Elastic Security)
- Sysmon Log Analysis
- Detection Engineering
- KQL Query Writing
- Threat Hunting
- PowerShell Threat Analysis
- IOC Extraction
- MITRE ATT&CK Mapping

---

## 🧑‍💻 Author

**Deepak Jadhav**  
