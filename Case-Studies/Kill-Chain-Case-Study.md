# 🛡️ Case Study: Analyzing and Neutralizing a Multi-Stage Phishing Attack

## 📖 The Scenario
**Context:** LexSecure is a medium-sized law firm that handles hundreds of emails daily, including numerous job applications from legal talent. Due to the highly sensitive nature of their client data, the firm is a prime target for cyber-attacks.

**The Threat:** A threat actor known as "Megatron" has targeted the firm’s client dossiers and financial records. The attacker plans a highly targeted Spear Phishing campaign to breach the perimeter, establish a persistent backdoor, and ultimately exfiltrate sensitive data for extortion.

**Project Objective:** This case study simulates the complete attack lifecycle using the **Cyber Kill Chain** framework. It explores how the attack is technically constructed from an offensive perspective (Red Team) and demonstrates how a SOC Analyst can detect and neutralize the threat in its early stages (Blue Team) to prevent a catastrophic breach.

---

## 🏗️ Phase 1: The Attack (Red Team Perspective)

### 1. Reconnaissance 🔍
* **Method:** Passive & Active OSINT.
* **Tools:** `LinkedIn`, `Hunter.io`, `theHarvester`, and `Nmap`.
* **Action:** Identified the HR Manager’s email address and discovered a job vacancy for a Junior Legal Assistant. Performed port scanning to map the external infrastructure and identify potential entry points.

### 2. Weaponization 🛠️
* **Payload:** A malicious Microsoft Word document (`CV_Candidate_2024.doc`).
* **Technique:** Embedded VBA Macros.
* **Logic:** The macro was designed to execute a **LOLBin** (PowerShell) to download a secondary payload from a remote server.

### 3. Delivery 📬
* **Method:** Spear Phishing.
* **Social Engineering:** An email was sent to HR appearing as a legitimate job application. By referencing the current vacancy, the attacker lowered the target's suspicion and encouraged them to open the attachment.

### 4. Exploitation & 5. Installation 🔓⚙️
* **Execution:** The user clicked "Enable Content," triggering an **Unexpected Process Spawn** (`winword.exe` -> `powershell.exe`).
* **Persistence:** Created a hidden **Windows Service** using `sc.exe` (masquerading as "Chrome Maintenance Task") to ensure the backdoor starts automatically upon system reboot with SYSTEM privileges.

### 6. Command & Control (C2) 📡
* **Method:** Encrypted HTTP/DNS Tunneling.
* **Action:** The malware established a connection to the attacker's server to receive remote commands while camouflaging its traffic as legitimate web activity to evade firewall detection.

### 7. Actions on Objectives 💰
* **Strategy:** **Double Extortion**.
* **Actions:** 1. **Data Discovery:** Located sensitive client dossiers and payment information.
    2. **Exfiltration:** Utilized "Drip-feeding" to slowly move data out of the network without triggering Data Leakage Detection (DLP) thresholds.
    3. **Impact:** Prepared a Ransomware payload to encrypt the network following successful data theft.

---

## 🛡️ Phase 2: The Defense (Blue Team Response)

### 🚨 Detection
The SOC team received a high-priority alert from the SIEM:
> **Alert:** *Abnormal Process Relationship detected. Parent: `winword.exe` | Child: `powershell.exe` with Base64 encoded arguments.*

### 🧪 Incident Response Actions
1. **Containment:** * Immediately isolated the HR Manager’s workstation using the EDR (Endpoint Detection & Response) tool to cut off the C2 communication.
    * Disabled the compromised user account in Active Directory to prevent lateral movement.
2. **Analysis:**
    * Decoded the PowerShell command to identify the C2 server IP and block it at the firewall level.
    * Located and purged the malicious "Chrome Maintenance" service.
3. **Recovery:** * Re-imaged the workstation and implemented a corporate-wide GPO to block macros in Office documents for non-technical departments.

---

## 🎓 Key Lessons Learned
* **Early Kill Chain Breakers:** Detecting the attack during the *Installation* phase prevented the *Actions on Objectives*, saving the firm from data loss and reputational damage.
* **Process Monitoring:** Monitoring Parent-Child process relationships is a critical detection capability for identifying fileless malware and macro-based attacks.
* **The Human Factor:** While technical controls are vital, security awareness training remains the first line of defense against sophisticated Spear Phishing.

---
*Prepared by Tim Janssen as part of my Cybersecurity SOC Portfolio.*
