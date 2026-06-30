# [service-name]

> **PLANTILLA** — Copiar esta carpeta a `services/<nombre-del-servicio>/` y reemplazar todos los campos marcados.
>
> Estado: 🟢 Completo | Última actualización: YYYY-MM-DD
> Autor: Nombre Apellido | Equipo: Nombre del equipo

## Propósito

Describir brevemente la finalidad del microservicio y el problema de negocio que resuelve.

> Ejemplo: Gestiona la planificación y administración de horarios académicos del Sistema de Gestión de Horarios SENA.

---

# Responsabilidad

Definir las responsabilidades funcionales del microservicio.

Incluir únicamente aquellas capacidades que pertenecen a este servicio y que no deben ser implementadas por otros microservicios.

---

# Bounded Context

Identificar el contexto de negocio (Bounded Context) al que pertenece el microservicio.

Indicar claramente sus límites funcionales y las responsabilidades que quedan fuera de su alcance.

---

# Funcionalidades principales

Enumerar las funcionalidades principales proporcionadas por el servicio.

Ejemplo:

- Gestión de ...
- Administración de ...
- Consulta de ...
- Validación de ...
- Publicación de eventos ...

---

# Dependencias

Relacionar únicamente los servicios con los que exista comunicación directa.

| Servicio | Tipo de comunicación | Motivo |
|-----------|----------------------|--------|
| Pendiente | REST / Eventos | Pendiente |

---

# Base de datos

Documentar la estrategia de persistencia del servicio.

Información recomendada:

- Motor de base de datos.
- Propiedad exclusiva de los datos.
- Estrategia de migraciones.
- Consideraciones relevantes de persistencia.

---

# APIs expuestas

Describir de forma general las APIs ofrecidas por el microservicio.

La especificación detallada deberá mantenerse en `api-contract.md`.

---

# Eventos

Indicar si el servicio:

- publica eventos;
- consume eventos;
- no participa en comunicación asíncrona.

La documentación detallada deberá mantenerse en `events.md`.

---

# Seguridad

Documentar los mecanismos generales de seguridad utilizados por el servicio.

Ejemplos:

- Autenticación.
- Autorización.
- Validación de permisos.
- Comunicación segura.

---

# Observabilidad

Indicar las capacidades de monitoreo implementadas.

Ejemplos:

- Logging.
- Métricas.
- Health Checks.
- Trazabilidad.
- Auditoría.

---

# Consideraciones de arquitectura

Registrar cualquier decisión arquitectónica relevante para comprender el funcionamiento del microservicio.

Cuando exista un ADR asociado, deberá referenciarse.

---

# Documentación relacionada

| Documento | Descripción |
|------------|-------------|
| api-contract.md | Contrato funcional de la API. |
| data-model.md | Modelo de datos del microservicio. |
| events.md | Eventos publicados y consumidos. |

---

# Enlaces

| Recurso | Ubicación |
|----------|-----------|
| Repositorio | Pendiente |
| OpenAPI / Swagger | Pendiente |
| ADR relacionados | Pendiente |
| Tablero del proyecto | Pendiente |
| Pipeline CI/CD | Pendiente |

---

# Observaciones

Este documento constituye la página principal de la documentación del microservicio y debe mantenerse sincronizado con el resto de la documentación técnica durante todo su ciclo de vida.