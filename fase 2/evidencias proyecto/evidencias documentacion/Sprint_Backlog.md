# Sprint Backlog — Aprueba Administración

## 1. Marco de trabajo

El proyecto se planificó utilizando **Scrum**, con:

- 10 sprints;
- duración aproximada de 1 semana por sprint;
- planificación por incrementos funcionales;
- capacidad de referencia cercana a 8 Story Points por desarrollador/sprint en el plan original.

El trabajo del equipo APT se concentró principalmente en el **Frontend de Aprueba Administración**.

## 2. Sprint Backlog consolidado

### Sprint 1 — Cimientos del Frontend

**Objetivo:** dejar preparada la base de la SPA administrativa.

**Actividades:**
- revisar proyecto base;
- instalar dependencias;
- configurar React 18 y Vite;
- configurar React Router;
- definir layout y navegación;
- preparar tema claro/oscuro;
- revisar internacionalización ES/EN.

**Resultado:** base del frontend lista para incorporar los módulos administrativos.

---

### Sprint 2 — Autenticación y modo demo

**Objetivo:** disponer de un flujo de acceso demostrable aunque la API real no esté completamente disponible.

**Actividades:**
- vista de inicio de sesión;
- validación de credenciales demo;
- flujo MFA demostrativo;
- control básico de sesión;
- definición de roles administrativos;
- implementación de `VITE_DEMO_MODE`.

**Resultado:** autenticación demostrable y frontend desacoplado temporalmente del backend.

---

### Sprint 3 — Resumen / Dashboard

**Objetivo:** visualizar indicadores generales del negocio.

**Actividades:**
- construir vista Resumen;
- tarjetas KPI;
- gráficos y tendencias;
- estado general de servicios;
- revisión de responsividad.

**Resultado:** dashboard principal navegable.

---

### Sprint 4 — Comercial

**Objetivo:** representar información comercial relevante.

**Actividades:**
- métricas DAU/MAU;
- conversión;
- MRR;
- embudo;
- recaudación;
- medallas y otros indicadores.

**Resultado:** módulo Comercial disponible en el MVP.

---

### Sprint 5 — Sponsors

**Objetivo:** permitir la gestión administrativa de sponsors.

**Actividades:**
- listado;
- creación;
- edición;
- eliminación;
- validación de formularios.

**Resultado:** CRUD de sponsors funcional en modo demo.

---

### Sprint 6 — Operativa

**Objetivo:** representar el monitoreo de servicios y contenedores.

**Actividades:**
- estado de servicios;
- CPU y memoria;
- listado de contenedores;
- acción de reinicio simulada;
- mensajes de estado.

**Resultado:** módulo Operativa funcional en modo demostración.

---

### Sprint 7 — Usuarios y soporte

**Objetivo:** habilitar los principales flujos administrativos de usuarios y soporte.

**Actividades:**
- búsqueda de usuarios;
- suspensión/reactivación;
- cambio de plan;
- tickets;
- estados y prioridades;
- validación de flujos de soporte.

**Resultado:** administración de usuarios y tickets disponible en el MVP.

---

### Sprint 8 — Tutores, recorrecciones y contenido

**Objetivo:** incorporar funcionalidades de gestión académica y moderación.

**Actividades:**
- gestión de tutores;
- verificación y pausa/reactivación;
- solicitudes de recorrección;
- creación y edición de preguntas;
- publicación;
- importación JSON.

**Resultado:** módulos de Tutores y Contenido disponibles, junto con flujos de recorrección.

---

### Sprint 9 — Planes y productos

**Objetivo:** representar la configuración de la oferta comercial.

**Actividades:**
- listado de planes;
- creación/edición/eliminación;
- configuración de límites;
- asignación de características;
- preparación para integración con precios de Stripe.

**Resultado:** constructor/configuración de planes funcional en modo demo.

---

### Sprint 10 — QA, documentación y despliegue

**Objetivo:** estabilizar el MVP y generar evidencias.

**Actividades:**
- pruebas funcionales;
- corrección de rutas SPA;
- validación con F5 en rutas internas;
- `npm run build`;
- Git y GitHub;
- despliegue en Vercel;
- diagramas UML;
- documentación técnica;
- identificación de brechas para integración backend.

**Resultado:** MVP frontend navegable, compilado, documentado y desplegado.

## 3. Ajustes realizados durante los sprints

La principal adaptación fue no esperar la disponibilidad completa del backend.

Se utilizó:

```text
VITE_DEMO_MODE=true
```

para ejecutar el frontend con datos simulados y continuar validando los flujos.

Esta decisión permitió mantener el avance incremental y dejó la integración con endpoints reales como trabajo posterior.

## 4. Próximo Sprint / trabajo pendiente

- integración real con `/api/v1/admin`;
- persistencia Firestore;
- validación de JWT, MFA y RBAC reales;
- integración Stripe;
- pruebas Frontend–Backend;
- pruebas de seguridad;
- Dockerización, si se adopta como requisito de despliegue.
