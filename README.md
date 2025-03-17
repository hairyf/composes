# Database Container System

This project provides Docker Compose configurations for various commonly used databases, facilitating quick deployment and usage of different databases in development environments.

## Supported Databases

- MySQL
- MongoDB
- Redis
- PostgreSQL
- SQL Server
- CockroachDB

## Usage

1. Ensure that [Docker](https://docs.docker.com/get-docker/) and [Docker Compose](https://docs.docker.com/compose/install/) are installed
2. Modify the configurations in the `.env` file as needed
3. Use the following commands to start the required databases

### Starting a Single Database

```bash
# Start MySQL
docker-compose -f compose.mysql.yml up -d

# Start MongoDB
docker-compose -f compose.mongodb.yml up -d

# Start Redis
docker-compose -f compose.redis.yml up -d

# Start PostgreSQL
docker-compose -f compose.postgres.yml up -d

# Start SQL Server
docker-compose -f compose.sqlserver.yml up -d

# Start CockroachDB
docker-compose -f compose.cockroach.yml up -d

# Start PlanetScale (MySQL compatible)
docker-compose -f compose.planetscale.yml up -d
```

### Stopping Containers

```bash
# Stop and remove MySQL container
docker-compose -f compose.mysql.yml down

# Stop and remove containers but preserve data volumes
docker-compose -f compose.mysql.yml down --volumes
```

## Connection Information

### MySQL
- Host: localhost
- Port: 3306 (configurable in .env)
- Username: root
- Password: 123456 (configurable in .env)

### MongoDB
- Host: localhost
- Port: 27017 (configurable in .env)
- Username: root
- Password: 123456 (configurable in .env)

### Redis
- Host: localhost
- Port: 6379 (configurable in .env)

### PostgreSQL
- Host: localhost
- Port: 5432 (configurable in .env)
- Username: postgres
- Password: 123456 (configurable in .env)
- Database: postgres

### SQL Server
- Host: localhost
- Port: 1433 (configurable in .env)
- Username: sa
- Password: Password123! (configurable in .env)

### CockroachDB
- Host: localhost
- Port: 26257 (configurable in .env)
- Web UI: localhost:8080 (configurable in .env)
- No authentication required (single-node insecure mode)


## Data Persistence

All databases are configured with data volumes to ensure data persistence. Data is stored in Docker volumes, so it will be preserved even if containers are removed.
