# Agent Checkout Relay

FastAPI service that converts high-intent agent/user traffic into paid Stripe checkout with minimal friction.

## Core Endpoints
- `POST /api/public/lead` - validate lead + return checkout URL
- `POST /v1/intents` - create machine-readable buying intent
- `POST /v1/intents/{intent_id}/checkout` - choose best-fit checkout path
- `GET /llms.txt` - LLM discovery profile

## Run local
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```

## Stripe
Set `CHECKOUT_LINK_*` environment vars to DataWeave INC Stripe payment links.

## Security defaults
- IP-based rate limits
- Strict security headers
- Input validation
- Minimal PII retention
