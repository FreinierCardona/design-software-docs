# Runbook

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura de Software

## Propósito

Este documento establece la estructura para documentar los procedimientos operativos de un microservicio del Sistema de Gestión de Horarios SENA.

El Runbook sirve como guía para la operación, monitoreo, mantenimiento y recuperación del servicio durante todo su ciclo de vida, facilitando la atención de incidentes y asegurando la continuidad operativa.

---

# Objetivos

La documentación operativa debe permitir:

- Comprender cómo operar el microservicio.
- Facilitar actividades de soporte.
- Estandarizar procedimientos.
- Reducir tiempos de recuperación.
- Documentar escenarios de contingencia.
- Apoyar la continuidad del servicio.

---

# Información general

Cada Runbook deberá incluir como mínimo:

- Nombre del microservicio.
- Descripción funcional.
- Equipo responsable.
- Ambientes disponibles.
- Contactos de soporte.
- Documentación relacionada.

---

# Requisitos operativos

Documentar los requisitos necesarios para la correcta operación del servicio, incluyendo cuando aplique:

- Infraestructura requerida.
- Dependencias externas.
- Recursos necesarios.
- Configuración general.
- Consideraciones de disponibilidad.

---

# Despliegue

Describir el procedimiento general para desplegar el microservicio.

Debe indicar:

- Prerrequisitos.
- Flujo de despliegue.
- Validaciones posteriores.
- Estrategia de reversión (Rollback).
- Consideraciones de versionamiento.

No incluir comandos específicos ni configuraciones sensibles.

---

# Monitoreo

Documentar los mecanismos utilizados para supervisar el servicio.

Incluir cuando corresponda:

- Health Checks.
- Métricas.
- Logs.
- Alertas.
- Indicadores operativos.
- Trazabilidad distribuida.

---

# Operación diaria

Registrar las actividades habituales necesarias para mantener el servicio operativo.

Ejemplos:

- Verificación de disponibilidad.
- Revisión de alertas.
- Validación de procesos programados.
- Seguimiento de métricas.
- Revisión de integraciones.

---

# Gestión de incidentes

Documentar los procedimientos generales para atender incidentes relacionados con el servicio.

Incluir:

- Identificación del incidente.
- Evaluación del impacto.
- Diagnóstico inicial.
- Acciones de mitigación.
- Escalamiento.
- Recuperación.
- Validación posterior.

---

# Recuperación ante fallos

Describir las estrategias disponibles para recuperar la operación del microservicio.

Cuando aplique documentar:

- Reinicio controlado.
- Recuperación del servicio.
- Restauración de datos.
- Recuperación de integraciones.
- Validaciones posteriores.

---

# Mantenimiento

Registrar los procedimientos relacionados con:

- Actualizaciones.
- Cambios de configuración.
- Mantenimiento preventivo.
- Mantenimiento correctivo.
- Actividades programadas.

---

# Dependencias operativas

Identificar los componentes cuya disponibilidad afecta el funcionamiento del microservicio.

Ejemplos:

- Otros microservicios.
- Base de datos.
- Broker de eventos.
- Servicio de autenticación.
- Almacenamiento.
- Servicios externos.

---

# Riesgos conocidos

Documentar los principales riesgos operativos identificados para el servicio.

Cuando aplique incluir:

- Limitaciones.
- Puntos críticos.
- Escenarios de indisponibilidad.
- Consideraciones de capacidad.

---

# Relación con otros documentos

Este documento complementa:

- README del microservicio.
- API Contract.
- Data Model.
- Events.
- ADR.
- Arquitectura del sistema.
- Documentación de DevOps.
- Documentación de Observabilidad.

---

# Buenas prácticas

El Runbook deberá:

- mantenerse actualizado con cada cambio operativo relevante;
- describir procedimientos claros y verificables;
- evitar información duplicada con otros documentos;
- no contener credenciales, secretos ni información sensible;
- reflejar el estado operativo vigente del microservicio.

---

# Observaciones

Este documento corresponde a una plantilla de documentación y deberá adaptarse a las necesidades operativas de cada microservicio. Toda modificación en los procedimientos de despliegue, monitoreo o recuperación deberá reflejarse oportunamente para mantener la documentación alineada con la operación real del Sistema de Gestión de Horarios SENA.