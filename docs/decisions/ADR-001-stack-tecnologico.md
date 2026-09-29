# ADR-001 — Stack tecnológico principal

## Estado

Aceptado

## Fecha

2026-09-29

## Contexto

Hostal Management System requiere una arquitectura que permita
desarrollar una aplicación web completa para administrar las
operaciones diarias de un hostal.

El proyecto tiene además un objetivo experimental y formativo:
incorporar desarrollo backend, diseño de bases de datos
relacionales, APIs, autenticación y lógica de negocio.

Por esta razón, no se busca únicamente minimizar el tiempo de
desarrollo. También se busca adquirir experiencia con conceptos
propios de una arquitectura Full Stack.

---

## Decisión

Se utilizará el siguiente stack principal:

- Next.js
- React
- TypeScript
- PostgreSQL
- Prisma ORM
- Tailwind CSS
- Zod

Next.js será utilizado tanto para la capa de presentación como
para las capacidades backend de la aplicación.

PostgreSQL será utilizado como sistema de gestión de base de
datos relacional.

Prisma será utilizado como ORM y capa principal de acceso a
datos.

---

## Arquitectura

La arquitectura inicial será:

    React
      │
      ▼
    Next.js
      │
      ├── Server Components
      ├── Server Actions
      └── Route Handlers
      │
      ▼
    Prisma
      │
      ▼
    PostgreSQL

---

## Motivos

### Next.js

Permite utilizar un único framework para frontend y backend,
reduciendo la cantidad de infraestructura inicial.

También permite trabajar con Server Components, Server Actions
y Route Handlers.

### PostgreSQL

El dominio del proyecto presenta relaciones claras entre:

- huéspedes
- reservas
- habitaciones
- tareas de limpieza
- usuarios
- eventos

Una base de datos relacional resulta apropiada para este modelo.

### Prisma

Permite trabajar con PostgreSQL desde TypeScript mediante un
modelo tipado y migraciones versionadas.

También permitirá ejecutar consultas SQL cuando sea necesario.

### TypeScript

Se utilizará para mantener tipado consistente entre las
distintas capas de la aplicación.

---

## Alternativas consideradas

### Supabase

Fue considerada como plataforma Backend-as-a-Service.

Se decidió inicialmente no utilizar Supabase como backend
principal porque el objetivo del proyecto incluye desarrollar
explícitamente la capa backend utilizando Next.js.

PostgreSQL podría utilizarse posteriormente mediante un
proveedor externo.

### Firebase

Fue considerada como alternativa Backend-as-a-Service.

No fue seleccionada debido a que el dominio presenta un modelo
fuertemente relacional y PostgreSQL resulta más adecuado para
este escenario.

### NestJS

Fue considerada como framework backend independiente.

No se utilizará inicialmente para evitar separar frontend y
backend en dos aplicaciones durante la primera etapa.

Podría evaluarse posteriormente si aparecen necesidades que
justifiquen un backend independiente.

---

## Consecuencias

### Positivas

- Una única aplicación.
- Un único lenguaje principal.
- Arquitectura Full Stack.
- PostgreSQL relacional.
- Tipado de extremo a extremo.
- Buen potencial de crecimiento.
- Mayor aprendizaje backend.

### Negativas

- Mayor responsabilidad sobre la arquitectura backend.
- Debemos diseñar correctamente la seguridad.
- Debemos administrar las migraciones.
- Algunas funcionalidades requerirán más código que utilizando
  un Backend-as-a-Service.

---

## Nota

La elección del proveedor concreto de PostgreSQL queda pendiente.

Esta decisión será registrada en un ADR independiente.
