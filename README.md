# Production-Ready E-Commerce Platform

A full-stack, scalable, and modern e-commerce platform built with React (Next.js) for the frontend, Node.js (Express) for the backend, PostgreSQL for primary data storage, and Redis for caching.

## Architecture

* **Frontend (`/frontend`)**: A modern React application built using the Next.js App Router. It features a responsive, premium glassmorphism design with Vanilla CSS.
* **Backend (`/backend`)**: A robust Express.js REST API using Sequelize ORM to interact with PostgreSQL. It handles authentication (JWT & bcrypt), product catalog management, and order processing.
* **Database**: PostgreSQL (relational data).
* **Caching**: Redis (caching frequent catalog queries for high performance).

## Features

- **User Authentication**: Secure JWT-based login and signup system.
- **Product Catalog**: High-performance product listing cached via Redis.
- **Shopping Cart**: Client-side cart management.
- **Checkout Process**: Secure backend order processing and total calculation.
- **Dockerized**: Fully containerized setup for easy deployment.

## Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop) installed on your machine.
- Node.js (if running locally without Docker).

## Getting Started (Docker - Recommended)

The easiest way to get the entire stack (Database, Cache, Backend, and Frontend) running is via Docker Compose.

1. Clone this repository or navigate to the project root.
2. Run the following command in the root directory:
   ```bash
   docker-compose up --build
   ```
3. The platform will be available at:
   - **Frontend:** http://localhost:3000
   - **Backend API:** http://localhost:5000

## Running Locally (Without Docker)

If you prefer to run the services individually on your host machine:

### 1. Start Services
Make sure you have an instance of **PostgreSQL** (running on port 5432) and **Redis** (running on port 6379) active on your machine.

### 2. Run Backend
```bash
cd backend
npm install
npm start
```
*The database models will automatically sync on server startup.*

### 3. Run Frontend
```bash
cd frontend
npm install
npm run dev
```

## Environment Variables

Default environment variables are baked into the `docker-compose.yml` and backend files. For production, you should override these:
- `JWT_SECRET`: Secret key for signing tokens.
- `DB_HOST`, `DB_USER`, `DB_PASS`, `DB_NAME`: Database credentials.
- `REDIS_URL`: URL to your Redis instance.

