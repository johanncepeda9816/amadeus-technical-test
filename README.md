# Amadeus Travel Platform

This is a monorepo containing the complete Amadeus Travel platform, including both frontend and backend applications.

## Project Structure

```
amadeus/
├── amadeus-travel/          # Frontend (React + TypeScript + Vite)
├── amadeus-travel-api/      # Backend (Java + Spring Boot)
└── README.md               # This file
```

## Projects

### Frontend (amadeus-travel)

- **Technologies**: React, TypeScript, Vite, Material-UI
- **Development port**: 5173
- **Package manager**: pnpm

### Backend (amadeus-travel-api)

- **Technologies**: Java, Spring Boot, Maven
- **Port**: 8080
- **Database**: H2 (development)

## Development

Each project maintains its own Git repository and independent configuration. To work with each project, navigate to its corresponding directory and follow the instructions in its specific README.

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

## Development Structure

This monorepo allows managing both projects in a coordinated way while maintaining the independence of each one. Projects can be developed and deployed separately, but can also be versioned together when necessary.
