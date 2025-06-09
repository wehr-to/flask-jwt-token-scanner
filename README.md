# 🧪 Flask: JWT Auth + API Token Scanner

## Purpose
Simulate a real-world web API that issues and validates JWTs. Includes an internal endpoint to audit, test, and simulate abuse of API tokens.

## Tech Stack
- **Framework**: Flask
- **Security Focus**:
  - JWT validation
  - Insecure token reuse
  - Session security

## OWASP Mapped Protections
- **A07**: Identification & Authentication Failures — Secure login and validation
- **A02**: Cryptographic Failures — Strong JWT signing and checking
- **A10**: SSRF / Authorization Misuse — Audit endpoint for detecting replay and misuse

## Features
- `POST /login` — Issues JWT upon successful login
- `GET /protected` — Requires valid token
- `POST /introspect` — Accepts JWT and performs:
  - Signature verification
  - Expiry check
  - Blacklist check
- Token misuse simulation:
  - Replay attack detection
  - Forged payload rejection
- Admin UI to view and invalidate tokens
- Docker support for deployment

## Getting Started
```bash
# Clone the repo
$ git clone https://github.com/yourusername/flask-jwt-token-scanner.git
$ cd flask-jwt-token-scanner

# Build and run via Docker
$ docker-compose up --build

# Or run locally
$ python3 -m venv venv && source venv/bin/activate
$ pip install -r requirements.txt
$ python run.py
```

## Admin Login
- Default: `admin:admin123` (change in config.py!)

## To Do
- [ ] Add token revocation list backed by Redis or file
- [ ] Add audit logs for failed/forged JWT attempts
- [ ] Write unit tests for all endpoints
- [ ] Add multi-user support and RBAC

## License
MIT
`
