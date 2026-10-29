# Requisitos No Funcionales — Aprueba Administración

## 1. Propósito

Los requisitos no funcionales definen atributos de calidad que debe cumplir Aprueba Administración además de sus funcionalidades.

Se consideran principalmente:

- seguridad;
- rendimiento;
- escalabilidad;
- disponibilidad;
- portabilidad;
- mantenibilidad;
- usabilidad;
- compatibilidad.

## 2. Requisitos

### RNF-01 — Seguridad de autenticación

El sistema debe requerir autenticación para acceder a las funcionalidades administrativas.

**Diseño objetivo:**
- correo y contraseña;
- MFA/OTP;
- JWT;
- expiración/control de sesión.

**Estado actual:** autenticación y MFA demostrativos en el MVP; validación real pendiente de integración backend.

---

### RNF-02 — Control de acceso por roles

El sistema debe limitar operaciones según el rol administrativo.

Roles considerados:

- admin / gerencia;
- finance / finanzas;
- ops / operaciones;
- support / soporte.

El backend debe validar permisos antes de ejecutar operaciones sensibles.

**Estado actual:** RBAC definido arquitectónicamente; integración real pendiente.

---

### RNF-03 — Protección de datos y secretos

El frontend no debe contener secretos de Firebase Admin, Stripe ni credenciales privadas del servidor.

Los secretos deben mantenerse mediante variables de entorno en el backend o plataforma de despliegue.

El frontend no debe acceder directamente a Firestore para operaciones administrativas sensibles.

---

### RNF-04 — Rendimiento

La interfaz debe mantener una navegación fluida y evitar cargas innecesarias.

Objetivos de diseño:

- utilizar componentes reutilizables;
- utilizar gráficos ligeros;
- generar build optimizado mediante Vite;
- evitar solicitudes repetidas cuando no sean necesarias;
- utilizar paginación en conjuntos de datos grandes cuando se integre la API real.

**Estado actual:** build de producción validado; pruebas de carga pendientes.

---

### RNF-05 — Escalabilidad

La solución debe permitir que frontend, backend y persistencia evolucionen de manera independiente.

La comunicación se realiza mediante API REST versionada:

```text
/api/v1/admin
```

Firestore se utiliza como modelo documental orientado a consultas.

**Estado actual:** arquitectura definida; validación de carga/escalabilidad pendiente.

---

### RNF-06 — Disponibilidad

El frontend debe estar disponible mediante un despliegue web accesible remotamente.

**Implementación actual:** Vercel.

MVP:

https://aprueba-admin-flax.vercel.app

No se declara un SLA productivo mientras el sistema se encuentre en etapa MVP.

---

### RNF-07 — Portabilidad

El proyecto debe poder ejecutarse en un entorno de desarrollo con Node.js y npm.

Frontend:

```bash
npm install
npm run dev
```

La portabilidad mediante Docker se considera como diseño/propuesta, pero actualmente no existen Dockerfile ni Docker Compose funcionales en el repositorio del MVP.

**Estado actual:** ejecución mediante Node/npm; Docker pendiente.

---

### RNF-08 — Mantenibilidad

La solución debe mantener separación de responsabilidades entre:

- presentación;
- acceso a datos;
- lógica de negocio;
- seguridad;
- persistencia.

Se utilizan Git y GitHub para control de versiones.

Se recomienda mantener:

- componentes reutilizables;
- nombres claros;
- módulos separados;
- documentación técnica;
- variables de entorno;
- archivos `.gitignore`.

---

### RNF-09 — Usabilidad

La consola debe mantener:

- navegación consistente;
- títulos y acciones comprensibles;
- formularios claros;
- mensajes de error;
- confirmaciones en acciones sensibles;
- tema claro/oscuro;
- soporte ES/EN cuando corresponda.

---

### RNF-10 — Compatibilidad

El frontend debe funcionar en navegadores web modernos.

Navegadores utilizados para validación del MVP:

- Google Chrome;
- Microsoft Edge.

---

### RNF-11 — Auditoría

Las acciones administrativas sensibles deben poder quedar registradas para mantener trazabilidad.

Ejemplos:

- suspensión de usuario;
- cambios de plan;
- resolución de recorrecciones;
- cambios en contenido;
- operaciones sobre servicios.

**Estado actual:** requisito definido; persistencia real de auditoría depende del backend.

---

### RNF-12 — Integridad del contrato API

Las respuestas de la API administrativa deben mantener una estructura consistente.

Formato definido:

```json
{
  "data": {},
  "error": null,
  "meta": {}
}
```

Esto reduce el acoplamiento entre frontend y backend.

## 3. Resumen de estado

| Área | Estado |
|---|---|
| Seguridad | Diseñada; integración real parcial/pendiente |
| Rendimiento | Build optimizado validado; carga pendiente |
| Escalabilidad | Arquitectura preparada; pruebas pendientes |
| Disponibilidad | MVP desplegado en Vercel |
| Portabilidad | Node/npm disponible; Docker pendiente |
| Mantenibilidad | Separación de responsabilidades y Git |
| Usabilidad | Validada funcionalmente en MVP |
| Compatibilidad | Validación principal en Chrome/Edge |
