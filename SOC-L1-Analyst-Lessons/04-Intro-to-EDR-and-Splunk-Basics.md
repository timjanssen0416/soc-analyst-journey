# 🛡️ Introduction to EDR (Endpoint Detection & Response)

> 📘 Notes based on the TryHackMe **SOC Level 1 – Introduction to EDR** room.  
> 🎯 Focused on EDR concepts, telemetry, detection techniques, and incident response from a SOC Analyst perspective.

---

## 🎯 Learning Objectives

- 🔍 Understand the fundamentals of EDR and how it works
- 🆚 Differentiate EDR from traditional Antivirus solutions
- 🏗️ Examine the architecture of an EDR solution
- 📊 Analyze the types of telemetry collected from endpoints
- 🚨 Understand detection and response capabilities
- 🧪 Investigate realistic EDR alerts

---

## 💡 What is EDR?

Endpoint Detection and Response (EDR) is a security solution that provides deep visibility and protection for endpoints such as workstations and servers.  
EDR continuously monitors endpoint activity to detect, analyze, and respond to threats in real time.

### 🧰 Common EDR Solutions

- CrowdStrike Falcon
- SentinelOne ActiveEDR
- Microsoft Defender for Endpoint
- OpenEDR
- Symantec EDR

---

## 🧱 The Three Pillars of EDR

### 👁️ 1. Visibility

EDR provides deep visibility into endpoint activity, including:
- 🧩 Process execution trees
- 🗂️ Registry modifications
- 📁 File and directory changes
- 👤 User actions
- 🌐 Network connections

All detections include full contextual timelines, enabling effective threat hunting and forensic analysis.

---

### 🚨 2. Detection

EDR detection capabilities go beyond traditional antivirus by using:
- 🧾 Signature-based detection
- 🧠 Behavioral detection
- 📈 Anomaly detection
- 🤖 Machine learning
- 🕵️ Fileless malware detection
- 🧬 Custom Indicators of Compromise (IOCs)

---

### 🔧 3. Response

EDR allows SOC analysts to take immediate action from a central console, including:
- 🔒 Isolating endpoints
- ✂️ Terminating malicious processes
- 🧼 Quarantining files
- 🖥️ Remote investigation via shell access

---

## 🆚 EDR vs Antivirus

| Attack Stage | Antivirus | EDR |
|-------------|----------|-----|
| 📩 Phishing email delivery | ❌ No detection | ✅ Logs activity |
| 📄 Document execution | ❌ Missed | 👀 Monitored |
| ⚡ Word → PowerShell | ❌ Missed | 🚨 Alert |
| ⬇️ Malware download | ⚠️ Often missed | ✅ Detected |
| 💉 Memory injection | ❌ Invisible | 🚨 Detected |
| 📡 C2 communication | ❌ No visibility | 🚨 Alert |

**🔑 Key Insight:**  
Antivirus relies on known signatures, while EDR detects behavior across the full attack chain.

---

## ⚙️ How EDR Works

### 🛰️ EDR Agent (Sensor)
- Installed on endpoints
- Collects telemetry data
- Sends data to the central console

### 🖥️ EDR Console
- Aggregates telemetry
- Uses analytics and machine learning
- Generates alerts with severity levels

### 🔄 Post-Detection Workflow
1. 🚨 Alert is generated
2. 👨‍💻 SOC Analyst reviews severity
3. 🔍 Investigation of processes and connections
4. 🛑 Response actions applied if confirmed

---

## 📊 EDR Telemetry

EDR collects telemetry such as:
- ⚙️ Process executions
- 🌐 Network connections
- 💻 Command-line activity
- 📁 File and directory changes
- 🗝️ Registry modifications

Telemetry acts as the **black box recorder** of an endpoint.

---

## 🧪 Investigating an EDR Alert (Lab)

**🔎 Findings:**
- ⬇️ Payload downloaded using `curl.exe`
- 📍 Malware path: `C:\Users\Public\install.exe`
- ⚠️ Suspicious binary: `syncsvc.exe`
- 📤 Exfiltration URL: https://files-wetransfer.com/upload/session/ab12cd34ef56/dump_2025.dmp
- ✅ `UpdateAgent.exe` identified as a legitimate internal IT tool

---

## ✅ Key Takeaways

- 👁️ Full attack-chain visibility
- 🧠 Behavioral detection is essential
- ⚡ Rapid response reduces impact
- 🛡️ EDR is a core SOC Analyst tool



# 📊 Splunk: The Basics

> 📘 Notes based on the TryHackMe **SOC Level 1 – Splunk: The Basics** room.  
> 🎯 Focused on Splunk architecture, log ingestion, and security analysis.

---

## 🎯 Learning Objectives

- 🧩 Understand Splunk components
- 🛠️ Explore Splunk functionality
- 📥 Understand log ingestion
- 🔍 Analyze ingested log data

---

## 🏗️ Splunk Architecture

Splunk consists of three main components:

### 🚚 Splunk Forwarder
- Lightweight agent on endpoints
- Sends logs to the Indexer
- Minimal performance impact

**📌 Common Data Sources:**
- 🌐 Web servers
- 🪟 Windows Event Logs
- ⚡ PowerShell & Sysmon
- 🐧 Linux system logs
- 🗄️ Database logs

---

### 📦 Splunk Indexer
- Receives data from forwarders
- Parses and normalizes events
- Stores searchable indexes

---

### 🖥️ Splunk Search Head
- Used by analysts for investigations
- Uses SPL (Search Processing Language)
- Creates dashboards and visualizations

---

## 🧪 Adding Data (Lab Exercise)

**📊 Results:**
- 🗂️ Index created: `VPN_Logs`
- 🔢 Total events: **2862**
- 👤 Events by user *Maleena*: **60**
- 🌍 IP `107.14.182.38` linked to user **Smith**

---

## ✅ Key Takeaways

- 📊 Centralized log visibility
- 🔄 Forwarders collect, Indexers process
- 🔍 Search Heads enable investigations
- 🧠 SPL is a must-have SOC skill



