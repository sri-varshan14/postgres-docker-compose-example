# Docker Compose Configuration for PostgreSQL

This Docker Compose configuration sets up a PostgreSQL database server using the official PostgreSQL Docker image.

## Prerequisites

- [Docker](https://www.docker.com/get-started) must be installed on your machine.

## Usage

1. Clone this repository:

   ```bash
   wget wget https://github.com/sri-varshan14/postgres-docker-compose-example/blob/master/docker-compose.yml
   ```

2. Create and start the PostgreSQL container:

   ```bash
   docker-compose up -d
   ```

   The `-d` flag runs the containers in the background.

3. To stop the containers:

   ```bash
   docker-compose down
   ```

## Services

### 1. PostgreSQL Database (db)

- **Container Name:** `postgres`
- **Image:** `postgres:alpine`
- **Environment Variables:**
  - `POSTGRES_DB`: Name of the default database (`postgres` in this case).
  - `POSTGRES_USER`: Username for PostgreSQL (`postgres` in this case).
  - `POSTGRES_PASSWORD`: Password for the specified user (`postgres` in this case).
  - `PGDATA`: PostgreSQL data directory (`/data/postgres`).
- **Ports:** Maps the host machine's port 5432 to the container's port 5432.
- **Volumes:** Persists data in the `/var/lib/postgresql/data` directory to the `db-data` volume.
- **Networks:** Connects to the `postgres` bridge network.
- **Restart:** Container restart policy is set to `unless-stopped`.

## Networks

### 1. postgres Network

- **Driver:** Bridge network for communication between containers.

## Volumes

### 1. db-data Volume

- **Purpose:** Volume to persist PostgreSQL data.

## License

This Docker Compose configuration is provided under the [MIT License](LICENSE).
