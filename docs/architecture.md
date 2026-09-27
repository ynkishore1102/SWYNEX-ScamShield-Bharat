# ScamShield Bharat - Project Architecture

## Task 1: Full-Stack Application Architecture

**Project Name:** ScamShield Bharat  
**Domain:** Cybersecurity / Full-Stack Web Development  
**Project Type:** Web Application  

---

## 1. Product Idea

ScamShield Bharat is a full-stack web application designed to help users
check suspicious digital messages and URLs before taking potentially unsafe
actions.

Users can paste a suspicious message or URL into the application. The
system analyzes the submitted content for common fraud-risk indicators and
provides an understandable risk assessment.

Instead of simply saying whether something is a scam or not, the platform
explains the warning indicators that were detected and suggests safer next
steps.

---

## 2. Problem Statement

Digital users frequently receive suspicious messages, phishing links,
fake job offers, payment requests and impersonation attempts.

Many users may find it difficult to understand whether such content is
trustworthy before clicking a link, sharing sensitive information or
making a payment.

ScamShield Bharat aims to provide a simple software platform that helps
users identify warning indicators before taking potentially unsafe digital
actions.

---

## 3. Core Features

- User Registration and Login
- Suspicious Message Analysis
- Suspicious URL Analysis
- Explainable Risk Scoring
- Detection of Fraud Risk Indicators
- Recommended Safety Actions
- Analysis History
- Suspicious Content Reporting

---

## 4. Data Models

### User

| Field | Type | Description |
|---|---|---|
| id | Integer | Unique user ID |
| name | String | User name |
| email | String | User email |
| password_hash | String | Secured password |
| created_at | DateTime | Account creation time |

### Analysis

| Field | Type | Description |
|---|---|---|
| id | Integer | Unique analysis ID |
| user_id | Integer | User who submitted the content |
| input_type | String | Message or URL |
| input_content | Text | Submitted content |
| risk_score | Integer | Calculated risk score |
| risk_level | String | Low, Caution or High |
| created_at | DateTime | Analysis time |

### RiskIndicator

| Field | Type | Description |
|---|---|---|
| id | Integer | Indicator ID |
| analysis_id | Integer | Related analysis |
| indicator_type | String | Type of warning |
| description | Text | Explanation of warning |
| severity | String | Severity level |

### Report

| Field | Type | Description |
|---|---|---|
| id | Integer | Report ID |
| user_id | Integer | Reporting user |
| analysis_id | Integer | Related analysis |
| reason | Text | Reason for report |
| status | String | Report status |
| created_at | DateTime | Report creation time |

---

## 5. API Routes

| Method | API Route | Purpose |
|---|---|---|
| POST | /api/auth/register | Register new user |
| POST | /api/auth/login | Login user |
| POST | /api/analyze/text | Analyze suspicious message |
| POST | /api/analyze/url | Analyze suspicious URL |
| GET | /api/analysis/{id} | View particular analysis |
| GET | /api/history | View previous analyses |
| POST | /api/reports | Report suspicious content |
| GET | /api/profile | View user profile |

---

## 6. Frontend Screens

### Landing Page
Introduces ScamShield Bharat and provides an option to start checking
suspicious content.

### Login / Registration Page
Allows users to create an account and login.

### Dashboard
Provides options for message analysis, URL analysis and viewing recent
checks.

### Message Analysis Page
Allows the user to paste a suspicious message for analysis.

### URL Analysis Page
Allows the user to enter a suspicious URL for analysis.

### Analysis Result Page
Displays the risk level, detected indicators, explanation and recommended
action.

### History Page
Displays the user's previous analyses.

### Profile Page
Displays basic user account information.

---

## 7. Risk Analysis

The first version uses simple and explainable rule-based risk indicators.

Example indicators include:

- Urgent payment requests
- OTP or PIN requests
- Suspicious URLs
- Recruitment payment requests
- Threatening language
- Impersonation indicators
- Identity mismatch

Example risk levels:

| Risk Score | Risk Level |
|---|---|
| 0-29 | Low |
| 30-59 | Caution |
| 60-100 | High |

The score represents detected risk indicators and should not be treated as
a guarantee that submitted content is fraudulent or safe.

---

## 8. System Architecture

```text
                    USER
                      |
                      v
              REACT FRONTEND
                      |
                      v
                  REST API
                      |
                      v
               FASTAPI BACKEND
                      |
             +--------+--------+
             |                 |
             v                 v
      AUTHENTICATION      RISK ANALYSIS
                              ENGINE
             |                 |
             +--------+--------+
                      |
                      v
               POSTGRESQL
                 DATABASE

**9. Application Flow**
User
 |
 v
Register / Login
 |
 v
Dashboard
 |
 +-------------------+
 |                   |
 v                   v
Message Check     URL Check
 |                   |
 +---------+---------+
           |
           v
      Risk Analysis
           |
           v
    Risk Indicators
           |
           v
   Explainable Result
           |
           v
 Recommended Action
           |
           v
   Save to History


10. Technology Stack
Frontend
- React.js
- HTML
- CSS
- JavaScript
Backend
- Python
- FastAPI
Database
- PostgreSQL
Authentication
- JWT
Development Tools
- Git
- GitHub
- VS Code

11. Future Scope
Future versions can include:
- Screenshot analysis using OCR
- QR code analysis
- Machine-learning-based risk classification
- Telugu and Hindi language support
- Trusted contact verification
- Fraud relationship analysis
- Browser extension
- Mobile application

12. Conclusion
ScamShield Bharat provides a simple and explainable approach for helping
users evaluate suspicious digital content.
The proposed architecture separates the frontend, backend, risk-analysis
logic and database so that the application can be developed and expanded
in a structured manner.
