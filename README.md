# 🛡️ ZeroGuard AI — Zero-Day Vulnerabilities Detection

### Detect. Analyze. Fix. Verify. Protect.

**ZeroGuard AI** is an AI-powered cybersecurity project designed to help developers discover potential vulnerabilities, understand security risks, verify remediation, and move toward real-time application protection.

Traditional security tools often stop after reporting a vulnerability. ZeroGuard AI aims to take security further by connecting vulnerability detection with fix verification and runtime monitoring—helping developers understand not only what might be wrong, but also whether the attempted fix addresses the original issue.

> **Our vision:** Build a security system that does more than detect threats—it helps developers verify defenses and improve application resilience against known and emerging attacks.

---

## 🚨 The Problem

Modern applications face security risks from vulnerable code, unsafe configurations, exposed secrets, insecure dependencies, and suspicious runtime activity.

Existing approaches can leave developers with important unanswered questions:

- Is the reported vulnerability a meaningful security risk?
- What changes could fix the issue?
- Does the same security test still fail after remediation?
- Could the fix break legitimate application functionality?
- Can suspicious behavior be detected when an application is running?

ZeroGuard AI is designed around a connected workflow that addresses these challenges.

## 💡 The Solution

ZeroGuard AI combines static code analysis, machine learning-based vulnerability analysis, remediation assistance, and a planned runtime protection workflow.

### Core security workflow

```text
Upload Application Code
          ↓
   Security Scanning
          ↓
 Risk & Evidence Analysis
          ↓
    Fix Suggestions
          ↓
       Apply Fix
          ↓
   Rescan & Regression Test
          ↓
    Verify the Fix
          ↓
   Security Report
```

### Runtime protection vision

```text
Protected Test Application
          ↓
   Runtime Event Monitoring
          ↓
  Detect Suspicious Activity
          ↓
     Generate Alert
          ↓
 Apply Controlled Response
          ↓
   Record & Review Events
```

The goal is to connect pre-deployment security checks with runtime defense in one developer-focused platform.

## ✨ Key Features

### 1. Static Security Analysis
- Integrates Semgrep for rule-based code analysis.
- Identifies potentially unsafe code patterns.
- Supports evidence-driven investigation of security findings.

### 2. AI/ML-Assisted Vulnerability Analysis
- Includes a trained machine learning model for vulnerability classification.
- Supports analysis of code patterns that may indicate security weaknesses.
- Provides a foundation for investigating unusual or previously unrecognized vulnerability patterns.

**Important:** An ML-generated zero-day candidate is a hypothesis, not proof of a new vulnerability or a successful exploit. Findings require validation and responsible security review.

### 3. Security Fix Suggestions
- Provides remediation suggestions for detected issues.
- Helps developers understand potential improvements to vulnerable code.
- Supports a workflow that prioritizes actionable security outcomes.

### 4. Fix Verification
- Designed to connect an original finding with a subsequent security scan.
- Aims to verify whether the original issue remains after remediation.
- Includes regression testing in the planned verification workflow to help protect legitimate functionality.

### 5. Runtime Monitoring and Protection
- Planned monitoring of security events from a protected test application.
- Intended detection of suspicious activity, such as repeated failed login attempts or abnormal request patterns.
- Designed to support real-time alerts, controlled protective actions, and event history.

### 6. Security Dashboard
- Provides a frontend for interacting with the security platform.
- Establishes a foundation for viewing security analysis and application status.
- Designed to bring scan findings, remediation progress, and runtime events into a unified experience.

*The features above describe the project's implemented foundations and intended capabilities. Runtime protection, full fix verification, and other roadmap items should not be considered production-ready until their implementation and tests are confirmed.*

## 🏗️ Technology Stack

| Layer | Technology |
|---|---|
| Frontend | React, Next.js, TypeScript |
| Backend API | Python, FastAPI |
| Static Analysis | Semgrep |
| Machine Learning | Python, Scikit-learn, Joblib |
| API Communication | HTTP APIs |
| Model Artifact | `primevul_baseline.joblib` |
| Development | Git, GitHub, Visual Studio Code |

**Architecture overview**

```text
Developer
    │
    ▼
Frontend Dashboard
    │
    ▼
FastAPI Backend
    │
    ├── Security Scanning
    │      └── Semgrep
    │
    ├── Fix Suggestions
    │
    ├── ML Vulnerability Analysis
    │      └── Trained Model
    │
    └── Future Verification & Runtime Protection
```

## 📂 Project Structure

```text
zeroguard-ai/
├── backend/
│   ├── main.py
│   ├── semgrep_scanner.py
│   ├── fix_suggestions.py
│   ├── requirements.txt
│   └── scan test files
│
├── frontend/
│   ├── app/
│   ├── components/
│   ├── services/
│   ├── public/
│   ├── package.json
│   └── .env.example
│
├── ml/
│   ├── models/
│   │   └── primevul_baseline.joblib
│   ├── load_dataset.py
│   ├── check_dataset.py
│   ├── train_model.py
│   ├── evaluate_model.py
│   └── tune_threshold.py
│
├── .gitignore
└── README.md
```

## ⚙️ Quick Start — Local Development

### Prerequisites

- Python installed
- Node.js and npm installed
- Git installed
- Visual Studio Code or another code editor

### 1. Clone the Repository

```bash
git clone https://github.com/Hackfest-X-Saividya/codenexus-t2-06.git
cd codenexus-t2-06
```

### 2. Start the Backend

Open PowerShell in the repository root:

```powershell
cd backend

python -m venv .venv
.\.venv\Scripts\Activate.ps1

python -m pip install --upgrade pip
pip install -r requirements.txt

uvicorn main:app --reload --port 8000
```

Backend API:

- Health and API endpoints: `http://127.0.0.1:8000`
- Interactive API documentation: `http://127.0.0.1:8000/docs`

**Setup note:** The current scanner references a local Semgrep executable path. You may need to configure the scanner for your local installation before security scans will run successfully.

### 3. Start the Frontend

Open a second PowerShell terminal from the repository root:

```powershell
cd frontend
npm install
npm run dev
```

Open the local URL displayed in the terminal, typically:

`http://localhost:3000`

If the frontend requires a backend URL, create a local `.env` file based on `frontend/.env.example` and use the variable expected by the application.

### 4. Machine Learning

The `ml/` directory contains scripts for dataset checks, training, evaluation, and threshold tuning.

The trained model is included at:

`ml/models/primevul_baseline.joblib`

The training dataset is not included in the repository because of its size. Configure the required dataset and paths before running the training scripts.

## 🧪 Testing and Validation

Security software must be validated before its results can be trusted.

The project's validation goals include:

- [ ] Verify backend health and API responses.
- [ ] Run Semgrep against controlled vulnerable and safe code samples.
- [ ] Validate ML inference using the compatible model pipeline.
- [ ] Confirm that findings contain useful evidence.
- [ ] Verify that remediation resolves the original finding.
- [ ] Test legitimate application behavior after a fix.
- [ ] Validate runtime alerts against controlled suspicious activity.
- [ ] Confirm protective actions do not unnecessarily block legitimate users.

Test counts and coverage should be reported after the corresponding automated test suites have been run and verified.

## 🔭 Future Roadmap

- [ ] Expand vulnerability detection and finding correlation.
- [ ] Improve ML-assisted identification of suspicious code patterns.
- [ ] Build a complete scan-to-fix verification pipeline.
- [ ] Add regression tests for remediation validation.
- [ ] Develop runtime event monitoring and real-time alerts.
- [ ] Demonstrate controlled protective actions against suspicious requests.
- [ ] Add security reports and scan history.
- [ ] Strengthen automated tests and deployment readiness.

## 🔐 Responsible Security and Zero-Day Disclaimer

ZeroGuard AI is intended for defensive cybersecurity, authorized code analysis, and controlled security testing.

- Static analysis and ML predictions may produce false positives or miss vulnerabilities.
- A suspected zero-day requires independent validation before it can be considered a confirmed vulnerability.
- Suggested fixes must be reviewed and tested before deployment.
- Runtime protective actions should be tested in controlled environments before production use.
- Do not scan systems without authorization or commit credentials and secrets to the repository.

**AI-assisted detection is not a guarantee of zero-day prevention.** The objective is to make vulnerabilities easier to investigate, fixes easier to verify, and application defenses more reliable.

## 👥 Team

**Team Name:** Codenexus  
**Project:** ZeroGuard AI — Zero-Day Vulnerabilities Detection  
**Hackathon:** HACKFEST 2026 — Secure Sphere

---

### Our Mission

**Move beyond finding vulnerabilities. Help developers verify their fixes and build applications that are better prepared for emerging threats.**
