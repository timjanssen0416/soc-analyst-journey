# 🧪 Case Study: EDR Telemetry vs SIEM Correlation

> 📘 This case study explains the practical differences between **EDR** and **SIEM**  
> 🎯 Written from a **Junior SOC Analyst** perspective

---

## 🧠 Scenario Overview

An organization detects suspicious activity on an employee workstation.  
Multiple security tools generate alerts, including the **EDR platform** and the **SIEM system**.

This case study answers two key SOC questions:

1. ❓ What does EDR log?
2. ❓ What does SIEM actually do?

---

## 🛡️ What Does EDR Log?

### 📍 EDR Focus: Endpoint-Level Visibility

EDR logs **everything that happens on an endpoint** (workstation or server) in near real time.

### 📊 Types of EDR Telemetry

EDR typically logs:

#### ⚙️ Process Activity
- Process creation & termination
- Parent-child process relationships
- Command-line arguments
- Execution paths

**Example:**
winword.exe → powershell.exe → curl.exe

---

#### 📁 File System Activity
- File creation, modification, deletion
- File hashes (MD5, SHA256)
- File paths and permissions

---

#### 🌐 Network Activity
- Outbound and inbound connections
- Destination IP addresses and domains
- Ports and protocols
- C2 (Command & Control) communication attempts

---

#### 🗝️ Registry Activity
- Registry key creation and modification
- Persistence mechanisms (Run keys, Services)

---

#### 👤 User & Privilege Activity
- Logged-in user
- Privilege escalation attempts
- Token misuse

---

### 🧩 EDR Context Advantage

EDR provides:
- 🕵️ Full attack timelines
- 🔗 Process trees
- 📌 Precise endpoint attribution

📌 **Key takeaway:**  
EDR answers the question:  
> *“What exactly happened on this specific machine?”*

---

## 📊 What Does SIEM Do?

### 🧠 SIEM Focus: Centralized Correlation

SIEM **does not generate raw telemetry itself**.  
Instead, it **collects, correlates, and analyzes logs** from multiple sources.

### 📥 Common SIEM Log Sources

SIEM ingests logs from:
- 🛡️ EDR platforms
- 🔥 Firewalls
- 🌐 Web proxies
- 🪟 Windows Event Logs
- 🔐 Identity systems (AD, Azure AD)
- ☁️ Cloud services

---

### 🔗 SIEM Correlation Example

#### 📌 Scenario:
- EDR reports malware execution on a workstation
- Firewall logs show outbound traffic to a suspicious IP
- VPN logs show the same user logged in from a foreign country

#### 🚨 SIEM Action:
- Correlates all events
- Detects abnormal behavior
- Raises a **high-severity incident**

---

### ⚙️ What SIEM Actually Does

SIEM performs:
- 📊 Log aggregation
- 🔍 Correlation across systems
- 🚨 Alerting based on rules & patterns
- 📈 Dashboards & KPIs
- 🧾 Compliance reporting

📌 **Key takeaway:**  
SIEM answers the question:  
> *“Is this activity suspicious across the entire environment?”*

---

## 🆚 EDR vs SIEM – SOC Perspective

| Capability | EDR | SIEM |
|---------|-----|------|
| Endpoint visibility | ✅ Yes | ❌ No |
| Network-wide view | ❌ Limited | ✅ Yes |
| Behavioral detection | ✅ Strong | ⚠️ Rule-based |
| Forensics | ✅ Excellent | ❌ Limited |
| Log correlation | ❌ No | ✅ Yes |
| Incident prioritization | ⚠️ Medium | ✅ Strong |

---

## 🔄 SOC Workflow Example

1. 🚨 **EDR alert** triggered on endpoint
2. 🔍 Analyst investigates process tree
3. 📤 Logs forwarded to SIEM
4. 🧠 SIEM correlates with firewall & identity logs
5. ⚠️ Incident severity increased
6. 🛑 SOC initiates response

---

## ✅ Final SOC Insight

- 🛡️ **EDR** = Deep endpoint visibility & response
- 📊 **SIEM** = Big-picture detection & correlation
- 🤝 Together they form the backbone of a SOC

🎯 A SOC Analyst must understand **both tools** to investigate incidents effectively.
