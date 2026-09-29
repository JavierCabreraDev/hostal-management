# ADR-002 — Proveedor de PostgreSQL

## Estado

Aceptado

## Fecha

2026-09-29

## Contexto

Hostal Management System requiere una base de datos relacional
PostgreSQL administrada y accesible desde el entorno de desarrollo
en CodeSandbox y posteriormente desde el entorno de producción.

El proyecto tiene además un objetivo experimental orientado al
aprendizaje de backend, bases de datos, migraciones y despliegue.

## Decisión

Se utilizará Neon como proveedor administrado de PostgreSQL.

Prisma ORM será utilizado como capa de acceso a datos.

Next.js será responsable de la lógica backend de la aplicación.

## Arquitectura

Next.js
    ↓
Prisma ORM
    ↓
Neon
    ↓
PostgreSQL

## Motivos

- PostgreSQL real y administrado.
- Integración con Prisma.
- Compatibilidad con aplicaciones serverless.
- Connection management apropiado para aplicaciones modernas.
- Database branching.
- Integración con Vercel.
- Plan gratuito adecuado para desarrollo y prototipado.
- Permite mantener separadas las responsabilidades de framework,
  ORM y proveedor de base de datos.

## Alternativas consideradas

### Prisma Postgres

Ofrece una integración excelente con Prisma y simplifica
considerablemente la configuración inicial.

No fue seleccionado porque se busca mantener separadas las
responsabilidades entre ORM y proveedor de PostgreSQL.

### Supabase

Ofrece PostgreSQL junto con autenticación, realtime, storage,
APIs y otros servicios.

No se utilizará como backend principal porque el proyecto busca
implementar explícitamente la capa backend mediante Next.js.

Supabase podría evaluarse posteriormente como proveedor de
PostgreSQL o para funcionalidades específicas.

### PostgreSQL local

Puede utilizarse posteriormente para desarrollo local si resulta
conveniente, pero el entorno principal utilizará PostgreSQL
administrado debido al uso de CodeSandbox.

## Consecuencias

### Positivas

- PostgreSQL administrado.
- Menor infraestructura operacional.
- Branching de bases de datos.
- Buena integración con Prisma.
- Buena integración con futuros despliegues en Vercel.
- Separación clara de responsabilidades.

### Negativas

- Dependencia de un proveedor externo.
- Dependencia de conexión a Internet para la base de desarrollo.
- El plan gratuito tiene límites de almacenamiento y cómputo.

## Decisión futura

El proveedor podrá cambiarse sin modificar la arquitectura de
la aplicación mientras el nuevo proveedor mantenga compatibilidad
con PostgreSQL.

La capa Prisma deberá ser la principal frontera entre la aplicación
y el proveedor de base de datos.