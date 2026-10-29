
# Aprueba Administración

Proyecto APT / Capstone de **Ingeniería en Informática — Duoc UC Plaza Oeste**.

**Equipo 3**  
**Integrantes:** Ignacio Catalán y Fernando Casanueva.

---

## Descripción del proyecto

**Aprueba Administración** es una consola web para gestionar y monitorear procesos administrativos de la plataforma Aprueba.

El equipo se concentró específicamente en el **Frontend de Administración del negocio**, desarrollando un MVP que permite representar las principales funciones de:

- Resumen / KPIs.
- Comercial.
- Sponsors.
- Operativa.
- Usuarios y soporte.
- Tutores.
- Contenido.
- Planes y productos.

El MVP actual funciona con un modo demostración basado en datos simulados mientras se completa la integración con el backend real.

**MVP desplegado:**  
https://aprueba-admin-flax.vercel.app

**Repositorio de implementación:**  
https://github.com/nacho055555/Aprueba-Admin

---

## Integrantes y roles

### Ignacio Catalán

Responsabilidades principales:

- autenticación y modo demo;
- Operativa;
- Usuarios y soporte;
- Tutores;
- integración general;
- pruebas;
- Git/GitHub;
- despliegue y documentación.

### Fernando Casanueva

Responsabilidades principales:

- Resumen;
- Comercial;
- Sponsors;
- Contenido / banco de preguntas;
- Planes y productos;
- pruebas;
- revisión funcional;
- documentación.

Las actividades de validación final, control de versiones, evidencias y despliegue fueron revisadas en conjunto.

---

## Metodología

Se utilizó un enfoque **Scrum / ágil e incremental**.

Plan general:

- 10 sprints;
- aproximadamente 1 semana por sprint;
- desarrollo por incrementos funcionales;
- planificación original de 1 FE + 1 BE;
- capacidad de referencia cercana a 8 Story Points por desarrollador/sprint.

La dependencia del backend llevó al equipo Frontend a implementar un modo demostración para mantener el avance sin bloquear los sprints.

Documentación Scrum:

- `Product_Vision.md`
- `Product_Backlog.md`
- `Sprint_Backlog.md`
- `Retrospectivas_Scrum.md`
- Definition of Done incluida en la documentación del proyecto.

---

## Tecnologías utilizadas

### Frontend

- JavaScript
- React 18
- React DOM
- React Router
- Vite
- HTML
- CSS

### Backend / arquitectura objetivo del proyecto

- Node.js
- Express
- Firebase Admin SDK
- Cloud Firestore
- API REST
- JWT
- MFA
- RBAC

### Integraciones

- Stripe

### Desarrollo y despliegue

- Node.js / npm
- Git
- GitHub
- Vercel
- variables de entorno

### Portabilidad

- Docker: **propuesto / pendiente de implementación en el repositorio actual**.

---

## Arquitectura

La solución utiliza una arquitectura desacoplada entre interfaz, API y datos.

```text
Administrador
     |
     | HTTPS
     v
Frontend SPA
React 18 + Vite + React Router
     |
     | REST / JSON
     | /api/v1/admin
     v
Backend administrativo
Node.js + Express
JWT + MFA + RBAC
     |
     +------------------> Stripe
     |
     v
Firebase Admin SDK
     |
     v
Cloud Firestore
```

### Principios

- separación Frontend / Backend;
- API REST versionada;
- el frontend no accede directamente a Firestore para operaciones sensibles;
- autorización y reglas críticas centralizadas en backend;
- contrato común `{data, error, meta}`;
- arquitectura preparada para sustituir datos demo por endpoints reales.

---

## Modelo de datos

La solución utiliza un modelo documental basado en **Cloud Firestore**.

Dominios principales:

- `adminUsers`
- `adminSessions`
- `auditLog`
- `users`
- `medalLedger`
- `supportTickets`
- `corrections`
- `questions`
- `sponsors`
- `benefits`
- `plans`
- `features`
- `subscriptions`
- métricas y operación.

Ver:

`modelo-datos-resumido.md`

---

## Requisitos no funcionales

El proyecto considera:

- seguridad;
- rendimiento;
- escalabilidad;
- disponibilidad;
- portabilidad;
- mantenibilidad;
- usabilidad;
- compatibilidad;
- auditoría.

Ver:

`Requisitos_No_Funcionales.md`

---

## Ejecución local

El código del MVP se encuentra en:

https://github.com/nacho055555/Aprueba-Admin

### Requisitos

- Node.js
- npm
- Git

### Frontend

Clonar el repositorio:

```bash
git clone https://github.com/nacho055555/Aprueba-Admin.git
cd Aprueba-Admin/aprueba_admin_web/frontend
```

Instalar dependencias:

```bash
npm install
```

Crear o configurar la variable de entorno para ejecutar el modo demostración:

```text
VITE_DEMO_MODE=true
```

Ejecutar:

```bash
npm run dev
```

Build de producción:

```bash
npm run build
```

Vista previa del build:

```bash
npm run preview
```

### Backend base

```bash
cd Aprueba-Admin/aprueba_admin_web/backend
npm install
npm run dev
```

> El MVP Frontend desplegado utiliza modo demo; la integración completa con backend real se mantiene como trabajo pendiente.

---

## Pruebas

Se realizaron pruebas funcionales sobre:

- login y MFA demo;
- navegación entre las 8 vistas;
- Sponsors;
- Operativa;
- Usuarios;
- Tickets;
- Recorrecciones;
- Tutores;
- Contenido;
- importación JSON;
- Planes;
- build de producción;
- despliegue Vercel;
- rutas SPA al actualizar con F5.

Ver:

`plan-pruebas.md`

---

## Diagramas UML

Las evidencias incluyen:

- Diagrama de Casos de Uso.
- Diagrama de Clases.
- Diagrama de Actividades.

La documentación técnica ampliada también considera arquitectura, componentes y secuencia de funcionalidad.

---

## Innovación

El proyecto agrega valor mediante:

- centralización de procesos administrativos;
- administración por roles;
- importación masiva de contenido;
- integración de negocio y operación;
- arquitectura desacoplada;
- modo demo que permitió mantener el desarrollo Frontend pese a la dependencia del Backend.

Ver:

`Innovacion.md`

---

## Estado actual

### Completado / validado

- MVP Frontend funcional.
- 8 vistas administrativas.
- navegación.
- acciones principales en modo demo.
- build de producción.
- Git/GitHub.
- despliegue en Vercel.
- documentación técnica.
- diagramas UML.
- plan de pruebas.

### Pendiente / siguiente etapa

- integración completa con backend;
- persistencia real;
- JWT/MFA/RBAC reales de extremo a extremo;
- integración Stripe;
- pruebas de integración;
- QA de seguridad;
- Docker funcional.

---

## Evidencias

**MVP:**  
https://aprueba-admin-flax.vercel.app

**Repositorio de implementación:**  
https://github.com/nacho055555/Aprueba-Admin

**Repositorio de evidencias:**  
https://github.com/nacho055555/Aprueba-Administracion-
