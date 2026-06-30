# Observability

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo DevOps
> Equipo: DevOps, Operaciones e Infraestructura

## Propósito

Este documento define la estrategia de observabilidad del Sistema de Gestión de Horarios SENA.

Su objetivo es establecer los lineamientos para la recopilación, análisis y utilización de información operativa que permita comprender el comportamiento del sistema, detectar anomalías, facilitar el diagnóstico de incidentes y apoyar la mejora continua de la plataforma.

La observabilidad constituye un componente fundamental de la operación de un sistema basado en microservicios y complementa las actividades de monitoreo, soporte y mantenimiento.

---

# Objetivos

La estrategia de observabilidad busca:

- Detectar fallos de forma temprana.
- Facilitar el diagnóstico de incidentes.
- Medir el estado operativo del sistema.
- Monitorear el comportamiento de los microservicios.
- Mejorar la disponibilidad de la plataforma.
- Proporcionar información para la toma de decisiones.
- Mantener trazabilidad sobre las operaciones del sistema.

---

# Alcance

La estrategia comprende la observación de todos los componentes que conforman la solución, incluyendo:

- Microservicios.
- APIs.
- Procesos de negocio.
- Integraciones.
- Infraestructura asociada.
- Bases de datos.
- Comunicaciones entre servicios.

No incluye configuraciones específicas de herramientas ni procedimientos particulares de monitoreo.

---

# Componentes de la observabilidad

La estrategia se fundamenta en cuatro pilares principales:

| Componente | Propósito |
|------------|-----------|
| Métricas | Medir el comportamiento y desempeño de los componentes del sistema. |
| Logs | Registrar eventos relevantes para auditoría, seguimiento y diagnóstico. |
| Trazas distribuidas | Analizar el recorrido de las solicitudes entre múltiples microservicios. |
| Alertas | Notificar oportunamente condiciones que requieran atención operativa. |

---

# Métricas

Las métricas deberán permitir conocer, entre otros aspectos:

- Disponibilidad de los servicios.
- Tiempo de respuesta.
- Cantidad de solicitudes procesadas.
- Tasas de error.
- Consumo de recursos.
- Estado de los procesos críticos.
- Utilización de componentes.

Las métricas deberán recopilarse de forma consistente para facilitar su comparación entre ambientes.

---

# Registros (Logs)

Todos los componentes deberán generar registros suficientes para permitir:

- seguimiento de operaciones;
- diagnóstico de errores;
- análisis de incidentes;
- auditoría de eventos relevantes;
- trazabilidad de solicitudes.

Los registros deberán mantenerse estructurados, ser consistentes y evitar la exposición de información sensible.

---

# Trazabilidad distribuida

Debido a la arquitectura basada en microservicios, deberá mantenerse la capacidad de seguir una solicitud durante todo su recorrido entre los diferentes servicios.

La información de trazabilidad permitirá:

- identificar cuellos de botella;
- localizar fallos;
- comprender dependencias entre componentes;
- facilitar el análisis de problemas complejos.

---

# Alertas

Las alertas deberán configurarse para notificar situaciones que puedan afectar la operación del sistema.

Como principio general, deberán priorizarse eventos relacionados con:

- indisponibilidad de servicios;
- degradación del rendimiento;
- incremento de errores;
- fallos en procesos críticos;
- problemas de integración;
- condiciones que puedan comprometer la continuidad del servicio.

---

# Tableros de monitoreo

La información recopilada podrá organizarse mediante tableros que permitan visualizar el estado general del sistema.

Los tableros deberán facilitar:

- seguimiento operativo;
- análisis histórico;
- identificación de tendencias;
- apoyo en la toma de decisiones;
- supervisión de indicadores clave.

---

# Responsabilidades

| Equipo | Responsabilidad |
|---------|-----------------|
| DevOps | Definir y mantener la estrategia de observabilidad. |
| Operaciones | Supervisar el comportamiento del sistema y atender alertas. |
| Desarrollo | Incorporar capacidades de observabilidad en los microservicios. |
| Arquitectura | Definir los lineamientos técnicos y validar su cumplimiento. |

---

# Buenas prácticas

La observabilidad del sistema deberá:

- formar parte del diseño de cada microservicio;
- mantenerse consistente entre todos los componentes;
- minimizar el impacto sobre el rendimiento;
- proporcionar información útil para el diagnóstico;
- evitar registrar datos sensibles;
- evolucionar junto con la arquitectura del sistema.

---

# Relación con otros documentos

Este documento complementa:

- `README.md` de Operaciones.
- `incident-management.md`.
- `backup-and-recovery.md`.
- Documentación de DevOps.
- Documentación de microservicios.
- Arquitectura del sistema.
- ADR (Architecture Decision Records).

---

# Mantenimiento

La estrategia de observabilidad deberá actualizarse cuando ocurra alguno de los siguientes cambios:

- incorporación de nuevos microservicios;
- modificación de la arquitectura;
- actualización de indicadores operativos;
- cambios en la estrategia de monitoreo;
- incorporación de nuevos mecanismos de trazabilidad o análisis.

Toda actualización deberá mantenerse alineada con la arquitectura, la estrategia DevOps y las políticas operativas del Sistema de Gestión de Horarios SENA.