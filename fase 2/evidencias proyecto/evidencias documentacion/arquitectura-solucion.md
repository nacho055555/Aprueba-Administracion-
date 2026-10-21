# Arquitectura de la Solución — Aprueba Administración

## 1. Propósito
Aprueba Administración es la consola web utilizada para gestionar y monitorear procesos administrativos de la plataforma Aprueba. El alcance de nuestro equipo corresponde al **Frontend de Administración del negocio**, desarrollado como una SPA web.

El objetivo arquitectónico es mantener una separación clara entre presentación, lógica de negocio, seguridad, acceso a datos e integraciones externas.

## 2. Arquitectura general
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

### Responsabilidades por capa
**Frontend**
- navegación entre módulos;
- formularios y visualización de información;
- tema claro/oscuro e i18n ES/EN;
- consumo de servicios REST.

**Backend**
- lógica administrativa;
- validaciones;
- autenticación y autorización;
- control de roles;
- auditoría;
- acceso a Firestore mediante Firebase Admin SDK;
- integración con servicios externos.

**Firestore**
- persistencia documental de usuarios, contenido, soporte, sponsors, planes, métricas y auditoría.

**Stripe**
- integración asociada a precios y suscripciones.

## 3. API y contrato de comunicación
El frontend se comunica con el backend mediante una API REST versionada bajo `/api/v1/admin`.

Formato común de respuesta:
```json
{
  "data": {},
  "error": null,
  "meta": {}
}
```

## 4. C4 — Nivel 1: Contexto
```text
Administrador
    |
    v
Aprueba Administración
    |     |  \--> Stripe
    |
    +-----> Plataforma Aprueba
```

Actor principal: usuarios administrativos de gerencia, finanzas, operaciones o soporte.

## 5. C4 — Nivel 2: Contenedores
```text
[Administrador]
      |
      v
[SPA Web]
React 18 + Vite
      |
      | HTTPS / REST
      v
[Backend Admin]
Node.js + Express
   |               |             \--> [Stripe]
   v
[Cloud Firestore]
```

### Decisión arquitectónica principal
El frontend **no debe acceder directamente a Firestore** para ejecutar operaciones administrativas sensibles. El backend centraliza reglas de negocio, permisos, validaciones y auditoría.

## 6. Modelo 4+1 aplicado
**Vista lógica:** usuarios, sponsors, tickets, preguntas, tutores, planes, métricas y auditoría.

**Vista de desarrollo:** SPA React, API Express, rutas, módulos y repositorio Git.

**Vista de procesos:** login, MFA, consultas, CRUD, recorrecciones y auditoría.

**Vista física:** navegador, frontend web, API, Firestore y Stripe.

**+1 Escenarios:** suspender usuario, importar JSON, modificar plan, resolver recorrección y reiniciar un servicio.

## 7. Estado actual del Frontend
Actualmente se dispone de un MVP funcional con las 8 vistas administrativas, build de producción validado y despliegue en Vercel.

Para permitir el avance independiente del backend se implementó `VITE_DEMO_MODE=true`.

## 8. Próximos pasos
- integrar endpoints reales;
- reemplazar datos simulados por persistencia real;
- realizar pruebas de integración;
- reforzar seguridad y auditoría;
- mejorar mantenibilidad y responsividad.

## 9. Evidencias
**MVP:** https://aprueba-admin-flax.vercel.app  
**Repositorio:** https://github.com/nacho055555/Aprueba-Admin
