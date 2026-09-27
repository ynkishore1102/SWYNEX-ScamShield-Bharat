# ScamShield Bharat - Backend

This folder will contain the backend development of the ScamShield Bharat web application.

## Backend Technology

- Python
- FastAPI
- PostgreSQL
- JWT Authentication
- REST API

## Planned Backend Modules

### Authentication
Handles user registration, login, and authentication.

### Message Analysis
Receives suspicious messages submitted by users and sends them to the risk analysis engine.

### URL Analysis
Processes submitted URLs and checks them for risk indicators.

### Risk Analysis Engine
Detects common fraud-risk indicators and generates an explainable risk score.

### Analysis History
Stores and retrieves previous user analyses.

### Reporting
Allows users to report suspicious digital content.

## Planned API Routes

- POST /api/auth/register
- POST /api/auth/login
- POST /api/analyze/text
- POST /api/analyze/url
- GET /api/analysis/{id}
- GET /api/history
- POST /api/reports
- GET /api/profile

## Database

PostgreSQL will be used to store:

- Users
- Analyses
- Risk Indicators
- Reports
- Fraud Patterns
