---
name: postgresql-basic-setup
description: Install and configure PostgreSQL database server with basic user and database creation
version: 1.0.0
metadata:
  skill_forge:
    domain: "postgresql"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [postgresql, database, sql, setup]
    category: database
---

# PostgreSQL Basic Setup

## When to Use
When you need to install and configure PostgreSQL for development or production use, create databases, and set up user access.

## Prerequisites
- Administrative access to the system
- Package manager (apt, yum, brew) or Windows installer access
- Basic command line familiarity

## Procedure
1. Install PostgreSQL: `sudo apt update && sudo apt install postgresql postgresql-contrib` (Ubuntu/Debian)
2. Start PostgreSQL service: `sudo systemctl start postgresql`
3. Enable auto-start: `sudo systemctl enable postgresql`
4. Switch to postgres user: `sudo -u postgres psql`
5. Create new database: `CREATE DATABASE myproject;`
6. Create new user: `CREATE USER myuser WITH ENCRYPTED PASSWORD 'mypassword';`
7. Grant privileges: `GRANT ALL PRIVILEGES ON DATABASE myproject TO myuser;`
8. Exit psql: `\q`
9. Test connection: `psql -h localhost -U myuser -d myproject`

## Verification
Run `psql --version` to confirm installation and `sudo systemctl status postgresql` to verify service is running.

## Pitfalls
- Default postgres user has no password - secure it immediately
- Firewall may block port 5432 for remote connections
- pg_hba.conf authentication settings can prevent connections

## Sources
- https://www.postgresql.org/
- https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
- https://www.w3schools.com/postgresql/