# 🎓 AssociationHub — NK Orchid College of Engineering & Technology (NKOCET)

> **Enterprise Full-Stack Collegiate Engagement & Digital Access Control Gateway**  
> *Developed for N.K. Orchid College of Engineering & Technology, Solapur (Autonomous Institute)*

[![FastAPI](https://img.shields.io/badge/FastAPI-0.110+-009688.svg?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg?logo=python&logoColor=white)](https://www.python.org/)
[![SQLite3](https://img.shields.io/badge/SQLite-Ledger_Ready-003B57.svg?logo=sqlite&logoColor=white)](https://www.sqlite.org/)
[![Status](https://img.shields.io/badge/Audit_Status-100%25_Green-brightgreen.svg)]()

---

## 🚀 Overview

**AssociationHub** is an enterprise-grade collegiate engagement platform and digital access control gateway built for **N.K. Orchid College of Engineering & Technology (NKOCET)**. It unifies all 6 engineering departments under a secure cryptographic system, providing junior students with interactive orientation pathways, verified digital membership passes with 3D smart-card flipping, real-time Gmail OTP identity verification, collegiate event calendars, and public gate check-in terminals.

---

## 🌟 Core System Modules

1. **Digital Membership Pass Generator (`/api/memberships`)**:
   - Issues verified digital passes with unique IDs (e.g. `NKOCET-2026-CSESA-A1B2C3`).
   - Generates dynamic, high-density Base64 QR codes signed with HMAC-SHA256 cryptographic hashes.
   - Interactive 3D flip card (front credentials, hologram, and back constitution/emergency contacts).
   - 1-click Print, PDF download, and local device persistence (`localStorage`).

2. **Gate Access Control & Live Camera Scanner (`/verify.html`)**:
   - Real-time verification terminal for campus security, event gates, and lab access.
   - **Interactive Live Camera Scanner**: Auto-detects QR passes in real time at 60 fps via native `BarcodeDetector` / `getUserMedia`.
   - **QR Image Uploader**: Drag-and-drop or upload pass screenshots for instant verification.
   - Audio feedback (synthesized Web Audio chimes for verified, alert, and check-in celebration).
   - Gatekeeper check-in logging (`gate_checkins` table in SQLite).

3. **Master Admin Console Suite (`PIN: admin2026`)**:
   - **Member Directory**: Search, filter by association, activate, suspend, or revoke passes.
   - **Revoke & Delete Pass**: Permanent SQLite record purge, device cache clearing, and restriction logging with Admin PIN modal.
   - **Campus Events Calendar**: Publish and delete hackathons, robotics challenges, and technical workshops across departments.
   - **Executive Analytics**: Real-time KPI telemetry (Registered Members, Gate Check-Ins, Discussions, Active Events, Ledger Health) and dynamic enrollment charts.
   - **Rejoin Approvals Queue**: Automated gateway preventing blocked/removed students from rejoining without explicit admin authorization.
   - **Security Audit Logs**: Timestamped ledger tracking all registrations, status changes, and troll violations.
   - **Real SMTP Gateway**: Configure Google App Passwords and send test emails directly from the UI.
   - **1-Click CSV Exports**: Download HOD & NAAC compliance reports for students and active members.

4. **Campus Pulse Community Chat (`#community`)**:
   - Gated student discussion boards gated by Gmail OTP verification.
   - Upvotes ("Helpful"), threaded replies, and anonymous publishing mode.
   - **Campus Anti-Troll Shield**: Blocks profanity, toxic keywords, external scam links, and repetitive character floods.
   - Admin post unmasking and moderation deletion.

---

## 🎨 Department Color Identities

| Association | Engineering Department | Primary Accent |
| :--- | :--- | :--- |
| **CSESA** | Computer Science & Engineering | **Cyber Blue (`#1687FF`)** |
| **MESA** | Mechanical Engineering | **Industrial Orange (`#FF8A24`)** |
| **EESA** | Electrical Engineering | **Electric Emerald (`#19D68C`)** |
| **CESA** | Civil Engineering | **Architectural Violet (`#A855F7`)** |
| **AEXS** | Electronics & Telecommunication | **Signal Crimson (`#FF416C`)** |
| **AIESA** | AI & Data Science | **Neural Cyan (`#00D9E8`)** |

---

## 📂 Repository File Tree

```text
nkocet-website/
├── index.html                  # Main Portal Homepage with Live Telemetry & Modals
├── verify.html                 # Gate Verification Portal with Live Camera & QR Scanner
├── aids.html                   # AI & Data Science Association (AIESA) Sub-Portal
├── civil.html                  # Civil Engineering Association (CESA) Sub-Portal
├── entc.html                   # Electronics & Telecom Association (AEXS) Sub-Portal
├── esa.html                    # Electrical Engineering Association (EESA) Sub-Portal
├── cep-cesa.html               # Computer Science Association (CSESA) Sub-Portal
├── cep-mesa.html               # Mechanical Engineering Association (MESA) Sub-Portal
├── cep-about us.html           # Project Vision, Academic Background & Team Dossier
│
├── css.css                     # Unified Dark Theme Glassmorphism Design System
├── main.js                     # Full-Stack Client Engine & Admin Suite
├── server.py                   # FastAPI Enterprise Backend (48 Endpoints)
├── associationhub.db           # SQLite Cryptographic Ledger (Auto-generated on startup)
│
├── tools/
│   ├── audit_project.py        # Automated Codebase & Database Architectural Auditor
│   ├── test_backend.py         # End-to-End API & Integration Regression Suite
│   └── seed_passes.py          # Demo Passes & Student Data Seeder
│
├── .env.example                # Template for Real Gmail SMTP Configuration
├── .gitignore                  # GitHub Exclusion Rules (Protects passwords & temp files)
├── requirements.txt            # Python Package Dependencies
└── README.md                   # Complete System Documentation
```

---

## ⚡ Quick Start & Local Setup

### 1. Prerequisites
- Python 3.10+ installed
- Modern web browser (Chrome, Edge, Firefox, Safari)

### 2. Clone Repository
```bash
git clone https://github.com/your-username/nkocet-website.git
cd nkocet-website
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure Environment (Optional for Real Gmail OTP)
Copy the example environment configuration:
```bash
cp .env.example .env
```
Fill in your Google App Password if you wish to send live emails to students, or configure it later inside the **Admin Suite** (`PIN: admin2026`).

### 5. Launch Full-Stack Server
```bash
python server.py 8080
```

### 6. Access Portal
- **Main Portal**: [http://127.0.0.1:8080](http://127.0.0.1:8080)
- **Gate Check-In & Scanner**: [http://127.0.0.1:8080/verify.html](http://127.0.0.1:8080/verify.html)
- **Interactive OpenAPI Docs**: [http://127.0.0.1:8080/docs](http://127.0.0.1:8080/docs)
- **Master Admin PIN**: `admin2026`

---

## 🧪 Automated Testing & Verification

Run the built-in audit and regression suites anytime:

```bash
# Run deep architectural audit
python tools/audit_project.py

# Run full-stack regression suite
python tools/test_backend.py
```

---

## 👥 Project Team & Authors

Developed as part of the **College Engagement Project (CEP)**, 2nd Year B.Tech, NKOCET Solapur:

* **Affan Choudhari** — Project Lead & Backend Systems Architect (Roll: C-62)
* **Suyash Gote** — UI/UX Lead & Design Systems Engineer (Roll: C-64)
* **Umair Shaikh** — Research & Association Documentation Lead (Roll: C-54)
* **Moin Shaikh** — Systems & Infrastructure Lead (Roll: C-67)
* **Sushil Habib** — Verification & Quality Assurance (Roll: C-58)
* **Siddeshwar Nagansure** — Technical Documentation (Roll: C-61)

---

## 📄 License

This project is developed for academic, collegiate, and access control purposes at **N.K. Orchid College of Engineering & Technology (NKOCET)**, Solapur.
