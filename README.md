# Amadeus Travel Platform

Este es un monorepo que contiene la plataforma completa de Amadeus Travel, incluyendo tanto el frontend como el backend.

## Estructura del Proyecto

```
amadeus/
├── amadeus-travel/          # Frontend (React + TypeScript + Vite)
├── amadeus-travel-api/      # Backend (Java + Spring Boot)
└── README.md               # Este archivo
```

## Proyectos

### Frontend (amadeus-travel)
- **Tecnologías**: React, TypeScript, Vite, Material-UI
- **Puerto de desarrollo**: 5173
- **Gestión de paquetes**: pnpm

### Backend (amadeus-travel-api)  
- **Tecnologías**: Java, Spring Boot, Maven
- **Puerto**: 8080
- **Base de datos**: H2 (desarrollo)

## Desarrollo

Cada proyecto mantiene su propio repositorio Git y configuración independiente. Para trabajar con cada proyecto, navega a su directorio correspondiente y sigue las instrucciones de su README específico.

### Ejecutar Frontend
```bash
cd amadeus-travel
pnpm install
pnpm dev
```

### Ejecutar Backend
```bash
cd amadeus-travel-api
./mvnw spring-boot:run
```

## Estructura de Desarrollo

Este monorepo permite gestionar ambos proyectos de forma coordinada mientras mantiene la independencia de cada uno. Los proyectos pueden desarrollarse y desplegarse por separado, pero también pueden versionarse juntos cuando sea necesario.
