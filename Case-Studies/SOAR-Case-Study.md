# 📖 SOAR Case Study: Automating Phishing Incident Response

This case study demonstrates the transition from a **Manual Response** to an **Automated SOAR Workflow**, highlighting the efficiency gains in a modern SOC environment.

---

## 🚩 The Problem: "The Phishing Deluge"
In a traditional SOC setting, an analyst receives 50+ suspicious email alerts daily. 

**The Manual Workflow (Before SOAR):**
1. 📧 **Receive Alert:** Analyst opens the ticket.
2. 🔍 **Inspection:** Manually extract headers, URLs, and attachments.
3. 🌐 **Reputation Check:** Copy-paste URLs into VirusTotal or URLScan.io.
4. 📂 **Sandbox Testing:** Upload attachments to a malware sandbox.
5. 🛡️ **Remediation:** If malicious, manually log into the Email Gateway to delete the mail and into the Firewall to block the IP.
6. 📝 **Reporting:** Manually document every step in the ticketing system.

**Total Time per Incident:** ~30 to 45 minutes.

---

## ⚡ The Solution: The SOAR Phishing Playbook
By implementing a SOAR Playbook, the organization automates the "low-brain" repetitive tasks, allowing the analyst to focus only on the final verdict.



### 🛠️ The Automated Workflow (With SOAR):
* **Step 1: Trigger** 🟢
  * The SIEM detects a suspicious email and sends the metadata to the SOAR.
* **Step 2: Automated Enrichment** 🤖
  * SOAR automatically queries **Threat Intelligence feeds** (e.g., AbuseIPDB, VirusTotal).
  * It checks if the sender's domain was recently registered (a common red flag).
* **Step 3: Internal Context** 🏢
  * SOAR checks if other employees received the same email.
* **Step 4: Containment (Conditional)** 🔒
  * **IF** the URL is 100% confirmed malicious:
    * Automatically delete the email from all user inboxes.
    * Block the source IP on the corporate Firewall.
    * Disable the user's account if they clicked the link (via IAM).
* **Step 5: Analyst Review** 👨‍💻
  * The analyst receives a "Cleaned" ticket with all evidence attached. They only need to perform a final 2-minute review.

**Total Time per Incident:** < 5 minutes.

---

## 📈 Business Impact & Key Metrics

| Metric | Manual Process | SOAR Automated | Improvement |
| :--- | :--- | :--- | :--- |
| **MTTD** (Mean Time to Detect) | 10 Minutes | Instant | 100% |
| **MTTR** (Mean Time to Respond) | 45 Minutes | 3 Minutes | ~93% |
| **Analyst Capacity** | ~15 alerts / day | 100+ alerts / day | 6x Increase |

---

## 🎓 Conclusion
This Case Study proves that SOAR is not just a "nice-to-have" tool but a necessity for scaling security operations. It eliminates **Alert Fatigue** and ensures that critical phishing threats are neutralized in minutes, not hours.

---
*Prepared as part of my Security Operations Center (SOC) specialization.*
