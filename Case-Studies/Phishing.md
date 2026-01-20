# 🎣 Phishing Incident – SOC L1 Case Study

## 📌 Incident Overview
- **Alert Type:** Phishing Email
- **Severity:** Medium
- **Affected User:** Finance Department Employee
- **Detection Source:** Email Security Gateway + SIEM
- **SOC Role:** Level 1 Analyst

---

## 📧 Initial Alert Details
- Suspicious email reported by user
- Email claimed: *“Urgent invoice requires immediate payment”*
- Sender domain visually similar to legitimate supplier
- Embedded hyperlink redirected to external login page

---

## 🔍 Investigation Steps

### 1. Email Analysis
- Checked sender domain reputation
- Observed domain spoofing technique
- Detected mismatched display name vs sender address

### 2. URL Analysis
- URL shortened to hide final destination
- Redirected to fake Microsoft 365 login page
- Domain not owned by Microsoft

### 3. Header Analysis
- SPF: Failed
- DKIM: Failed
- DMARC: Failed

---

## 🧪 Verdict
**True Positive – Phishing Attack**

Indicators confirmed malicious intent:
- Credential harvesting page
- Domain impersonation
- Failed email authentication checks

---

## 🚨 Response Actions

- Alert escalated to SOC L2
- Malicious URL blocked at email gateway
- User credentials reset as precaution
- Awareness notification sent to finance team

---

## 📊 Impact Assessment
- No confirmed credential compromise
- Attack contained within SLA limits
- No lateral movement observed

---

## 🧠 Lessons Learned

- Finance users remain high-value targets
- Domain lookalike attacks are highly effective
- User reporting significantly reduces impact

---

## 🛡️ Recommended Mitigations
- Advanced anti-phishing rules
- Security awareness training
- MFA enforcement for financial systems

---

## ⏱️ KPI Performance (Example)

| Metric | Value |
|-----|------|
| MTTD | 6 minutes |
| MTTA | 8 minutes |
| MTTR | 42 minutes |
| FPR | 0% |

---

> Early user reporting + fast L1 triage prevented credential theft.
