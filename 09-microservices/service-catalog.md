# Catálogo de Microservicios

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura de Software

## Propósito

Este documento constituye el inventario oficial de los microservicios que conforman la arquitectura del Sistema de Gestión de Horarios SENA.

Su objetivo es proporcionar una visión centralizada de los servicios existentes, sus responsabilidades, propietarios funcionales y técnicos, ubicación de su documentación y estado dentro del ciclo de vida del proyecto.

El catálogo permite identificar rápidamente los límites de cada contexto de negocio y facilita la coordinación entre los diferentes equipos de desarrollo.

---

# Alcance

El catálogo registra para cada microservicio:

- Nombre oficial.
- Contexto de negocio (Bounded Context).
- Responsabilidad principal.
- Equipo responsable.
- Repositorio asociado.
- Estado de desarrollo.
- Estado de la documentación.

No documenta aspectos técnicos internos como APIs, bases de datos o modelos de dominio, los cuales se encuentran en la documentación específica de cada servicio.

---

# Estados del servicio

| Estado | Descripción |
|---------|-------------|
| Planeado | Hace parte de la arquitectura objetivo pero aún no inicia desarrollo. |
| En desarrollo | Se encuentra en construcción activa. |
| En validación | Está siendo probado antes de su liberación. |
| Productivo | Se encuentra desplegado y operativo. |
| Obsoleto | Ha sido reemplazado o retirado de la arquitectura. |

---

# Estados de la documentación

| Estado | Descripción |
|---------|-------------|
| 🟢 Completa | La documentación refleja el estado actual del servicio. |
| 🟡 En actualización | Se encuentra siendo ajustada por cambios recientes. |
| 🔴 Pendiente | La documentación aún no ha sido elaborada. |

---

# Inventario de Microservicios

| Microservicio | Contexto de negocio | Responsabilidad | Equipo responsable | Repositorio | Estado del servicio | Documentación |
|---------------|---------------------|-----------------|-------------------|-------------|---------------------|---------------|
| IAM | Gestión de identidad y acceso | Administración de usuarios, roles, permisos, autenticación y autorización. | Arquitectura / Backend | Pendiente | Planeado | 🟢 |
| Reference Data | Datos maestros | Administración de catálogos y parámetros del sistema. | Arquitectura / Backend | Pendiente | Planeado | 🟢 |
| Academic Management | Gestión académica | Administración de programas, fichas, competencias, RAP y oferta de formación. | Arquitectura / Backend | Pendiente | Planeado | 🟢 |
| Training Environment | Ambientes de formación | Gestión de ambientes, recursos, disponibilidad y reservas. | Arquitectura / Backend | Pendiente | Planeado | 🟢 |
| Scheduling | Gestión de horarios | Planificación de horarios, sesiones, asignaciones y resolución de conflictos. | Arquitectura / Backend | Pendiente | Planeado | 🟢 |
| Actors | Gestión de actores | Administración de instructores, aprendices, empresas y etapa productiva. | Arquitectura / Backend | Pendiente | Planeado | 🟢 |
| Document | Gestión documental | Administración de documentos, plantillas y versiones. | Arquitectura / Backend | Pendiente | Planeado | 🟢 |
| Monitoring | Monitoreo y seguimiento | Indicadores, alertas, notificaciones y planes de mejoramiento. | Arquitectura / Backend | Pendiente | Planeado | 🟢 |
| Audit | Auditoría | Registro de eventos y trazabilidad del sistema mediante auditoría append-only. | Arquitectura / Backend | Pendiente | Planeado | 🟢 |

---

# Lineamientos de actualización

Este catálogo deberá actualizarse cuando ocurra alguno de los siguientes eventos:

- Incorporación de un nuevo microservicio.
- División o consolidación de servicios existentes.
- Cambio de responsabilidades funcionales.
- Cambio de equipo responsable.
- Cambio de repositorio.
- Cambio en el estado del ciclo de vida del servicio.
- Retiro de un microservicio de la arquitectura.

Toda modificación deberá mantenerse sincronizada con la documentación de arquitectura, los ADR y la documentación específica del microservicio.

---

# Relación con otros documentos

Este catálogo se complementa con:

- `README.md` de esta sección.
- `communication-patterns.md`.
- Documentación individual ubicada en `services/`.
- ADR (Architecture Decision Records).
- Arquitectura general del sistema.
- Modelo de dominio.
- Documentación de APIs.

---

# Observaciones

Este documento representa la fuente oficial para conocer el inventario de microservicios del Sistema de Gestión de Horarios SENA.

Ningún microservicio deberá considerarse parte de la arquitectura oficial si no se encuentra registrado y documentado en este catálogo.