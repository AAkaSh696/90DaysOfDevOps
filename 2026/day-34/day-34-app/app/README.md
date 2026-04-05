# Multi-Service Web Application

This is a simple 3-service application consisting of:

- Web Application (Python Flask)
- PostgreSQL Database
- Redis Cache

---

## Application Overview

The web application is built using Flask and exposes a single endpoint:

When accessed, it:
- Connects to PostgreSQL database
- Connects to Redis cache
- Returns connection status

---

## Application Behavior

- The app listens on port `5000`
- It depends on:
  - PostgreSQL for persistent data
  - Redis for caching
- If services are not ready, the app may return temporary connection errors

---


---

## Application Requirements

### Python Dependencies

Defined in `requirements.txt`:

- flask
- psycopg2-binary
- redis

---

## Environment Configuration

The application expects the following services:

### Database (PostgreSQL)

- Host: `db`
- Database Name: `testdb`
- Username: `user`
- Password: `password`

---

### Cache (Redis)

- Host: `redis`
- Port: `6379`

---

## Application Configuration (Important)

Inside the application code:

- Database host is set to: `db`
- Redis host is set to: `redis`

These are expected to be resolved via internal networking (service discovery).

---

## Key Considerations for Containerization

- The application must run on port `5000`
- The database should persist data using a volume
- The cache does not require persistence
- Services must be able to communicate using hostnames:
  - `db`
  - `redis`
- The application should not use `localhost` for external services
- Startup order matters:
  - Database must be ready before the app connects
- Health checks are recommended for database readiness

---

## Expected Behavior
- Once all services are running:
- Accessing the root endpoint should return:
- Database Connected | Hello from Redis
