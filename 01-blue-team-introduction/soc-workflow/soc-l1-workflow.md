# SOC Level 1 Workflow

## 🎯 Purpose
This document describes the standard workflow of a **SOC Level 1 (Junior SOC Analyst)**.  
The goal of SOC L1 is to **detect, triage, document, and escalate security alerts** efficiently while minimizing false positives.

---

## 🔄 High-Level SOC Workflow

1. Alert is generated
2. Alert is triaged
3. Initial investigation is performed
4. Decision is made (benign or suspicious)
5. Incident is escalated (if required)
6. Alert is documented and closed

---

## 🧩 Step-by-Step SOC L1 Workflow

### 1️⃣ Alert Generation
An alert is triggered by a security tool such as:
- SIEM (Splunk, Elastic)
- EDR / Antivirus
- IDS / IPS
- Email security gateway
- Firewall or proxy

The alert usually contains:
- Timestamp
- Source and destination
- Alert type or rule name
- Severity level

📌 *SOC L1 does not create alerts — they respond to them.*

---

### 2️⃣ Alert Triage
The SOC analyst reviews the alert to determine:
- Is this a **true positive** or **false positive**?
- Is this expected or unexpected behavior?
- Does it match known attack patterns?

Key triage questions:
- What asset is involved?
- Who is the user?
- Is this system business-critical?
- Has this alert happened before?

📌 *Most alerts are filtered out at this stage.*

---

### 3️⃣ Initial Investigation
If the alert looks suspicious, the analyst gathers context:

#### Common investigation steps:
- Review logs (authentication, network, endpoint)
- Check IPs, domains, hashes against threat intelligence
- Correlate with other alerts
- Look for unusual behavior (time, location, volume)

Tools used:
- SIEM
- Threat intelligence platforms
- EDR console
- Email analysis tools

📌 *SOC L1 focuses on understanding what happened, not full remediation.*

---

### 4️⃣ Decision Making
After investigation, the analyst decides:

#### Option A: Benign / False Positive
- Activity is legitimate
- Alert triggered by misconfiguration or normal behavior
- Alert is documented and closed

#### Option B: Suspicious / Malicious
- Indicators suggest compromise or attack
- Further investigation or response is required

📌 *When in doubt → escalate.*

---

### 5️⃣ Escalation
If the alert is confirmed or strongly suspicious, SOC L1 escalates to:
- SOC Level 2
- Incident Response Team (CIRT)
- SOC Manager (for critical incidents)

Escalation includes:
- Summary of findings
- Logs and evidence
- Affected systems or users
- Recommended next steps

📌 *Clear documentation is critical here.*

---

### 6️⃣ Documentation & Closure
Every alert must be documented, including:
- What triggered the alert
- What was investigated
- What decision was made
- Who was notified (if escalated)

This information is stored in:
- Ticketing system
- Case management tool
- SOC workbook

📌 *Good documentation improves detection and future response.*

---

## 🧠 SOC L1 Mindset

A SOC Level 1 analyst should always:
- Think analytically, not emotionally
- Avoid assumptions
- Follow procedures
- Ask for help when unsure
- Learn from every alert

---

## 📌 Key Takeaways
- SOC L1 focuses on **detection, triage, and escalation**
- Most alerts are false positives
- Investigation is about **context**
- Escalation is a strength, not a weakness
- Documentation is as important as detection

---

## 🚀 Next Steps
- Practice alert triage in SIEM labs
- Improve log analysis skills
- Learn common attack patterns (MITRE ATT&CK)
- Build investigation write-ups
