# SecurityReview.io API
Smart Contract Security Analysis Platform

#Overview

FastAPI backend for SecurityReview.io - an AI-powered platform that provides fast and affordable security audits for Solidity smart contracts.

**Key Features:**
- Fast analysis (1-2 minutes)
- Affordable pricing ($49-$299 vs $50k audits)
- AI-powered explanations (GPT-4)
- Comprehensive security checks (Slither + custom rules)
- PDF reports with risk scoring
- Stripe payments integration

#Tech Stack

- **Framework:** FastAPI
- **Analysis:** Slither + OpenAI GPT-4
- **Database:** Supabase (PostgreSQL)
- **Payments:** Stripe
- **Deployment:** Railway/Docker

## Project Structure

backend/
├── main.py                 # FastAPI entry point
├── routes/                 # API endpoints
│   ├── analysis.py        # Smart contract analysis
│   ├── auth.py            # Authentication
│   └── health.py          # Health checks
├── services/              # External integrations
│   ├── slither_service.py
│   ├── openai_service.py
│   ├── payment_service.py
│   └── email_service.py
├── models/                # Data models
├── database/              # DB connection
└── utils/                 # Helpers (PDF, JWT, validators)

Quick Start
Prerequisites
Python 3.10+

PostgreSQL (Supabase)

API keys: OpenAI, Stripe

Installation

# Clone repository
git clone https://github.com/yourusername/securityreview-api.git
cd securityreview-api

# Create virtual environment
python3 -m venv venv
source venv/bin/activate  # macOS/Linux
# or: venv\Scripts\activate  # Windows

# Install dependencies
pip install -r requirements.txt

# Create .env file
cp .env.example .env
# Edit .env with your API keys

# Run development server
python main.py

Visit http://localhost:8000/docs for API documentation (Swagger UI)

API Endpoints
Health Check
GET /api/health

Analyze Contract
POST /api/analysis/analyze
Content-Type: application/json

{
  "contract_code": "pragma solidity ^0.8.0; ...",
  "network": "ethereum",
  "email": "user@example.com"
}

Get Report
GET /api/analysis/report/{analysis_id}

Environment Variables
See .env.example for complete list:
  OPENAI_API_KEY - OpenAI API key
  STRIPE_SECRET_KEY - Stripe secret key
  SUPABASE_URL - Supabase project URL
  SUPABASE_KEY - Supabase API key
  SENDGRID_API_KEY - Email service key

Development
Run Tests
pytest
Code Style
  Python 3.10+
  PEP 8
  Type hints recommended

Deployment
Railway
git push
# Automatically deploys on push to main

Docker
docker build -t securityreview-api .
docker run -p 8000:8000 securityreview-api
Contributing
This is a solo project. Feel free to fork and adapt!

License
MIT License - see LICENSE file

Author
Sigayov Stanislav

Status
🚧 MVP in development - Expected completion: Q1 2025

For frontend code, see: securityreview-frontend
