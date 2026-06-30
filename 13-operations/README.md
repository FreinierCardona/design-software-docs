# Operaciones

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo DevOps
> Equipo: DevOps, Operaciones e Infraestructura

## Propósito

Esta sección centraliza la documentación relacionada con la operación del Sistema de Gestión de Horarios SENA una vez los componentes han sido desplegados en los diferentes ambientes.

Su objetivo es establecer los lineamientos para el monitoreo, la observabilidad, la gestión de incidentes y la recuperación del sistema, garantizando la continuidad del servicio, la disponibilidad de los componentes y una respuesta oportuna ante eventos operativos.

La documentación aquí contenida constituye la referencia para los equipos responsables de la operación, soporte, infraestructura y arquitectura.

---

# Objetivos

La documentación de operaciones permite:

- Definir la estrategia de monitoreo del sistema.
- Documentar la gestión de incidentes.
- Establecer procedimientos de recuperación.
- Garantizar la continuidad operativa.
- Facilitar el diagnóstico de fallos.
- Mejorar la disponibilidad del sistema.
- Mantener trazabilidad sobre los eventos operativos.

---

# Alcance

Esta sección documenta:

- Observabilidad.
- Monitoreo.
- Gestión de incidentes.
- Recuperación del servicio.
- Estrategia de respaldos.
- Continuidad operativa.
- Procedimientos generales de operación.

No incluye configuraciones específicas de infraestructura, scripts operativos ni información sensible de los ambientes.

---

# Principios

La operación del sistema deberá fundamentarse en los siguientes principios:

- Disponibilidad.
- Confiabilidad.
- Observabilidad.
- Recuperación controlada.
- Automatización cuando sea posible.
- Seguridad operativa.
- Trazabilidad.
- Mejora continua.

---

# Organización

```text
13-operations/
│
├── README.md
├── observability.md
├── incident-management.md
└── backup-and-recovery.md
```

---

# Responsabilidades

La operación del sistema involucra diferentes equipos con responsabilidades complementarias.

| Equipo | Responsabilidad |
|---------|-----------------|
| DevOps | Operación de la plataforma, despliegues y monitoreo de infraestructura. |
| Operaciones | Supervisión diaria del servicio y atención de eventos operativos. |
| Arquitectura | Definición de lineamientos técnicos y apoyo en incidentes de alto impacto. |
| Desarrollo | Corrección de defectos identificados durante la operación. |
| QA | Validación de correcciones cuando sea necesario. |

---

# Relación con la arquitectura

La documentación operativa deberá mantenerse alineada con:

- Arquitectura basada en microservicios.
- Estrategia de observabilidad.
- Arquitectura de despliegue.
- Estrategia DevOps.
- Documentación de microservicios.
- ADR (Architecture Decision Records).

---

# Archivos relacionados

| Archivo | Descripción | Estado |
|----------|-------------|--------|
| observability.md | Estrategia de monitoreo, métricas, registros, trazabilidad distribuida y alertas. | 🟢 |
| incident-management.md | Clasificación, gestión, escalamiento y seguimiento de incidentes operativos. | 🟢 |
| backup-and-recovery.md | Estrategia de respaldo, recuperación del servicio y continuidad operativa. | 🟢 |

---

# Relación con otros documentos

Esta sección complementa la documentación disponible en:

- DevOps.
- Microservicios.
- Arquitectura del sistema.
- ADR.
- Seguridad.
- Calidad.
- Documentación de despliegue.

---

# Mantenimiento

La documentación de operaciones deberá actualizarse cuando exista alguno de los siguientes cambios:

- modificación de la estrategia de monitoreo;
- incorporación de nuevos mecanismos de observabilidad;
- cambios en los procedimientos de recuperación;
- actualización de políticas de respaldo;
- modificación de la arquitectura operativa;
- incorporación de nuevos servicios al sistema.

Toda actualización deberá mantenerse alineada con la arquitectura, la estrategia DevOps y las políticas de continuidad operativa definidas para el Sistema de Gestión de Horarios SENA.