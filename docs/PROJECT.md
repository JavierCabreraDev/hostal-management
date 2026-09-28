# Hostal Management System

## Proyecto

Sistema interno de gestión para Hostal Puerto Victoria.

## Versión

0.1.0-alpha

## Estado

En desarrollo

---

## Descripción

Aplicación web orientada a la administración y operación
diaria del Hostal Puerto Victoria.

El sistema busca digitalizar y centralizar procesos
actualmente realizados de forma manual.

---

## Objetivo general

Desarrollar una aplicación web que permita administrar
las operaciones diarias del hostal, centralizando la
gestión de reservas, habitaciones, check-in, check-out,
limpieza y visualización operacional.

---

## Objetivos específicos

- Digitalizar el proceso de check-in.
- Digitalizar el proceso de check-out.
- Gestionar el estado de las habitaciones.
- Gestionar las tareas de limpieza.
- Registrar solicitudes de limpieza.
- Visualizar la ocupación mediante un calendario.
- Proporcionar un dashboard operacional.
- Mantener un historial de eventos.
- Centralizar la información operacional.

---

## Stack tecnológico

### Frontend

- Next.js
- React
- TypeScript
- Tailwind CSS

### Backend

- Next.js
- Route Handlers
- Server Actions

### Base de datos

- PostgreSQL
- Prisma ORM

### Validación

- Zod

### Autenticación

- Auth.js

---

## Arquitectura

La aplicación seguirá inicialmente una arquitectura
Full Stack utilizando Next.js como framework principal.

La persistencia de datos estará gestionada mediante
PostgreSQL y Prisma ORM.

---

## Alcance inicial

### Dashboard

- Estado general del hostal.
- Ocupación.
- Check-ins.
- Check-outs.
- Habitaciones pendientes de limpieza.

### Habitaciones

- Listado.
- Estado actual.
- Información de habitación.
- Historial.

### Reservas

- Calendario.
- Check-in.
- Check-out.
- Asignación de habitación.

### Limpieza

- Solicitudes.
- Tareas pendientes.
- Tareas en progreso.
- Tareas completadas.

### Historial

- Eventos de habitaciones.
- Cambios de estado.
- Acciones de usuarios.

---

## Estado del proyecto

### Sprint 0 — Fundaciones

- [x] Crear proyecto Next.js
- [x] Crear estructura inicial
- [ ] Configurar documentación
- [ ] Definir arquitectura
- [ ] Configurar Prisma
- [ ] Configurar PostgreSQL
- [ ] Diseñar modelo de datos
- [ ] Configurar autenticación

### Sprint 1 — Habitaciones

- [ ] Modelo Room
- [ ] CRUD de habitaciones
- [ ] Estados
- [ ] Dashboard inicial

### Sprint 2 — Reservas

- [ ] Modelo Reservation
- [ ] Modelo Guest
- [ ] Calendario
- [ ] Check-in
- [ ] Check-out

### Sprint 3 — Limpieza

- [ ] Modelo CleaningTask
- [ ] Solicitudes
- [ ] Estados
- [ ] Historial

---

## Principios del proyecto

1. Mantener una única fuente de verdad para los datos.
2. Separar presentación, lógica de negocio y persistencia.
3. Validar los datos en el servidor.
4. Priorizar integridad de datos.
5. Registrar eventos relevantes.
6. Diseñar pensando en futuras extensiones.
7. Mantener documentación técnica actualizada.
