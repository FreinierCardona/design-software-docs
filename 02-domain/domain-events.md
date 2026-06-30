# Domain Events

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

## Propósito

Los eventos de dominio representan hechos relevantes que ocurren dentro del negocio y reflejan un cambio de estado significativo en alguna entidad del Sistema de Gestión de Horarios SENA.

Estos eventos permiten describir la interacción entre los diferentes módulos del sistema sin acoplar directamente sus responsabilidades, facilitando una arquitectura basada en microservicios y principios de Domain-Driven Design (DDD).

> **Importante:** Los eventos aquí descritos representan sucesos del negocio. La implementación técnica (mensajería, colas, brokers o mecanismos de publicación) se documenta en la arquitectura de software, no en este documento.

---

# Eventos del dominio

## Gestión Académica

| Evento | Descripción |
|---------|-------------|
| ProgramaCreado | Se registra un nuevo programa de formación en el sistema. |
| FichaCreada | Se crea una nueva ficha de formación asociada a un programa. |
| OfertaPublicada | Una oferta de formación queda disponible para planificación. |
| CompetenciaActualizada | Se modifica la información de una competencia del programa. |

---

## Gestión de Actores

| Evento | Descripción |
|---------|-------------|
| InstructorRegistrado | Un instructor queda habilitado dentro del sistema. |
| InstructorActualizado | Se modifica la información del instructor. |
| AprendizRegistrado | Un aprendiz es asociado a una ficha de formación. |
| EmpresaVinculada | Una empresa queda registrada para procesos de etapa productiva. |

---

## Gestión de Ambientes

| Evento | Descripción |
|---------|-------------|
| AmbienteRegistrado | Se crea un nuevo ambiente de formación. |
| AmbienteActualizado | Se modifican las características del ambiente. |
| AmbienteDisponible | El ambiente puede ser utilizado para programación. |
| AmbienteFueraDeServicio | El ambiente queda indisponible por mantenimiento o novedad. |

---

## Gestión de Horarios

| Evento | Descripción |
|---------|-------------|
| HorarioCreado | Se genera un nuevo horario académico. |
| HorarioActualizado | Se modifica una programación existente. |
| SesionProgramada | Una sesión de formación queda asignada dentro del horario. |
| AsignacionRealizada | Se asigna instructor y ambiente a una sesión. |
| ConflictoDetectado | El sistema identifica una inconsistencia en la programación. |
| HorarioPublicado | El horario queda disponible para consulta de los usuarios. |

---

## Gestión Documental

| Evento | Descripción |
|---------|-------------|
| DocumentoRegistrado | Se incorpora un nuevo documento al sistema. |
| VersionDocumentoCreada | Se genera una nueva versión de un documento existente. |
| PlantillaActualizada | Se modifica una plantilla institucional. |

---

## Seguimiento

| Evento | Descripción |
|---------|-------------|
| IndicadorActualizado | Se recalcula un indicador de seguimiento. |
| AlertaGenerada | El sistema identifica una situación que requiere atención. |
| PlanMejoramientoCreado | Se registra un nuevo plan de mejoramiento. |
| SeguimientoRegistrado | Se almacena una nueva sesión de seguimiento. |

---

## Seguridad

| Evento | Descripción |
|---------|-------------|
| UsuarioRegistrado | Se crea una nueva cuenta de usuario. |
| RolAsignado | Se asigna un rol a un usuario. |
| PermisosActualizados | Se modifican los permisos asociados a un rol. |
| SesionIniciada | Un usuario inicia sesión correctamente. |
| SesionFinalizada | Finaliza la sesión activa del usuario. |

---

## Auditoría

| Evento | Descripción |
|---------|-------------|
| RegistroAuditado | Se almacena un nuevo registro de auditoría derivado de una operación del sistema. |

---

# Consideraciones

- Los eventos representan cambios de negocio y no operaciones técnicas de base de datos.
- Un evento puede ser producido por un único módulo y consumido por uno o varios módulos.
- Todo evento debe representar un hecho ya ocurrido y no una intención futura.
- Los nombres de los eventos utilizan tiempo pasado para indicar que la acción ya fue completada.
- La definición detallada de los mensajes, contratos o mecanismos de integración se documenta en la arquitectura de integración del proyecto.