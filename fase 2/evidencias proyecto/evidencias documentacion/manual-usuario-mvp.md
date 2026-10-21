# Manual de Usuario — MVP Aprueba Administración

## 1. Descripción
Aprueba Administración es una consola web destinada a la gestión y monitoreo de la plataforma Aprueba. Este manual corresponde al **MVP Frontend en modo demostración**.

## 2. Acceso
**URL:** https://aprueba-admin-flax.vercel.app

Credenciales demo:
```text
Correo: admin@aprueba.cl
Contraseña: admin123
MFA: 123456
```

## 3. Menú principal
La consola incluye:
1. Resumen
2. Comercial
3. Sponsors
4. Operativa
5. Usuarios y soporte
6. Tutores
7. Contenido
8. Planes y productos

También considera tema claro/oscuro e idioma ES/EN.

## 4. Resumen
Presenta KPIs, tendencias, recaudación y estado general del sistema.

## 5. Comercial
Permite visualizar descargas, DAU, MAU, convertidos, tasa de conversión, MRR, embudo, recaudación y medallas.

## 6. Sponsors
Funciones:
- listar;
- agregar;
- editar;
- eliminar.

## 7. Operativa
Incluye plataformas, servicios, contenedores, CPU, memoria y estado. El reinicio de contenedores se simula en modo demo.

## 8. Usuarios y soporte
Permite:
- buscar usuarios;
- cambiar plan;
- suspender/reactivar;
- gestionar tickets;
- resolver recorrecciones.

Una recorrección confirmada puede otorgar **250 medallas de bronce** en el flujo demo.

## 9. Tutores
Funciones:
- listar y buscar;
- crear y editar;
- verificar/desverificar;
- destacar;
- pausar/reactivar;
- eliminar;
- moderar reseñas.

## 10. Contenido
Permite:
- listar y filtrar preguntas;
- crear;
- editar;
- publicar;
- importar JSON.

## 11. Ejemplo de importación JSON
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

## 12. Planes y productos
Permite visualizar, agregar, editar y eliminar planes, modificar límites y asignar características.

## 13. Limitaciones del MVP
El sistema funciona con `VITE_DEMO_MODE=true`.

Esto significa:
- los datos no son productivos;
- varias acciones son simuladas;
- los cambios pueden desaparecer al actualizar;
- la integración completa con backend está pendiente;
- no debe utilizarse como entorno productivo real.

## 14. Próximos pasos
- integrar API real;
- persistir cambios en Firestore;
- validar JWT y MFA reales;
- validar permisos RBAC;
- completar pruebas de integración;
- reforzar auditoría y mantenibilidad.

## 15. Evidencias
**Aplicación:** https://aprueba-admin-flax.vercel.app  
**Repositorio:** https://github.com/nacho055555/Aprueba-Admin
