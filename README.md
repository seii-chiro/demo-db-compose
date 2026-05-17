# postgredb Setup Guide

`postgredb` provides a shared PostgreSQL container for applications that connect through the external Docker network named `app-network`.

## Prerequisites

- Docker Desktop
- Docker Compose

## Setup

1. Create the shared Docker network if it does not exist:

   ```bash
   docker network create app-network
   ```

2. Copy the environment file:

   ```powershell
   Copy-Item .env.example .env
   ```

   On macOS, Linux, Git Bash, or WSL:

   ```bash
   cp .env.example .env
   ```

3. Update `.env` if needed:

   ```env
   DB_DATABASE=sampledb
   DB_USERNAME=postgres
   DB_PASSWORD=postgres
   ```

4. Start PostgreSQL:

   ```bash
   docker compose up -d
   ```

PostgreSQL is available inside Docker as `db:5432` and from your machine as `localhost:5446`.

## Stop

```bash
docker compose down
```

To remove the database volume too:

```bash
docker compose down -v
```

