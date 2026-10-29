# Retrospectivas Scrum — Aprueba Administración

## 1. Objetivo

Este documento consolida las principales retrospectivas y aprendizajes obtenidos durante los sprints de Aprueba Administración.

Se registra:

- qué funcionó;
- qué dificultad apareció;
- qué acción de mejora se tomó o se propone.

> Este es un registro retrospectivo consolidado del trabajo realizado. No pretende reemplazar actas formales que no hayan sido generadas durante cada reunión.

## 2. Retrospectivas por Sprint

| Sprint | Qué funcionó bien | Dificultad / aprendizaje | Acción de mejora |
|---|---|---|---|
| 1 | La revisión del proyecto base permitió identificar componentes y tecnologías existentes. | La configuración inicial del entorno requirió tiempo y revisión de dependencias. | Documentar pasos de instalación y mantener dependencias controladas. |
| 2 | Se logró validar el flujo de autenticación desde el frontend. | El backend no estaba completamente disponible para autenticación real. | Incorporar modo demo y separar la fuente de datos de la interfaz. |
| 3 | El Dashboard permitió obtener rápidamente una vista demostrable del producto. | Fue necesario mantener los gráficos ligeros y legibles. | Priorizar KPIs relevantes y evitar sobrecargar las vistas. |
| 4 | La vista Comercial permitió reutilizar componentes de indicadores. | Existía riesgo de duplicar lógica y estilos. | Reutilizar componentes y mantener consistencia visual. |
| 5 | El CRUD de Sponsors permitió validar formularios y acciones administrativas. | Los datos simulados no permanecen necesariamente después de recargar. | Mantener claramente identificadas las limitaciones del modo demo. |
| 6 | Operativa permitió representar un caso técnico distinto a los módulos CRUD. | El reinicio de servicios no podía ejecutarse contra infraestructura real. | Simular el flujo en MVP y dejar la operación real para integración backend. |
| 7 | Los flujos de usuarios y soporte demostraron acciones administrativas relevantes. | Aumentó la cantidad de estados y acciones posibles. | Simplificar estados, validar formularios y probar flujos principales. |
| 8 | Se incorporaron tutores, recorrecciones e importación JSON. | La diversidad de funcionalidades incrementó la complejidad del módulo. | Separar responsabilidades por vista y probar cada flujo de manera independiente. |
| 9 | El módulo de planes permitió representar la administración de productos. | La sincronización real con Stripe depende del backend. | Mantener la integración externa fuera del frontend y documentar el contrato esperado. |
| 10 | Se logró un build de producción y despliegue en Vercel. | Las rutas SPA requirieron configuración para funcionar al actualizar con F5. | Agregar configuración de rewrites y pruebas de despliegue antes del cierre. |

## 3. Principales aprendizajes del equipo

### Dependencias entre equipos

La principal dificultad fue la dependencia del backend administrativo.

**Aprendizaje:** frontend y backend deben acordar tempranamente el contrato de API para reducir bloqueos.

### Desarrollo desacoplado

El modo demo permitió continuar el trabajo sin esperar todos los servicios externos.

**Aprendizaje:** una capa de datos desacoplada facilita desarrollo, pruebas y futura integración.

### Pruebas durante el desarrollo

Las validaciones por módulo ayudaron a detectar problemas antes del despliegue.

**Aprendizaje:** las pruebas no deben dejarse solamente para el final del proyecto.

### Control de versiones y despliegue

Git, GitHub y Vercel permitieron mantener trazabilidad y publicar una versión accesible.

**Aprendizaje:** el despliegue temprano ayuda a descubrir problemas que no siempre aparecen en desarrollo local.

## 4. Mejoras para una siguiente iteración

- definir contrato OpenAPI/API antes del desarrollo de las vistas;
- agregar pruebas automatizadas desde los primeros sprints;
- establecer revisiones de código;
- mejorar documentación en cada sprint;
- integrar observabilidad;
- mantener un tablero Scrum con responsables y estados actualizados;
- validar Docker y estrategia de despliegue si pasa a ser requisito obligatorio.
