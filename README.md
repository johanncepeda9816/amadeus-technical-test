# Amadeus Travel Platform

This is a monorepo containing the complete Amadeus Travel platform, including both frontend and backend applications as Git submodules.

## Project Structure

```
amadeus-technical-test/
├── .gitmodules             # Git submodules configuration
├── amadeus-travel/         # Frontend submodule (React + TypeScript + Vite)
├── amadeus-travel-api/     # Backend submodule (Java + Spring Boot)
├── docker-compose.yml      # Multi-container orchestration
└── README.md               # This file
```

## Projects

### Frontend (amadeus-travel)

- **Technologies**: React, TypeScript, Vite, Material-UI
- **Development port**: 5173
- **Package manager**: pnpm
- **Repository**: [amadeus-travel](https://github.com/johanncepeda9816/amadeus-travel)
- **Documentation**: [Frontend README](https://github.com/johanncepeda9816/amadeus-travel#readme)

### Backend (amadeus-travel-api)

- **Technologies**: Java, Spring Boot, Maven
- **Port**: 8080
- **Database**: H2 (development)
- **Repository**: [amadeus-travel-api](https://github.com/johanncepeda9816/amadeus-travel-api)
- **Documentation**: [Backend README](https://github.com/johanncepeda9816/amadeus-travel-api#readme)

## Development

Each project is a Git submodule pointing to its own independent repository. For detailed setup and development instructions, refer to each project's documentation:

- **Frontend**: See [Frontend Repository](https://github.com/johanncepeda9816/amadeus-travel#readme)
- **Backend**: See [Backend Repository](https://github.com/johanncepeda9816/amadeus-travel-api#readme)

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
# Clone the repository with submodules
git clone --recursive https://github.com/johanncepeda9816/amadeus-technical-test.git
cd amadeus-technical-test

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

This monorepo uses **Git Submodules** to manage both projects in a coordinated way while maintaining complete independence. Each project has its own repository, commit history, and can be developed separately.

### Working with Submodules

```bash
# Clone repository with all submodules
git clone --recursive https://github.com/johanncepeda9816/amadeus-technical-test.git

# If you already cloned without --recursive, initialize submodules
git submodule update --init --recursive

# Update all submodules to latest commits
git submodule update --remote

# Work on individual projects
cd amadeus-travel        # Work on frontend
cd amadeus-travel-api    # Work on backend
```

### Submodule Benefits

- ✅ **Independent Development**: Each project maintains its own Git history
- ✅ **Coordinated Releases**: Version projects together when needed
- ✅ **GitHub Integration**: Proper linking and navigation in GitHub
- ✅ **Flexible Deployment**: Deploy projects independently or together

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
