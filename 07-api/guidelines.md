# API Guidelines

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

## Propósito

Este documento define los lineamientos de diseño de las APIs del Sistema de Gestión de Horarios SENA (SGH SENA).

Su objetivo es garantizar que todos los microservicios expongan interfaces consistentes, predecibles, mantenibles y fáciles de consumir, independientemente del equipo que las implemente.

Estas reglas son de obligatorio cumplimiento para todos los servicios del proyecto.

---

# Principios de diseño

Todas las APIs deberán cumplir los siguientes principios:

- Arquitectura REST.
- Bajo acoplamiento entre servicios.
- Recursos claramente identificables.
- Operaciones idempotentes cuando aplique.
- Versionamiento explícito.
- Contratos documentados mediante OpenAPI 3.x.
- DTOs independientes del modelo de dominio.
- Respuestas consistentes.
- Validación de datos de entrada.
- Manejo uniforme de errores.

---

# Convención de URLs

Todas las rutas deberán iniciar con:

```
/api/v1
```

Ejemplos:

```
GET    /api/v1/instructores
GET    /api/v1/fichas
POST   /api/v1/horarios
PUT    /api/v1/ambientes/{id}
DELETE /api/v1/programas/{id}
```

---

# Convención de nombres

Se utilizarán nombres en plural para representar recursos.

Correcto:

```
/usuarios
/programas
/instructores
/ambientes
/horarios
```

Incorrecto:

```
/getUsuarios
/createHorario
/deleteFicha
```

Las URLs representan recursos, no acciones.

---

# Métodos HTTP

| Método | Uso |
|---------|-----|
| GET | Consultar recursos |
| POST | Crear recursos |
| PUT | Actualizar completamente un recurso |
| PATCH | Actualización parcial |
| DELETE | Eliminar un recurso |

---

# Versionamiento

Todas las APIs deberán exponer su versión en la URL.

Ejemplo:

```
/api/v1
```

Cambios incompatibles requerirán una nueva versión.

Ejemplo:

```
/api/v2
```

---

# Formato de intercambio

Las APIs intercambiarán información únicamente en formato JSON.

Ejemplo:

```json
{
    "id": "UUID",
    "nombre": "Programación de Software"
}
```

---

# Identificadores

Los recursos utilizarán UUID como identificador principal.

Ejemplo:

```
GET /api/v1/programas/{uuid}
```

---

# Códigos HTTP

| Código | Significado |
|---------|-------------|
| 200 OK | Consulta exitosa |
| 201 Created | Recurso creado |
| 204 No Content | Operación exitosa sin contenido |
| 400 Bad Request | Error de validación |
| 401 Unauthorized | No autenticado |
| 403 Forbidden | Sin permisos |
| 404 Not Found | Recurso inexistente |
| 409 Conflict | Conflicto de negocio |
| 422 Unprocessable Entity | Validación de reglas de negocio |
| 500 Internal Server Error | Error inesperado |

---

# Formato de respuestas

Respuesta exitosa:

```json
{
    "data": { },
    "message": "Operación realizada correctamente."
}
```

Respuesta con colección:

```json
{
    "data": [ ],
    "total": 120
}
```

Respuesta de error:

```json
{
    "timestamp": "2026-06-30T14:30:00Z",
    "status": 400,
    "error": "Bad Request",
    "message": "La ficha no existe.",
    "path": "/api/v1/fichas/123"
}
```

---

# Paginación

Las consultas que retornen listas deberán soportar paginación.

Parámetros:

```
?page=0
&size=20
&sort=nombre,asc
```

---

# Filtrado

Se utilizarán parámetros de consulta.

Ejemplo:

```
GET /api/v1/instructores?centro=9209
GET /api/v1/horarios?estado=ACTIVO
```

---

# Ordenamiento

Se realizará mediante el parámetro:

```
sort=campo,direccion
```

Ejemplo:

```
sort=nombre,asc
sort=fecha,desc
```

---

# Validaciones

Toda solicitud será validada antes de ejecutar la lógica de negocio.

Las validaciones incluirán:

- Campos obligatorios.
- Longitudes máximas.
- Formatos.
- Tipos de datos.
- Reglas de negocio.

---

# Idempotencia

Las operaciones PUT y DELETE deberán ser idempotentes.

Ejecutar varias veces la misma petición deberá producir el mismo resultado.

---

# Documentación

Toda API deberá disponer de:

- Especificación OpenAPI 3.x.
- DTOs documentados.
- Ejemplos de Request.
- Ejemplos de Response.
- Códigos HTTP.
- Descripción de cada endpoint.

Los contratos oficiales serán publicados en:

```
07-api/contracts/openapi/
```

---

# Compatibilidad

No se podrán realizar cambios incompatibles sobre una API publicada sin crear una nueva versión.

Se consideran cambios incompatibles:

- Eliminar endpoints.
- Renombrar campos.
- Cambiar tipos de datos.
- Modificar códigos HTTP.
- Alterar contratos públicos.

---

# Convenciones generales

Todos los microservicios del SGH SENA deberán:

- Mantener consistencia en la estructura de endpoints.
- Utilizar nombres descriptivos.
- Evitar lógica de negocio en los controladores.
- Mantener separación entre dominio, aplicación e infraestructura.
- Cumplir los contratos OpenAPI aprobados por Arquitectura.
- Garantizar compatibilidad con el ecosistema de microservicios del proyecto.