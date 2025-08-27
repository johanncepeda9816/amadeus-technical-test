# Amadeus Travel Platform

This is a monorepo containing the complete Amadeus Travel platform, including both frontend and backend applications.

## Project Structure

```
amadeus/
├── amadeus-travel/          # Frontend (React + TypeScript + Vite)
│   ├── Dockerfile          # Frontend container configuration
│   └── ...
├── amadeus-travel-api/      # Backend (Java + Spring Boot)
│   ├── Dockerfile          # Backend container configuration
│   └── ...
├── docker-compose.yml      # Multi-container orchestration
└── README.md               # This file
```

## Projects

### Frontend (amadeus-travel)

- **Technologies**: React, TypeScript, Vite, Material-UI
- **Development port**: 5173
- **Package manager**: pnpm
- **Documentation**: [Frontend README](./amadeus-travel/README.md)

### Backend (amadeus-travel-api)

- **Technologies**: Java, Spring Boot, Maven
- **Port**: 8080
- **Database**: H2 (development)
- **Documentation**: [Backend README](./amadeus-travel-api/README.md)

## Development

Each project maintains its own Git repository and independent configuration. For detailed setup and development instructions, refer to each project's documentation:

- **Frontend**: See [amadeus-travel/README.md](./amadeus-travel/README.md)
- **Backend**: See [amadeus-travel-api/README.md](./amadeus-travel-api/README.md)

### Run Frontend

```bash
cd amadeus-travel
pnpm install
pnpm dev
```

### Run Backend

```bash
cd amadeus-travel-api
./mvnw spring-boot:run
```

## Docker Setup (Recommended)

The easiest way to run the entire platform is using Docker Compose. This will automatically install all dependencies and start both applications.

### Prerequisites

- Docker
- Docker Compose

### Quick Start

```bash
# Clone the repository
git clone <repository-url>
cd amadeus

# Start all services
docker-compose up --build
```

### Services

- **Frontend**: http://localhost:5173
- **Backend API**: http://localhost:8080/api
- **API Documentation**: http://localhost:8080/api/swagger-ui.html

### Docker Commands

```bash
# Start services in background
docker-compose up -d

# View logs
docker-compose logs -f

# Stop services
docker-compose down

# Rebuild and start
docker-compose up --build

# Stop and remove all containers, networks, and volumes
docker-compose down -v
```

## Development Structure

This monorepo allows managing both projects in a coordinated way while maintaining the independence of each one. Projects can be developed and deployed separately, but can also be versioned together when necessary.

## Future Features

### CI/CD Pipeline

- **Automated Testing**: Lint and test both projects on every commit
- **Change Detection**: Only build and deploy affected projects based on file changes
- **Multi-Environment Deployment**:
  - Staging environment with auto-deployment on `develop` branch
  - Production deployment with manual approval on `main` branch
- **Platform Options**: GitHub Actions, GitLab CI/CD, or Jenkins
- **Build Strategy**:
  - Frontend: ESLint, TypeScript checks, unit tests → build artifacts
  - Backend: Checkstyle, unit/integration tests → JAR packaging
- **Deployment**: Container-based deployment with blue-green or rolling strategies
