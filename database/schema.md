# ScamShield Bharat - Database Schema

ScamShield Bharat will use PostgreSQL as its primary database.

## 1. Users Table

| Field | Type | Description |
|---|---|---|
| id | SERIAL | Primary key |
| name | VARCHAR | User name |
| email | VARCHAR | User email |
| password_hash | VARCHAR | Secured password |
| created_at | TIMESTAMP | Account creation time |

## 2. Analyses Table

| Field | Type | Description |
|---|---|---|
| id | SERIAL | Primary key |
| user_id | INTEGER | References user |
| input_type | VARCHAR | Message or URL |
| input_content | TEXT | Submitted content |
| risk_score | INTEGER | Calculated risk score |
| risk_level | VARCHAR | Low, Caution or High |
| created_at | TIMESTAMP | Analysis time |

## 3. Risk Indicators Table

| Field | Type | Description |
|---|---|---|
| id | SERIAL | Primary key |
| analysis_id | INTEGER | References analysis |
| indicator_type | VARCHAR | Type of risk indicator |
| description | TEXT | Explanation |
| severity | VARCHAR | Severity level |

## 4. Reports Table

| Field | Type | Description |
|---|---|---|
| id | SERIAL | Primary key |
| user_id | INTEGER | References user |
| analysis_id | INTEGER | References analysis |
| reason | TEXT | Reason for reporting |
| status | VARCHAR | Report status |
| created_at | TIMESTAMP | Report creation time |

## Database Relationships

User → Analysis

Analysis → Risk Indicators

User → Reports

Analysis → Reports
