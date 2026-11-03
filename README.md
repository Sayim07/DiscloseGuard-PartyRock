<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:A100C0,50:5B4FB0,100:00A8A8&height=220&section=header&text=DiscloseGuard&fontSize=64&fontColor=9AE62F&animation=fadeIn&fontAlignY=38&desc=Responsible%20Security%20Triage%20%26%20Safe-Harbor%20Liaison&descSize=20&descColor=ffffff&descAlignY=58" alt="DiscloseGuard banner" width="100%" />

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&pause=1200&color=2DD4BF&center=true&vCenter=true&width=760&lines=CVSS+v3.1+%2B+OWASP+Risk+Scorecards;Zero-Trust+Code+Remediation;ISO%2FIEC+29147+Safe-Harbor+Disclosure+Emails;Built+with+6+Chained+Widgets+on+Amazon+PartyRock" alt="Typing animation" />

<br/>

![GenAI Sprint](https://img.shields.io/badge/GENAI%20SPRINT-1.0-0078D4?style=for-the-badge)
![Platform](https://img.shields.io/badge/PLATFORM-AMAZON%20PARTYROCK-F28A30?style=for-the-badge)
![AI Engine](https://img.shields.io/badge/AI%20ENGINE-CLAUDE%203.5%20SONNET-8A1CB8?style=for-the-badge)
![Compliance](https://img.shields.io/badge/COMPLIANCE-ISO%2FIEC%2029147-6CC24A?style=for-the-badge)

### 🚀 [Launch Live DiscloseGuard App on AWS PartyRock][app] 🚀

</div>

---

## 📌 Overview

**DiscloseGuard** is an AI-powered **defensive** cybersecurity governance, legal compliance, and campus/EdTech safety suite, built entirely on **Amazon PartyRock** using multi-stage prompt chaining across 6 connected widgets.

A student pastes a raw vulnerability description and the target organization type. In one click, the app produces:

1. a formal **CVSS v3.1 + OWASP Risk Rating** scorecard,
2. **production-ready defensive code fixes** (Express middleware, NGINX zero-trust headers, P0–P2 roadmap),
3. a **legally safe ISO/IEC 29147 disclosure email**, and
4. a **visual compliance badge** for executive presentation.

> ⚠️ DiscloseGuard never scans, tests, or attacks any website. It only processes text that the user provides, and it is designed to never generate exploit payloads.

---

## 🎯 Problem Statement

**The Campus & EdTech Vulnerability Paradox**

| # | Problem | Impact |
|---|---------|--------|
| 1 | **Critical campus ERP exposures** — university portals and club platforms often suffer from broken access controls (IDOR/BOLA) and unauthenticated APIs. | Predictable registration numbers can expose thousands of marksheets and phone numbers. |
| 2 | **Legal & disciplinary fear gap** — poorly worded reports sound threatening or extortionate to non-technical administration. | Student researchers face disciplinary action instead of appreciation. |
| 3 | **Slow, ad-hoc patching** — developers get vague reports with no severity score and no actionable fix. | No standard P0 vs. P2 prioritization; no drop-in middleware code. |

**The core need:** a *zero-exploit* defensive triage and safe-harbor bridge that turns raw technical findings into scorecards, code patches, and legally protected disclosure emails.

---

## 🧩 Solution & Pipeline Architecture

```text
 TIER 1: USER INPUTS            TIER 2: CORE TRIAGE                TIER 3: DOWNSTREAM GENERATORS
┌──────────────────────────┐   ┌──────────────────────────┐
│ [1] Input_Vulnerability  │──▶│ [3] Severity_CVSS_Engine │──┬──▶ [4] Remediation_Advisor
│     _Data                │   │  CVSS v3.1 + OWASP Risk  │  │         │
├──────────────────────────┤   └──────────────────────────┘  │         ▼
│ [2] Input_Target_Org     │──────────────────────────────────┼──▶ [5] Safe_Harbor_Drafter
└──────────────────────────┘                                  │
        │                                                     │
        └─────────────────────────────────────────────────────┴──▶ [6] Triage_Report_Card (Image Gen)
```

### Widget Breakdown

| # | Widget | Type | Chains | Output |
|---|--------|------|--------|--------|
| 1 | `Input_Vulnerability_Data` | User Input | — | Raw API / endpoint bug description |
| 2 | `Input_Target_Org` | User Input | — | University / EdTech ERP context |
| 3 | `Severity_CVSS_Engine` | Text Generation (Claude Sonnet) | 1 + 2 | CVSS v3.1 base score, vector string, 8-metric rationale table, OWASP Risk Rating matrix |
| 4 | `Remediation_Advisor` | Text Generation (Claude Sonnet) | 1 + 2 + 3 | Root cause, Node.js JWT/BOLA middleware, NGINX zero-trust headers, P0–P2 action plan |
| 5 | `Safe_Harbor_Drafter` | Text Generation (Claude Sonnet) | 1 + 2 + 3 + 4 | ISO/IEC 29147 & 30111 aligned CVD email with redacted PII and zero-extortion tone |
| 6 | `Triage_Report_Card` | Image Generation | 1 + 2 | Executive cyber-defense shield and compliance badge |

**Why chaining matters:** the output of `Severity_CVSS_Engine` feeds directly into `Remediation_Advisor` and `Safe_Harbor_Drafter`, so the score, fix priorities, and email always stay consistent with each other.

---

## 🧪 Live Demo — Sample Test Case

**`Input_Vulnerability_Data`**
```text
Unauthenticated GET request to /api/v1/student/semester-marks?reg_no=2026001 exposes internal registration numbers, full marksheets, and phone numbers without checking session authentication tokens.
```

**`Input_Target_Org`**
```text
State University Portal (Academic Examination & Attendance ERP).
```

### Output 1 — Risk Scorecard (`Severity_CVSS_Engine`)

**Severity: 🔴 HIGH (7.5 / 10)**
Vector: `CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:N`

| CVSS v3.1 Metric | Value | AI Triage Rationale |
|---|---|---|
| Attack Vector (AV) | Network (N) | Reachable remotely over HTTP(S) without network restrictions. |
| Attack Complexity (AC) | Low (L) | Direct crafted GET request suffices; no special timing required. |
| Privileges Required (PR) | None (N) | No session token, cookie, or auth header validated server-side. |
| User Interaction (UI) | None (N) | Exploitation requires zero action from any legitimate user. |
| Scope (S) | Unchanged (U) | Vulnerable ERP component itself is compromised directly. |
| Confidentiality (C) | High (H) | Full exposure of student PII, registration numbers & marksheets. |
| Integrity (I) | None (N) | Read-only GET endpoint; no data modification capability. |
| Availability (A) | None (N) | No resource exhaustion or denial-of-service impact observed. |

**Classification:** OWASP API1:2023 — Broken Object Level Authorization (BOLA / IDOR) and OWASP API2:2023 — Broken Authentication.
**OWASP Risk Rating:** Threat Agent, Vulnerability, Technical Impact and Business Impact are all rated **HIGH**.

### Output 2 — Defensive Remediation (`Remediation_Advisor`)

```javascript
// 1. Cryptographic JWT + Redis Session Verification
const decoded = jwt.verify(token, JWT_SECRET, {
  algorithms: ['RS256'], issuer: JWT_ISSUER, audience: JWT_AUDIENCE
});
const session = await getSession(decoded.sid);
if (!session || session.revoked) return res.status(401).json({ error: 'Invalid' });

// 2. Object-Level Authorization (Prevent IDOR/BOLA)
function authorizeStudentRecordAccess(req, res, next) {
  const requestedRegNo = req.query.reg_no;
  const { regNo: sessionRegNo, roles } = req.auth;
  if (!roles.includes('registrar') && requestedRegNo !== sessionRegNo) {
    logSecurityEvent('IDOR_ATTEMPT', { user: req.auth.userId, requestedRegNo });
    return res.status(403).json({ error: 'Forbidden: record access denied' });
  }
  req.authorizedRegNo = sessionRegNo; // Never trust client input
  next();
}
// 3. Field-Level PII Masking: phone.replace(/\d(?=\d{4})/g, 'X')
```

```nginx
add_header Strict-Transport-Security "max-age=63072000; preload" always;
add_header Cache-Control "no-store, no-cache, private" always;
add_header X-Content-Type-Options "nosniff" always;
add_header Content-Security-Policy "default-src 'none';" always;
# Plus 30s RS256 X-Internal-Assertion JWT for microservice mTLS
```

**Prioritized roadmap**
- **P0 (Immediate):** Enforce `authenticate` + `authorizeStudentRecordAccess` middleware and resolve `reg_no` strictly from the server session.
- **P1 (High):** Deploy an API Gateway auth gate, rate limiting (10 req/min), and SIEM alerting on repeated 403 IDOR denials.
- **P2 (Medium):** Migrate sequential `reg_no` parameters to opaque UUIDs and audit sibling ERP modules (attendance, fees, hostel).

### Output 3 — Safe-Harbor Disclosure Email (`Safe_Harbor_Drafter`)

> **Subject:** Responsible Security Disclosure — Unauthenticated Access to Student Records via `/api/v1/student/semester-marks` (State University Portal ERP)

- **Good-faith & zero-extortion clause** — states the report is submitted solely to help remediate, that no data was exfiltrated or retained, and that no payment or compensation is requested.
- **Non-exploitative reproduction steps** — describes standard GET behavior and the missing 401/403 responses, with no weaponized PoC scripts and no real student PII.
- **Structured CVD timeline** — requests acknowledgment within 7 business days and proposes a 30–90 day mutually agreed remediation window before any public write-up.

### Output 4 — Compliance Badge (`Triage_Report_Card`)

An AI-generated executive security badge for CISO / Dean presentations, signalling that the vulnerability was triaged under ethical CVD governance.

---

## 🆚 Why DiscloseGuard vs. Raw ChatGPT / Claude / Gemini?

| Raw chatbot | DiscloseGuard (PartyRock 6-widget pipeline) |
|---|---|
| **Domain knowledge bottleneck** — a student must already know CVSS vector notation, OWASP API taxonomy and ISO/IEC 29147 to prompt for them. | **Zero-prompt domain expertise** — pre-engineered personas enforce OWASP, CVSS v3.1 and ISO/IEC 29147 & 30111. |
| **Single-prompt context dilution** — scoring, code, legal drafting and badge generation in one chat dilutes quality. | **Multi-stage prompt chaining** — each widget has one job; outputs feed forward for consistency. |
| **Safety refusals & ambiguity** — raw security prompts can trigger false refusals or produce unsafe PoC scripts. | **Strict defensive guardrails** — redacts PII, forbids exploit payloads, enforces calm non-extortionate language. |
| **Blank-canvas friction** — manual multi-turn prompting every time. | **Parallel executive dashboard** — risk tables, code, email and badge in one click. |

---

## 🔒 Ethical Guardrails

- ❌ No exploit payloads or weaponized proof-of-concept scripts
- ❌ No scanning or interaction with live systems — text-in, text-out only
- ✅ PII is redacted in generated reports
- ✅ Calm, good-faith, non-extortionate legal language
- ✅ Aligned with ISO/IEC 29147 (Vulnerability Disclosure) and ISO/IEC 30111 (Vulnerability Handling)

---

## ⚙️ How to Use

1. Open the [live app][app] (no account needed to view).
2. Describe the vulnerability in `Input_Vulnerability_Data` (sample is pre-filled).
3. Enter the organization type in `Input_Target_Org`.
4. Read the scorecard, remediation plan, disclosure email, and badge generated below.

**Remix it:** click **Remix** on the [app page][app] to clone it into your own PartyRock account and customize the prompts.

---

## 🗺️ Future Roadmap (Phase 2)

- **Multi-stack remediation:** toggle for Python (FastAPI/Django), Java (Spring Boot) and Go middleware fixes.
- **CERT-In & institutional templates:** pre-configured compliance templates for Indian CERT-In disclosure norms.
- **Interactive Security Mentor Chat:** post-triage Q&A widget for developers.

---

## 🌍 Real-World Impact

- **Campus & university ERPs:** helps student security clubs and GDG chapters audit exam, attendance and hostel portals safely, and gives registrars and IT admins clear P0–P2 checklists without costly external consultants.
- **EdTech & startups:** early-stage teams without AppSec engineers get instant Express/NGINX patches and CVSS v3.1 tables for compliance audits.

---

## 👨‍💻 Developer Profile & Project Metadata

- **Developer / Team Lead:** Sayim Mullick — B.Tech IT/CSE ([GitHub Profile](https://github.com/Sayim07))
- **Contact:** sayimmullick2005@gmail.com
- **Event:** GenAI Sprint 1.0 | Track 1: Amazon PartyRock (AWS Student Builder Group, JIS University)
- **Team Name:** CodeX
- **AI Models:** Claude Sonnet (reasoning & code) + PartyRock Image Generation
- **Core Theme:** Cybersecurity Governance, DevSecOps & Legal Safe-Harbor Compliance

---

## ⚠️ Disclaimer

DiscloseGuard is a decision-support and drafting tool. AI-generated scores, code and legal drafts should be reviewed by qualified security and legal professionals before real-world use. It is not legal advice.

<div align="center">

**Built with ❤️ by Team CodeX on Amazon PartyRock**

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00A8A8,50:5B4FB0,100:A100C0&height=100&section=footer" alt="footer" width="100%" />

</div>

<!-- Single place to update the PartyRock link. All "app" links above use this line. -->
[app]: https://partyrock.aws/u/smdev/4T2v35MxM
