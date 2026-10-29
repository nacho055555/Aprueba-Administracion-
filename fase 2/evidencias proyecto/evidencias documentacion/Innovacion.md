# Innovación y Valor Diferencial — Aprueba Administración

## 1. Problema abordado

Aprueba requiere administrar procesos de negocio, soporte, operación, contenido y productos desde una solución centralizada.

Aprueba Administración busca reducir la dependencia de intervenciones técnicas y concentrar las operaciones en una única consola web.

## 2. Valor agregado

El valor del proyecto no se limita a mostrar información.

La consola integra en un mismo entorno:

- KPIs y métricas;
- gestión comercial;
- sponsors;
- monitoreo operacional;
- usuarios y soporte;
- tutores;
- contenido;
- planes y productos.

Esto permite que diferentes perfiles administrativos trabajen sobre una misma solución, manteniendo responsabilidades y permisos diferenciados.

## 3. Elementos de innovación del producto

### 3.1 Administración centralizada

La solución reúne distintos dominios administrativos que normalmente podrían encontrarse separados.

Esto mejora:

- visibilidad;
- consistencia;
- trazabilidad;
- rapidez de operación.

### 3.2 Seguridad basada en roles

La arquitectura contempla:

- MFA;
- JWT;
- claims;
- RBAC.

Esto permite diseñar accesos diferentes para gerencia, finanzas, operaciones y soporte.

### 3.3 Gestión de contenido mediante JSON

La importación masiva de preguntas mediante JSON reduce el trabajo manual necesario para incorporar contenido al banco de preguntas.

### 3.4 Integración de negocio y operación

La misma consola permite representar información comercial y también información operacional de servicios.

Esto genera una visión más completa del funcionamiento de Aprueba.

### 3.5 Arquitectura desacoplada

El frontend utiliza una API REST como contrato de comunicación y no depende directamente de Firestore.

Esto permite evolucionar la interfaz y el backend de forma más independiente.

## 4. Innovación en el proceso de desarrollo

Una decisión relevante fue implementar un **modo demo desacoplado**:

```text
VITE_DEMO_MODE=true
```

El backend administrativo era una dependencia externa al equipo Frontend.

En lugar de detener el desarrollo, el modo demo permitió:

- desarrollar las vistas;
- validar navegación;
- probar formularios;
- demostrar funcionalidades;
- desplegar el MVP;
- preparar posteriormente la sustitución de mocks por servicios reales.

Este enfoque disminuyó el bloqueo entre equipos y permitió obtener evidencia funcional antes de completar la integración.

## 5. Diferenciadores del MVP

El MVP incluye en una sola consola:

- ocho módulos administrativos;
- tema claro/oscuro;
- soporte ES/EN;
- gráficos y KPIs;
- CRUD de sponsors;
- administración de usuarios;
- soporte y recorrecciones;
- gestión de tutores;
- gestión e importación de preguntas;
- configuración de planes;
- preparación para Stripe;
- despliegue público en Vercel.

## 6. Evolución futura

Para aumentar el valor del producto se considera:

- integración completa con backend;
- persistencia real;
- auditoría;
- observabilidad;
- pruebas de integración y seguridad;
- automatización de despliegue;
- Dockerización si se adopta como estándar de portabilidad.

## 7. Evidencia

MVP:

https://aprueba-admin-flax.vercel.app
