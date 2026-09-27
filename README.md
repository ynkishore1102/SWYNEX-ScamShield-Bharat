# ScamShield Bharat

## Digital Fraud Risk Detection and Prevention Platform

ScamShield Bharat is a full-stack web application designed to help users
identify risk indicators in suspicious digital messages and URLs before
taking potentially unsafe actions.

The system analyzes submitted content, identifies common fraud-related
patterns, provides an explainable risk level, and suggests safer next steps.

---

## Problem Statement

Digital users frequently receive suspicious messages, links, fake job
offers, payment requests, phishing messages, and impersonation attempts.

Many users may find it difficult to determine whether such content is
trustworthy before clicking a link, sharing sensitive information, or
making a payment.

ScamShield Bharat aims to provide a simple platform where users can check
suspicious digital content and understand the reasons behind identified
risk indicators.

---

## Core Features

- User Registration and Login
- Suspicious Message Analysis
- URL Analysis
- Explainable Risk Scoring
- Detection of Common Fraud Indicators
- Recommended Safety Actions
- Analysis History
- Suspicious Content Reporting

---

## Technology Stack

### Frontend
- React.js
- HTML
- CSS
- JavaScript

### Backend
- Python
- FastAPI

### Database
- PostgreSQL

### Authentication
- JWT

---

## System Architecture

User
↓
React Frontend
↓
REST API
↓
FastAPI Backend
↓
Risk Analysis Engine
↓
PostgreSQL Database

---

## Data Models

### User
- id
- name
- email
- password_hash
- created_at

### Analysis
- id
- user_id
- input_type
- input_content
- risk_score
- risk_level
- created_at

### RiskIndicator
- id
- analysis_id
- indicator_type
- description
- severity

### Report
- id
- user_id
- analysis_id
- reason
- status
- created_at

### FraudPattern
- id
- pattern_name
- keywords
- category
- severity

---

## API Routes

| Method | Route | Description |
|---|---|---|
| POST | /api/auth/register | Register a user |
| POST | /api/auth/login | Login |
| POST | /api/analyze/text | Analyze suspicious text |
| POST | /api/analyze/url | Analyze a URL |
| GET | /api/analysis/{id} | Get analysis result |
| GET | /api/history | View analysis history |
| POST | /api/reports | Report suspicious content |
| GET | /api/profile | View user profile |

---

## Frontend Screens

1. Landing Page
2. Login / Registration
3. User Dashboard
4. Message Analysis Page
5. URL Analysis Page
6. Risk Result Page
7. Analysis History Page
8. User Profile Page

---

## Future Scope

Future versions can include:

- Screenshot analysis using OCR
- QR code analysis
- Machine learning based fraud detection
- Telugu, Hindi and other Indian language support
- Trusted contact verification
- Fraud relationship analysis
- Browser extension
- Mobile application

---

## Project Status

Task 1 - Project Architecture
