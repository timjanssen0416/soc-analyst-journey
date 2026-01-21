# 🔍 Elastic Stack (ELK) – SOC Fundamentals

> 📌 Based on TryHackMe training  
> 🎯 Focused on SOC analysis, log investigation, and dashboards

---

## 🎯 Learning Objectives

By completing this module, I learned how to:

- Understand the components of the **Elastic Stack (ELK)** 🧱
- Use ELK as a **SIEM-like solution** in a SOC
- Search and filter logs efficiently
- Investigate **VPN logs** to detect anomalies 🔐
- Create **visualizations and dashboards** for SOC visibility 📊

---

## 🧠 What Is the Elastic Stack (ELK)?

The **Elastic Stack** is a collection of open-source tools used to **collect, process, search, and visualize large volumes of data**.  
While originally designed for data analytics, it is widely used by **SOC teams as a SIEM solution**.

---

## 🧩 Core Components of ELK

### 🔎 Elasticsearch
- High-performance **search and analytics engine**
- Stores data in **JSON format**
- Enables fast querying of massive datasets

---

### 🔄 Logstash
- Data processing pipeline
- Ingests logs from multiple sources
- Filters, parses, and **normalizes** data before storage

---

### 🚚 Beats
- Lightweight **data shippers (agents)**
- Installed on endpoints or servers
- Examples:
  - `Filebeat` → log files
  - `Winlogbeat` → Windows Event Logs

---

### 📊 Kibana
- Web-based **visualization and analysis interface**
- Used by SOC analysts to:
  - Search logs
  - Investigate incidents
  - Build dashboards

---

## 🔗 How ELK Works Together

1. 📥 **Beats** collect data
2. 🔄 **Logstash** processes and normalizes it
3. 🗄️ **Elasticsearch** stores and indexes it
4. 📊 **Kibana** visualizes and analyzes it

---

## 🧪 Kibana Discover Tab

The **Discover tab** is the primary workspace for SOC analysts.

### Key Features:
- 🧾 **Index Pattern** – Select which dataset to analyze
- 🧩 **Fields Pane** – View and filter normalized fields
- 🔍 **Search Bar** – Execute queries
- ⏱️ **Time Filter & Histogram** – Spot activity spikes
- 📄 **Log Rows** – Individual events

📌 Ideal for **initial triage and investigation**

---

## 🔎 KQL – Kibana Query Language

KQL is used to search logs in Elasticsearch.

### Supported searches:
- 🆓 Free-text search
- 🎯 Field-based search (`field:value`)
- 🔗 Logical operators: `AND`, `OR`, `NOT`
- ⭐ Wildcards (`*`)

# 🛡️ Introduction to SOAR (Security Orchestration, Automation, and Response)

This repository contains my study notes and practical insights into **SOAR** technology, exploring how it revolutionizes modern Security Operations Centers (SOC) by addressing traditional bottlenecks through automation.

---

## 🎯 Learning Objectives
* Understand the traditional **SOC** architecture and its core challenges.
* Explore how **SOAR** overcomes these challenges.
* Deep dive into **SOAR Playbooks** and their logic.
* Practically walk through a **Threat Intelligence workflow**.

---

## 🏛️ Task 1: The Traditional SOC & Its Challenges

A Security Operations Center (SOC) serves as a centralized hub for monitoring and protecting digital assets. It relies on a synergy of **People, Processes, and Technology**.

### Key Responsibilities of a SOC:
* 🔍 **Monitoring & Detection:** Continuous scanning for suspicious activities via **SIEM** (e.g., detecting brute force attempts).
* 🛠️ **Recovery & Remediation:** Acting as "First Responders" by isolating infected endpoints (via **EDR**), blocking malicious IPs (via **Firewalls**), or disabling compromised users (via **IAM**).
* 📡 **Threat Intelligence:** Utilizing real-time data feeds (IPs, hashes, domains) to stay ahead of emerging threats.
* 📢 **Communication:** Coordinating with IT teams and management to ensure incidents are addressed and documented.

### ⚠️ Common SOC Challenges:
1. **Alert Fatigue:** Analysts are overwhelmed by a massive volume of security events, many of which are false positives.
2. **Disconnected Tools:** Security solutions often operate in silos, forcing analysts to manually switch between multiple dashboards.
3. **Manual Processes:** Lack of documented procedures leads to inefficient investigations and slower response times.
4. **Talent Shortage:** High pressure and repetitive tasks make it difficult to retain and expand skilled security teams.

---

## 🚀 Task 2: Overcoming Challenges with SOAR

**SOAR** is the "glue" that unifies all security tools into a single interface, providing a structured way to document, track, and resolve incidents.

### The Three Pillars of SOAR:
1. 🎼 **Orchestration:** Connecting different tools (from various vendors) into seamless workflows. It uses **Playbooks** to define investigation steps.
2. 🤖 **Automation:** Executing playbook steps automatically without human intervention (e.g., auto-checking IP reputation).
3. ⚡ **Response:** Taking direct action from the SOAR interface, such as blocking a domain or isolating a host.

> **Note:** Does SOAR replace analysts? **No.** While it handles repetitive tasks, human judgment is still vital for complex investigations and business context.

---

## 📋 Task 3: Building SOAR Playbooks

Playbooks are the "recipes" for security investigations. They follow "if-this-then-that" logic to standardize responses.

### 🎣 1. Phishing Playbook
Phishing is the #1 attack vector. A SOAR playbook automates the time-consuming parts:
* **Trigger:** Suspicious email received.
* **Action:** Automatically extract URLs/attachments.
* **Analysis:** Scan via Threat Intel platforms.
* **Outcome:** If malicious, delete the email across the organization and block the sender.

### 🛡️ 2. CVE Patching Playbook
Managing **CVEs** (Common Vulnerabilities and Exposures) can be overwhelming.
* **Trigger:** New CVE disclosure from Advisory Lists.
* **Action:** Analyze risk threshold and scan the network for vulnerable assets.
* **Remediation:** Create a patching ticket for IT and verify the patch post-deployment.
* **Fallback:** If assets remain vulnerable, develop a **Mitigation Plan**.

---

## 💻 Practical Lab: Threat Intel Workflow
In this practical scenario, I successfully implemented a SOAR workflow to automate a Threat Intelligence integration. 

**Key Takeaway:** Automation significantly reduces the **Mean Time to Respond (MTTR)** and allows the SOC team to focus on high-priority threats.

**Completion Flag:** `THM{AUT0M@T1N6_S3CUR1T¥}`

---
*Developed as part of my Cybersecurity Analyst training path.*


