# 📘 SOC Workbooks, Lookups & Metrics (SOC L1)

This document covers **SOC workbooks, asset & identity lookups, network diagrams, and SOC performance metrics**, based on hands-on labs and simulations from the TryHackMe SOC Analyst Level 1 path.

---

## 📌 SOC Workbooks and Lookups

### 🎯 Learning Objectives
- Understand SOC investigation workbooks (playbooks / runbooks)
- Learn how to use asset and identity inventories
- Interpret corporate network diagrams
- Practice SOC workflows in realistic simulations

---

## 🧑‍💼 Assets and Identities

### Identity Inventory
A **catalog of corporate identities**, including:
- Employees (user accounts)
- Services (machine accounts)
- Privileges, roles, and contact details

### Asset Inventory
A **lookup table of all IT assets**, such as:
- Servers
- Workstations
- Network devices
- Critical data repositories

> Asset inventory is essential for understanding **what is affected**, **who owns it**, and **how critical it is**.

#### Lab Findings
- **R. Lund role:** US Financial Adviser  
- **HQ-FINFS-02 server stores:** Financial Records  
- **File sharing behavior:** Legitimate and expected

---

## 🌐 Network Diagrams

A **network diagram** visually represents:
- Locations
- Subnets
- Network segmentation
- Security boundaries

SOC analysts use network diagrams to **contextualize IP addresses, lateral movement, and attack paths**.

### Example Attack Chain
1. External IP `103.61.240.174` connects to firewall via `TCP/10443`
2. NAT translates traffic to `10.10.0.53`
3. Internal scanning of `172.16.15.0/24` (Database subnet)
4. Continued scanning of `172.16.23.0/24`
5. VPN brute force against `vpn.tryhackme.thm`
6. Successful VPN login → attacker assigned VPN subnet IP
7. Attempted access to Database subnet (blocked)
8. Switch to Office subnet for further compromise

#### Analysis Results
- **Service on TCP/10443:** VPN  
- **172.16.15.99 subnet:** Database subnet  
- **Verdict:** True Positive (TP)

---

## 📖 SOC Workbooks (Playbooks)

A **SOC Workbook** is a structured guide that defines how analysts should:
- Investigate alerts
- Make decisions
- Escalate incidents

Workbooks are especially critical for **SOC L1 analysts**, ensuring:
- Consistent investigations
- Reduced errors
- Faster triage

### Typical Workbook Stages
1. **Enrichment**
   - Threat intelligence
   - Asset & identity lookups
2. **Investigation**
   - SIEM log analysis
   - Context validation
3. **Escalation**
   - Notify L2 or contact user if required

#### Key Concepts
- **Primary users:** SOC L1 Analysts  
- **Context gathering process:** Enrichment  
- **Identity inventory example platform:** BambooHR  

#### Workbook Practice Flags
- `THM{the_most_common_soc_workbook}`
- `THM{be_vigilant_with_powershell}`
- `THM{asset_inventory_is_essential}`

---

## 📊 SOC Metrics and Objectives

### 🎯 Learning Objectives
- Understand SLA, MTTD, MTTA, and MTTR
- Learn the importance of False Positive Rate
- Improve SOC performance as an L1 analyst

---

## 📈 Core SOC Metrics

| Metric | Formula | Purpose |
|------|-------|--------|
| Alerts Count | Total alerts received | Analyst workload |
| False Positive Rate (FPR) | False Positives / Total Alerts | Alert noise level |
| Alert Escalation Rate (AER) | Escalated Alerts / Total Alerts | L1 analyst experience |
| Threat Detection Rate (TDR) | Detected Threats / Total Threats | SOC reliability |

### Key Insights
- Ideal alerts per L1 analyst: **5–30 per day**
- FPR ≥ **80%** indicates serious tuning issues
- AER should be **<50%**, ideally **<20%**
- TDR must always be **100%**

---

## ⏱️ Triage & SLA Metrics

SOC performance is measured via **Service Level Agreements (SLA)**.

| Metric | Typical SLA | Description |
|------|-----------|------------|
| SOC Availability | 24/7 | Operational coverage |
| Mean Time to Detect (MTTD) | 5 minutes | Attack → Detection |
| Mean Time to Acknowledge (MTTA) | 10 minutes | Alert → Analyst action |
| Mean Time to Respond (MTTR) | 60 minutes | Detection → Containment |

### Example Calculation
- Detection after 12 min → **MTTD = 12**
- Acknowledgement after 10 min → **MTTA = 10**
- Response took 51 min → **MTTR = 51**

---

## 🔧 Improving SOC Metrics

| Issue | Recommended Actions |
|----|------------------|
| FPR > 80% | Tune detection rules, exclude trusted behavior, automate triage |
| MTTD > 30 min | Optimize detection rules, ensure real-time log ingestion |
| MTTA > 30 min | Improve alert notifications and workload distribution |
| MTTR > 4 hours | Faster escalation, documented incident procedures |

> Improving metrics is a **shared responsibility across all SOC roles**.

---

## 🧪 Practice & Simulation Results

- `THM{mttr:quick_start_but_slow_response}`
- `THM{mttd:time_between_attack_and_alert}`
- `THM{fpr:the_main_cause_of_l1_burnout}`

---

## 🎣 SOC Simulator – Phishing

Completed a **SOC Simulator scenario focused on phishing detection**, including:
- Email header analysis
- Sender reputation validation
- User impact assessment
- Alert reporting & escalation

This simulation reinforced:
- Alert triage workflows
- SOC communication best practices
- Real-world phishing response handling

---

## 🧠 Key Terminology

- **Alert vs Incident**
  - Alert: Notification of suspicious activity
  - Incident: Confirmed security breach requiring response

- **False Positive vs True Positive**
  - False Positive: Benign activity incorrectly flagged
  - True Positive: Legitimate malicious activity

---

🛡️ *“Metrics don’t just measure performance — they shape behavior.”*

