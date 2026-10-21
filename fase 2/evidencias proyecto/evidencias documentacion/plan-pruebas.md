# Plan de Pruebas — MVP Aprueba Administración

## 1. Objetivo
Validar que el MVP del frontend administrativo permita navegar y ejecutar correctamente los principales flujos definidos para Aprueba Administración.

El MVP actual usa `VITE_DEMO_MODE=true`, por lo que estas pruebas validan principalmente interfaz, navegación, comportamiento funcional, formularios, acciones simuladas, build y despliegue.

## 2. Entorno de pruebas
- Desarrollo local: `npm run dev`
- Build: `npm run build`
- Producción: https://aprueba-admin-flax.vercel.app
- Navegadores: Chrome y Edge actuales.

## 3. Credenciales demo
```text
Correo: admin@aprueba.cl
Contraseña: admin123
MFA: 123456
```

## 4. Casos de prueba
| ID | Módulo | Caso | Resultado esperado | Estado |
|---|---|---|---|---|
| CP-01 | Login | Credenciales válidas | Acceso al panel | Aprobado |
| CP-02 | Login | Contraseña incorrecta | Acceso rechazado | Aprobado |
| CP-03 | Login | MFA incorrecto | Autenticación rechazada | Aprobado |
| CP-04 | Navegación | Recorrer 8 vistas | Todas cargan correctamente | Aprobado |
| CP-05 | Resumen | Abrir dashboard | KPIs y gráficos visibles | Aprobado |
| CP-06 | Comercial | Abrir métricas | KPIs y visualizaciones visibles | Aprobado |
| CP-07 | Sponsors | Crear sponsor | Registro aparece en lista | Aprobado |
| CP-08 | Sponsors | Editar sponsor | Cambios visibles | Aprobado |
| CP-09 | Sponsors | Eliminar sponsor | Registro desaparece | Aprobado |
| CP-10 | Operativa | Reiniciar contenedor | Estado cambia en modo demo | Aprobado |
| CP-11 | Usuarios | Suspender usuario | Estado suspendido | Aprobado |
| CP-12 | Usuarios | Reactivar usuario | Estado activo | Aprobado |
| CP-13 | Usuarios | Cambiar plan | Plan actualizado | Aprobado |
| CP-14 | Tickets | Modificar ticket | Estado/prioridad actualizados | Aprobado |
| CP-15 | Recorrecciones | Confirmar | Se resuelve y se entregan 250 medallas | Aprobado |
| CP-16 | Tutores | Crear/editar | Cambios visibles | Aprobado |
| CP-17 | Tutores | Verificar/pausar/reactivar | Estado correcto | Aprobado |
| CP-18 | Contenido | Crear pregunta | Se crea como borrador | Aprobado |
| CP-19 | Contenido | Editar/publicar | Estado actualizado | Aprobado |
| CP-20 | Contenido | Importar JSON | Preguntas agregadas | Aprobado |
| CP-21 | Planes | Agregar/editar/eliminar | Operación reflejada | Aprobado |
| CP-22 | Producción | Ejecutar build | `dist` generado sin errores | Aprobado |
| CP-23 | Vercel | Abrir app desplegada | MVP carga correctamente | Aprobado |
| CP-24 | Router | Actualizar ruta interna con F5 | Sin error 404 | Aprobado |

## 5. Importación JSON
Ejemplo:
```json
[
  {
    "pregunta": "¿Cuánto es 15 + 7?",
    "alternativas": ["20", "21", "22", "23"],
    "respuesta_correcta": "C",
    "eje": "Números",
    "dificultad": "d1"
  }
]
```

Resultado esperado: JSON válido, pregunta importada y visible en la lista.

## 6. Pruebas de build
Comando: `npm run build`

Resultado esperado: Vite finaliza correctamente y genera `dist/`.

## 7. Prueba de rutas SPA en Vercel
1. ingresar al sistema;
2. navegar a una ruta interna, por ejemplo `/usuarios`;
3. actualizar con F5;
4. comprobar que no aparece error 404.

Estado: **Aprobado**.

## 8. Limitaciones conocidas
- los datos demo no son información real;
- algunas modificaciones desaparecen al recargar;
- no existe persistencia real en Firestore durante el modo demo;
- integración con backend real pendiente;
- pruebas de seguridad de extremo a extremo pendientes.

## 9. Próximas pruebas
- integración Frontend–Backend;
- JWT real;
- RBAC por rol;
- MFA real;
- persistencia Firestore;
- errores HTTP y timeouts;
- auditoría;
- seguridad y carga.

## 10. Evidencias
**MVP:** https://aprueba-admin-flax.vercel.app  
**Repositorio:** https://github.com/nacho055555/Aprueba-Admin
