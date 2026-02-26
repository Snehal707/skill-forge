---
name: postgresql-install-setup
description: Install and configure PostgreSQL database server for local development
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

# Install and Setup PostgreSQL

## When to Use
When you need to install PostgreSQL database server for local development, testing, or production use.

## Prerequisites
- Administrative/sudo privileges on your system
- Internet connection for downloading packages

## Procedure
1. **Install PostgreSQL** (Ubuntu/Debian): `sudo apt update && sudo apt install postgresql postgresql-contrib`
2. **Install PostgreSQL** (macOS): `brew install postgresql`
3. **Install PostgreSQL** (Windows): Download installer from https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
4. **Start PostgreSQL service**: `sudo systemctl start postgresql`
5. **Enable auto-start**: `sudo systemctl enable postgresql`
6. **Switch to postgres user**: `sudo -i -u postgres`
7. **Access PostgreSQL prompt**: `psql`
8. **Set password for postgres user**: `\password postgres`
9. **Create new database**: `CREATE DATABASE myproject;`
10. **Create new user**: `CREATE USER myuser WITH ENCRYPTED PASSWORD 'mypassword';`
11. **Grant privileges**: `GRANT ALL PRIVILEGES ON DATABASE myproject TO myuser;`
12. **Exit psql**: `\q`

## Verification
- Check service status: `sudo systemctl status postgresql`
- Connect to database: `psql -h localhost -U myuser -d myproject`
- List databases: `\l` (inside psql)

## Pitfalls
- Default postgres user has no password initially
- PostgreSQL uses peer authentication by default on Unix systems
- Firewall may block connections on port 5432
- Check pg_hba.conf for authentication configuration issues

## Sources
- https://www.postgresql.org/
- https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
- https://www.w3schools.com/postgresql/