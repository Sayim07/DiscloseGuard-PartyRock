# 🛡️ DiscloseGuard: Responsible Security Triage & Safe-Harbor Liaison

> **GenAI Sprint 1.0 | Track 1: Amazon PartyRock Hackathon**  
> **Team:** CodeX  
> **Team Lead:** Sayim Mullick ([GitHub Profile](https://github.com/Sayim07))  
> **Live PartyRock App:** [Launch DiscloseGuard on AWS PartyRock](https://partyrock.aws/u/smdev/4T2v35MxM/DiscloseGuard%253A-Responsible-Vulnerability-Triage-and-Dis)

---

## 🚀 Project Overview
**DiscloseGuard** is an AI-powered defensive security governance, legal compliance, and campus safety suite built entirely on **Amazon PartyRock**. It automates vulnerability triage and responsible reporting for student researchers and ethical hackers, bridging the gap between discovering security flaws in campus portals and reporting them safely without fear of legal or administrative backlash.

---

## 🔗 Live Application Link
👉 **[Click Here to Access DiscloseGuard on AWS PartyRock](https://partyrock.aws/u/smdev/4T2v35MxM/DiscloseGuard%253A-Responsible-Vulnerability-Triage-and-Dis)**

---

## 🛠️ Tech Stack & Architecture (PartyRock 6-Widget Pipeline)
This application is engineered using an advanced **multi-stage prompt chaining architecture** across 6 interconnected widgets:

1. **`Input_Vulnerability_Data` (User Input):** Captures raw technical vulnerability descriptions (e.g., unauthenticated API endpoints or IDOR/BOLA flaws).
2. **`Input_Target_Org` (User Input):** Captures target organization context (e.g., State University Portal or Student Club Platform).
3. **`Severity_CVSS_Engine` (Claude 3.5 Sonnet / Reasoning LLM):** Chains both inputs to calculate OWASP Risk Ratings and standard CVSS v3.1 base metrics (`Attack Vector`, `Privileges Required`, `Impact Scope`) into a structured markdown scorecard.
4. **`Remediation_Advisor` (Claude 3.5 Sonnet):** Chains inputs and the CVSS scorecard to generate defensive architectural fixes, production-ready Node.js/Express middleware validation code, and NGINX Zero-Trust header guidelines.
5. **`Safe_Harbor_Drafter` (Claude 3.5 Sonnet):** Chains upstream triage and remediation outputs to draft a professional, legally cautious Coordinated Vulnerability Disclosure (CVD) email aligned with **ISO/IEC 29147** and **ISO/IEC 30111** guidelines (enforcing zero extortion tone and strict PII redaction).
6. **`Triage_Report_Card` (PartyRock Image Generation):** Generates an executive security compliance badge and digital defense shield for institutional presentations.

---

## 🧪 Quick Sample Input for Judges (1-Click Testing)
To test the live application on PartyRock, paste the following sample parameters into the top input widgets:

* **`Input_Vulnerability_Data`:**
  
```text
  Unauthenticated GET request to /api/v1/student/semester-marks?reg_no=2026001 exposes internal registration numbers, full marksheets, and phone numbers without checking session authentication tokens.
