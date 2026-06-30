# Incident Management

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo DevOps
> Equipo: DevOps, Operaciones e Infraestructura

## Propósito

Este documento establece la estrategia de gestión de incidentes del Sistema de Gestión de Horarios SENA.

Su objetivo es definir los lineamientos para la identificación, clasificación, atención, escalamiento, resolución y seguimiento de incidentes que puedan afectar la disponibilidad, estabilidad, seguridad o funcionamiento del sistema.

La gestión de incidentes busca restaurar la operación normal del servicio en el menor tiempo posible, minimizando el impacto sobre los usuarios y garantizando la trazabilidad de todas las acciones realizadas.

---

# Objetivos

La estrategia de gestión de incidentes busca:

- Detectar oportunamente eventos que afecten el sistema.
- Reducir el tiempo de recuperación del servicio.
- Minimizar el impacto sobre la operación.
- Definir responsabilidades claras durante la atención.
- Garantizar una comunicación adecuada entre los equipos.
- Mantener trazabilidad sobre los incidentes.
- Favorecer la mejora continua mediante el análisis de causas.

---

# Alcance

La estrategia aplica a incidentes relacionados con:

- Disponibilidad de microservicios.
- Integraciones entre servicios.
- APIs.
- Infraestructura de soporte.
- Bases de datos.
- Procesos críticos del negocio.
- Despliegues.
- Componentes compartidos.

No contempla la gestión de solicitudes de cambio, nuevas funcionalidades o requerimientos evolutivos.

---

# Definición de incidente

Se considera incidente cualquier evento no planificado que provoque o pueda provocar una interrupción, degradación o comportamiento anómalo de uno o varios componentes del Sistema de Gestión de Horarios SENA.

---

# Clasificación

Los incidentes deberán clasificarse considerando, como mínimo:

- Impacto sobre la operación.
- Cantidad de usuarios afectados.
- Criticidad del componente involucrado.
- Riesgo para la continuidad del servicio.
- Urgencia de atención.

La organización podrá definir niveles de severidad (por ejemplo, crítica, alta, media y baja) de acuerdo con sus necesidades operativas.

---

# Ciclo de gestión

Todo incidente deberá seguir un proceso estructurado que contemple las siguientes etapas:

1. Detección.
2. Registro.
3. Clasificación.
4. Priorización.
5. Asignación.
6. Diagnóstico.
7. Contención.
8. Resolución.
9. Validación.
10. Cierre.
11. Análisis posterior cuando corresponda.

Cada etapa deberá quedar documentada para garantizar la trazabilidad del incidente.

---

# Escalamiento

Cuando un incidente exceda la capacidad del equipo responsable o comprometa la continuidad del servicio, deberá escalarse conforme a los procedimientos establecidos.

El escalamiento podrá involucrar, según la naturaleza del incidente:

- Equipo de Operaciones.
- Equipo DevOps.
- Equipo de Desarrollo.
- Arquitectura de Software.
- Equipo de Seguridad.
- Responsables funcionales.

---

# Comunicación

Durante la atención de un incidente deberá mantenerse una comunicación clara y oportuna entre los equipos involucrados.

La información registrada deberá incluir, cuando aplique:

- descripción del incidente;
- fecha y hora de detección;
- servicios afectados;
- impacto identificado;
- acciones ejecutadas;
- estado de la atención;
- responsable asignado;
- fecha y hora de resolución.

---

# Análisis posterior

Los incidentes de mayor impacto deberán ser objeto de un análisis posterior para identificar:

- causa raíz;
- factores contribuyentes;
- acciones correctivas;
- acciones preventivas;
- oportunidades de mejora.

Las conclusiones deberán documentarse y utilizarse para fortalecer la estabilidad del sistema.

---

# Responsabilidades

| Equipo | Responsabilidad |
|---------|-----------------|
| Operaciones | Detectar, registrar y coordinar la atención inicial de los incidentes. |
| DevOps | Restaurar la operación de la plataforma y coordinar las acciones técnicas necesarias. |
| Desarrollo | Analizar y corregir defectos de software cuando el incidente tenga origen en el código. |
| Arquitectura | Apoyar la resolución de incidentes que afecten decisiones arquitectónicas o múltiples servicios. |
| QA | Validar las correcciones implementadas cuando corresponda. |

---

# Relación con la observabilidad

La estrategia de gestión de incidentes depende de la información obtenida mediante:

- métricas;
- registros (logs);
- trazas distribuidas;
- alertas;
- tableros de monitoreo.

Estos mecanismos permiten detectar y diagnosticar oportunamente los eventos operativos.

---

# Buenas prácticas

La gestión de incidentes deberá:

- priorizar la restauración del servicio;
- mantener evidencia de todas las acciones realizadas;
- evitar soluciones temporales no documentadas;
- promover la colaboración entre equipos;
- registrar las lecciones aprendidas;
- utilizar los incidentes como fuente de mejora continua.

---

# Relación con otros documentos

Este documento complementa:

- `README.md` de Operaciones.
- `observability.md`.
- `backup-and-recovery.md`.
- `ci-cd.md`.
- `environments.md`.
- Arquitectura del sistema.
- Documentación de microservicios.
- ADR (Architecture Decision Records).

---

# Mantenimiento

La estrategia de gestión de incidentes deberá actualizarse cuando exista alguno de los siguientes cambios:

- modificación del proceso de atención;
- incorporación de nuevos servicios;
- cambios en la estrategia de observabilidad;
- actualización de responsabilidades operativas;
- evolución de la arquitectura del sistema.

Toda actualización deberá mantenerse alineada con la arquitectura, la estrategia DevOps y las políticas de continuidad operativa definidas para el Sistema de Gestión de Horarios SENA.