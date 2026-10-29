# Product Vision — Aprueba Administración

## 1. Visión del producto

**Aprueba Administración** es una consola web administrativa para la plataforma Aprueba. Su propósito es centralizar en una sola interfaz las tareas de negocio, operación, soporte y administración de contenido que necesitan los usuarios internos de la plataforma.

El producto busca entregar una experiencia administrativa clara, modular y segura, preparada para integrarse mediante API REST con los servicios backend de Aprueba.

## 2. Problema que resuelve

La plataforma Aprueba requiere que distintas áreas internas puedan consultar información y ejecutar acciones administrativas sin depender de intervenciones técnicas directas.

Entre las necesidades principales se encuentran:

- visualizar KPIs y métricas;
- administrar sponsors;
- monitorear servicios y operación;
- consultar y administrar usuarios;
- gestionar tickets y solicitudes de recorrección;
- administrar tutores;
- gestionar preguntas y contenido;
- configurar planes y productos.

Sin una consola administrativa centralizada, estas tareas quedan distribuidas o dependen de procesos técnicos externos, dificultando su control y trazabilidad.

## 3. Usuarios del producto

Los principales usuarios son perfiles administrativos de Aprueba:

- **Gerencia:** consulta indicadores y visión general del negocio.
- **Finanzas:** consulta información comercial, planes y precios.
- **Operaciones:** monitorea servicios y acciones operativas.
- **Soporte:** administra usuarios, tickets y solicitudes de recorrección.

La arquitectura contempla autorización basada en roles o **RBAC**, de modo que cada perfil pueda acceder solamente a las funcionalidades que le correspondan.

## 4. Propuesta de valor

Aprueba Administración entrega una consola centralizada para operar y monitorear la plataforma desde un único punto.

La propuesta de valor se basa en:

- centralización de procesos administrativos;
- separación entre frontend, backend y persistencia;
- navegación modular;
- seguridad mediante autenticación, MFA y roles;
- arquitectura preparada para integración con API REST;
- soporte para español e inglés;
- tema claro y oscuro;
- posibilidad de avanzar y validar el frontend mediante modo demo aunque el backend no esté completamente disponible.

## 5. Alcance del MVP Frontend

El MVP desarrollado por el equipo contempla ocho áreas principales:

1. Resumen / KPIs.
2. Comercial.
3. Sponsors.
4. Operativa.
5. Usuarios y soporte.
6. Tutores.
7. Contenido.
8. Planes y productos.

Además, se validaron funciones representativas como:

- CRUD de sponsors;
- suspensión y reactivación de usuarios;
- cambio de plan;
- gestión de tickets;
- resolución de recorrecciones;
- gestión de tutores;
- creación y edición de preguntas;
- importación masiva mediante JSON;
- configuración de planes y productos.

## 6. Estado actual

El frontend se encuentra disponible como un **MVP funcional en modo demostración**.

El modo demo utiliza:

```text
VITE_DEMO_MODE=true
```

Esto permite validar interfaz, navegación y flujos principales utilizando datos simulados mientras se completa la integración con los servicios backend reales.

## 7. Fuera de alcance actual

En esta etapa no se considera como completado:

- integración completa con backend real;
- persistencia productiva de todas las operaciones en Firestore;
- MFA real de extremo a extremo;
- pruebas completas de seguridad;
- despliegue productivo del backend;
- Docker implementado en el repositorio.

Estos puntos forman parte de las siguientes etapas de integración y endurecimiento de la solución.

## 8. Objetivo del producto

> Desarrollar una consola administrativa centralizada, segura, modular y mantenible que permita gestionar las principales funciones de Aprueba y que pueda evolucionar desde un MVP frontend desacoplado hacia una integración completa con el backend de la plataforma.

## 9. Evidencias

- MVP: https://aprueba-admin-flax.vercel.app
- Repositorio de implementación: https://github.com/nacho055555/Aprueba-Admin
- Repositorio de evidencias: https://github.com/nacho055555/Aprueba-Administracion-
