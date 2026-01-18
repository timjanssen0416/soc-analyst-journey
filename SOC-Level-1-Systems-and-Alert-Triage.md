# 🛡️ SOC Level 1 – Systems as Attack Vectors & Alert Handling

> This document summarizes my learning progress in the TryHackMe SOC Analyst Level 1 path.  
> Focus areas include system-based attack vectors, vulnerability management, and SOC L1 alert triage & reporting workflows.

---

## 🔹 Systems as Attack Vectors

### 🎯 Learning Objectives
- Understand the role of systems in modern cyber attacks
- Identify real-world attacks targeting endpoints, servers, and infrastructure
- Learn how SOC teams detect and mitigate system-based threats

---

### 🖥️ What Is a System?
A system can be any digital asset that processes, stores, or transmits data.  
A single compromised system can have **high business impact**.

| Breached System | Potential Impact |
|----------------|------------------|
| Personal laptop | Credential theft, botnet participation |
| IT admin laptop | Full internal network access |
| Mail server | Data leakage & blackmail |
| Industrial server | Ransomware impacting operations |
| Government web panel | Website defacement / activism |

**Key takeaway:**  
✔️ Cyber attacks do **not always require user interaction**  
✔️ One compromised system can lead to **catastrophic consequences**

---

### ⚔️ How Systems Are Attacked

#### 1️⃣ Human-Led Attacks
- Infected USB devices  
- Pirated software  
- Weak or reused passwords  

Humans often unintentionally initiate system compromise.

#### 2️⃣ Vulnerabilities
- Software flaws (CVEs)
- Zero-day vulnerabilities (unknown to vendors)
- Weak credentials or excessive permissions

Example:  
Shellshock (CVE-2014-6271) existed for over 20 years before discovery.

#### 3️⃣ Supply Chain Attacks
Malware delivered via **trusted software updates or libraries**.

Well-known cases:
- SolarWinds
- 3CX

⚠️ Supply chain attacks are difficult to prevent because organizations cannot fully control third-party software.

---

### 🧩 Vulnerabilities vs Misconfigurations

#### 🔧 Software Vulnerabilities
- Fixed by **patching**
- Identified via CVE numbers
- High-risk when actively exploited

**SOC Response:**
- Apply vendor patches
- Restrict access (IP allowlists)
- Temporary mitigations (WAF / IPS rules)
- Monitor exploitation attempts

---

#### ⚙️ Misconfigurations
- Caused by incorrect system setup
- Examples:
  - Default passwords
  - Open admin interfaces
  - Excessive privileges

❌ Cannot be fixed with patches  
✅ Require configuration changes

**Detection & Prevention:**
- Vulnerability scanning
- Configuration audits (CIS Benchmarks)
- Penetration testing

---

### 🛡️ Mitigation Measures

| Control | Purpose |
|------|-------|
| Patch management | Reduce exposure to known vulnerabilities |
| IT security training | Prevent insecure configurations |
| Network access control | Limit attacker reach |
| Antivirus / EDR | Detect and block system abuse |

---

## 🔹 SOC L1 Alert Triage

### 🎯 Learning Objectives
- Understand SOC alerts and their lifecycle
- Perform alert triage as a Level 1 analyst
- Learn prioritization and investigation workflows

---

### 📊 From Events to Alerts
1. Event occurs (login, file creation, process execution)
2. Event is logged
3. Logs are sent to SIEM / EDR
4. Detection rules generate alerts
5. SOC analysts triage alerts instead of raw logs

---

### 🧰 Alert Management Platforms
- **SIEM:** Splunk, Elastic
- **EDR/NDR:** Microsoft Defender, CrowdStrike
- **SOAR:** Splunk SOAR, Cortex XSOAR
- **ITSM:** Jira, TheHive

---

### 👤 SOC Roles in Alert Triage
- **L1 Analyst:** Initial triage & classification
- **L2 Analyst:** Deep investigation & remediation
- **SOC Engineer:** Detection logic & tooling
- **SOC Manager:** Metrics, performance, oversight

---

### 🧾 Alert Properties
Key alert fields include:
- Alert name
- Severity
- Status
- Verdict
- Affected user / host
- Detection logic
- Supporting evidence

---

### 🚦 Alert Prioritization Strategy
1. Take unassigned alerts
2. Sort by severity (Critical → Low)
3. Handle oldest alerts first

---

### 🔍 Alert Triage Workflow (SOC L1)

#### 1️⃣ Initial Actions
- Assign alert to yourself
- Set status to *In Progress*
- Review alert context

#### 2️⃣ Investigation
- Identify affected user/system
- Understand suspicious activity
- Correlate related logs
- Validate findings with threat intelligence

#### 3️⃣ Final Actions
- Classify alert (True / False Positive)
- Document investigation
- Close alert or escalate

---

## 🔹 SOC L1 Alert Reporting & Escalation

### 📝 Why Reporting Matters
- Saves time for L2 analysts
- Preserves investigation context
- Improves analytical thinking

---

### 📄 Alert Report Structure (5 W’s)
- **Who** was involved
- **What** happened
- **When** it occurred
- **Where** it originated
- **Why** it is malicious or benign

---

### ⬆️ When to Escalate
Escalate alerts if:
- Major attack indicators are present
- Remediation is required
- External communication is needed
- You are unsure about the verdict

---

### 💬 SOC Communication Best Practices
- Use out-of-band communication for compromised users
- Escalate missed threats immediately
- Inform L2 when alert volume spikes
- Never ignore alerts due to tooling issues

---

## 📘 Key SOC Concepts

### Alert vs Incident
- **Alert:** A notification triggered by suspicious activity  
- **Incident:** A confirmed security breach requiring response  

➡️ Not every alert becomes an incident.

---

### False Positive vs True Positive
- **False Positive:** Benign activity incorrectly flagged  
- **True Positive:** Confirmed malicious activity  

---

## ✅ Final Takeaways
- Systems are high-value attack targets
- Vulnerabilities and misconfigurations require different responses
- SOC L1 analysts are the first line of defence
- Clear reporting and escalation save time and prevent damage

---

## 📌 Next Steps
- Continue SOC Level 1 labs
- Apply consistent triage workflows
- Document learning progress publicly on GitHub
