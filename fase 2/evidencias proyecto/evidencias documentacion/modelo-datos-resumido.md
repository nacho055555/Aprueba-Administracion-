# Modelo de Datos Resumido — Aprueba Administración

## 1. Enfoque
Aprueba Administración utiliza **Cloud Firestore**, una base de datos documental. El diseño se orienta a las consultas y operaciones administrativas de la consola.

Principios considerados:
- modelo orientado a consultas;
- denormalización controlada;
- índices para consultas frecuentes;
- auditoría de acciones;
- retención o TTL cuando corresponda;
- separación por dominios funcionales.

> Este documento es un resumen conceptual para documentación del proyecto y no reemplaza el modelo técnico detallado.

## 2. Seguridad y administración
```text
adminUsers
adminSessions
auditLog
```
- **adminUsers:** usuarios autorizados para utilizar la consola.
- **adminSessions:** sesiones administrativas.
- **auditLog:** trazabilidad de acciones sensibles.

## 3. Usuarios y soporte
```text
users
medalLedger
supportTickets
corrections
```
- **users:** usuarios de la plataforma.
- **medalLedger:** movimientos de medallas.
- **supportTickets:** tickets de soporte.
- **corrections:** solicitudes de recorrección relacionadas con usuarios y preguntas.

Ejemplo de flujo: una recorrección confirmada puede otorgar **250 medallas de bronce** al usuario.

## 4. Contenido
```text
questions
```
Desde la consola se contemplan operaciones de listado, filtrado, creación, edición, cambio de estado e importación JSON.

## 5. Sponsors y beneficios
```text
sponsors
benefits
```
Permiten representar auspiciadores y beneficios asociados.

## 6. Planes y suscripciones
```text
plans
features
subscriptions
```
Permiten modelar planes comerciales, características asociadas y suscripciones.

## 7. Métricas y operación
```text
metricsDaily
metricsMonthly
serviceStatus
opsRestarts
```
Representan métricas agregadas, estados de servicios y trazabilidad de operaciones técnicas.

## 8. Relaciones conceptuales simplificadas
```text
adminUsers
   +----> adminSessions
   +----> auditLog

users
   +----> medalLedger
   +----> supportTickets
   +----> corrections ----> questions

sponsors ----> benefits

plans ----> features
   +----> subscriptions
```

Estas relaciones son conceptuales; Firestore no se interpreta como un esquema relacional con claves foráneas tradicionales.

## 9. Seguridad del acceso a datos
```text
Frontend
   |
   v
Backend Node.js + Express
   |
   v
Firebase Admin SDK
   |
   v
Firestore
```

El backend valida JWT, rol, permisos, reglas de negocio, datos de entrada y auditoría.

## 10. Evidencias
**Repositorio:** https://github.com/nacho055555/Aprueba-Admin  
**MVP:** https://aprueba-admin-flax.vercel.app
