# Product Backlog Priorizado — Aprueba Administración

## 1. Descripción

Este Product Backlog reúne las principales historias de usuario del módulo **Aprueba Administración**.

La priorización utiliza:

- **Must:** indispensable para el MVP.
- **Should:** importante, pero puede completarse después del núcleo.
- **Could:** mejora complementaria.

Los Story Points son una estimación relativa de esfuerzo utilizada para la planificación Scrum.

## 2. Product Backlog

| ID | Épica | Historia de usuario | Prioridad | SP | Estado |
|---|---|---|---|---:|---|
| HU-01 | Base | Como administrador, quiero acceder a una interfaz web organizada para navegar por los módulos administrativos. | Must | 5 | Implementado en MVP |
| HU-02 | Autenticación | Como administrador, quiero iniciar sesión con correo y contraseña para acceder al sistema. | Must | 5 | Implementado en modo demo |
| HU-03 | Seguridad | Como administrador, quiero validar un segundo factor MFA para aumentar la seguridad del acceso. | Must | 5 | Simulado en MVP; integración real pendiente |
| HU-04 | Seguridad | Como sistema, quiero aplicar permisos por rol para restringir acciones según gerencia, finanzas, operaciones o soporte. | Must | 8 | Diseño definido; integración backend pendiente |
| HU-05 | Resumen | Como gerente, quiero visualizar KPIs generales para conocer el estado de la plataforma. | Must | 5 | Implementado en MVP |
| HU-06 | Comercial | Como usuario de negocio, quiero consultar métricas comerciales para analizar conversión, MRR y comportamiento. | Must | 5 | Implementado en MVP |
| HU-07 | Sponsors | Como administrador, quiero listar sponsors para conocer los registros disponibles. | Must | 3 | Implementado en MVP |
| HU-08 | Sponsors | Como administrador, quiero crear, editar y eliminar sponsors para mantener la información actualizada. | Must | 5 | Implementado en modo demo |
| HU-09 | Operativa | Como usuario de operaciones, quiero visualizar servicios y contenedores para conocer su estado. | Must | 5 | Implementado en MVP demo |
| HU-10 | Operativa | Como usuario de operaciones, quiero simular o ejecutar un reinicio controlado para recuperar un servicio. | Should | 5 | Simulado en MVP |
| HU-11 | Usuarios | Como usuario de soporte, quiero buscar usuarios para revisar su información. | Must | 3 | Implementado en MVP |
| HU-12 | Usuarios | Como usuario de soporte, quiero suspender o reactivar un usuario para administrar su acceso. | Must | 5 | Implementado en modo demo |
| HU-13 | Usuarios | Como administrador, quiero cambiar el plan de un usuario para administrar su suscripción. | Should | 3 | Implementado en modo demo |
| HU-14 | Soporte | Como usuario de soporte, quiero gestionar tickets para dar seguimiento a solicitudes. | Must | 5 | Implementado en MVP demo |
| HU-15 | Recorrecciones | Como usuario de soporte, quiero resolver solicitudes de recorrección para gestionar reclamos asociados a preguntas. | Must | 5 | Implementado en MVP demo |
| HU-16 | Tutores | Como administrador, quiero crear, editar, verificar, pausar y reactivar tutores para administrar su participación. | Should | 8 | Implementado en MVP demo |
| HU-17 | Contenido | Como administrador, quiero crear y editar preguntas para mantener actualizado el banco de contenido. | Must | 8 | Implementado en MVP demo |
| HU-18 | Contenido | Como administrador, quiero importar preguntas mediante JSON para acelerar la carga masiva de contenido. | Should | 5 | Implementado en MVP demo |
| HU-19 | Planes | Como usuario autorizado, quiero visualizar y configurar planes y productos para mantener la oferta comercial. | Must | 8 | Implementado en MVP demo |
| HU-20 | Planes | Como usuario autorizado, quiero sincronizar precios con Stripe para mantener consistencia con el servicio externo. | Should | 8 | Integración real pendiente |
| HU-21 | Interfaz | Como administrador, quiero alternar tema claro/oscuro para mejorar la experiencia de uso. | Could | 3 | Considerado en frontend |
| HU-22 | Interfaz | Como administrador, quiero utilizar la consola en español o inglés para facilitar su uso en distintos contextos. | Could | 5 | Considerado en frontend |
| HU-23 | Calidad | Como equipo, quiero generar un build de producción sin errores para validar que el frontend pueda desplegarse. | Must | 3 | Completado |
| HU-24 | Despliegue | Como equipo, quiero publicar el MVP en Vercel para demostrar y validar el sistema remotamente. | Must | 3 | Completado |
| HU-25 | Integración | Como equipo, quiero reemplazar progresivamente los datos simulados por endpoints reales para completar la integración Frontend–Backend. | Must | 8 | Pendiente |
| HU-26 | Calidad | Como equipo, quiero realizar pruebas de integración y seguridad para validar la solución completa. | Must | 8 | Pendiente |

## 3. Criterios generales de aceptación

Una historia se considera aceptada para el MVP frontend cuando:

- la vista o flujo puede ejecutarse sin errores visibles;
- la navegación asociada funciona;
- se validan entradas principales cuando corresponde;
- se verifica el comportamiento esperado en modo demo;
- no se exponen secretos en el frontend;
- el proyecto continúa compilando correctamente con `npm run build`.

## 4. Dependencias

La principal dependencia del Product Backlog es la disponibilidad del backend administrativo.

Para reducir este bloqueo se implementó un modo demostración que desacopla temporalmente el frontend de la API real.

## 5. Evidencias

- MVP desplegado: https://aprueba-admin-flax.vercel.app
- Plan de pruebas: `plan-pruebas.md`
- Arquitectura: `arquitectura-solucion.md`
