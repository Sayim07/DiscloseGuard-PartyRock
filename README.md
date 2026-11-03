# DiscloseGuard: Responsible Security Triage & Safe-Harbor Liaison

> **GenAI Sprint 1.0 | Track 1: Amazon PartyRock Hackathon**  
> **Team:** CodeX  
> **Team Lead:** Sayim Mullick ([GitHub Profile](https://github.com/Sayim07))

---

## 🚀 Project Overview
**DiscloseGuard** is an AI-powered defensive security governance, legal compliance, and campus safety suite built entirely on Amazon PartyRock. It automates vulnerability triage and responsible reporting for student researchers and ethical hackers, bridging the gap between discovering security flaws in campus portals and reporting them safely without fear of legal or administrative backlash.

---

## 🛠️ Tech Stack & Architecture (PartyRock Multi-Widget Pipeline)
This application is designed using an advanced **multi-stage prompt chaining architecture** across 6 interconnected widgets:
1. **Input_Vulnerability_Data (User Input):** Captures raw technical vulnerability descriptions.
2. **Input_Target_Org (User Input):** Captures target organization context (e.g., State University Portal).
3. **Severity_CVSS_Engine (Reasoning LLM / Claude 3.5):** Calculates OWASP Risk Ratings and CVSS v3.1 base metrics (Attack Vector, Privileges Required, Impact Scope) into a structured markdown scorecard.
4. **Remediation_Advisor (Claude 3.5 Sonnet):** Generates defensive architectural fixes, secure middleware validation code, and zero-trust header guidelines.
5. **Safe_Harbor_Drafter (Claude 3.5 Sonnet):** Drafts a professional, legally cautious Coordinated Vulnerability Disclosure (CVD) email aligned with ISO/IEC 29147 guidelines (with zero extortion tone and strict data redaction).
6. **Triage_Report_Card (Image Generation):** Generates an executive security compliance badge and digital defense shield for presentations.

---

## 🔗 Live Application Link
* [Access DiscloseGuard on AWS PartyRock](PASTE_YOUR_PUBLIC_PARTYROCK_LINK_HERE)

---

## 📂 Workflow & Schema
* The app enforces strict zero-exploit safety guardrails, focusing exclusively on defensive triage, secure coding remediation, and Coordinated Vulnerability Disclosure (CVD) best practices.
