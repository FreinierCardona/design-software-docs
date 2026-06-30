# Risks

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Gestión del Proyecto
> Equipo: Gestión, Arquitectura y Desarrollo

## Propósito

Este documento registra y da seguimiento a los riesgos identificados durante el desarrollo del Sistema de Gestión de Horarios SENA.

Su objetivo es facilitar la identificación temprana de eventos que puedan afectar el cumplimiento de los objetivos del proyecto, permitiendo planificar acciones preventivas, reducir su probabilidad de ocurrencia y minimizar su impacto sobre el producto.

La gestión de riesgos forma parte de la gobernanza del proyecto y deberá mantenerse durante todo su ciclo de vida.

---

# Objetivos

La gestión de riesgos busca:

- Identificar riesgos de forma temprana.
- Evaluar su impacto y probabilidad.
- Priorizar las acciones de mitigación.
- Reducir la incertidumbre del proyecto.
- Facilitar la toma de decisiones.
- Dar seguimiento continuo a los riesgos identificados.
- Mantener trazabilidad sobre las acciones implementadas.

---

# Alcance

Este documento registra riesgos relacionados con:

- Arquitectura.
- Desarrollo.
- Calidad.
- Integraciones.
- Infraestructura.
- Seguridad.
- Operación.
- Gestión del proyecto.
- Dependencias externas.

No contempla la gestión de incidentes operativos posteriores al despliegue, los cuales se documentan en la sección de Operaciones.

---

# Proceso de gestión

Todo riesgo deberá seguir el siguiente ciclo de gestión:

1. **Identificación**

   Cualquier integrante del proyecto podrá registrar un riesgo cuando identifique una situación que pueda afectar el desarrollo o la operación futura del sistema.

2. **Evaluación**

   El riesgo deberá analizarse considerando:

   - probabilidad de ocurrencia;
   - impacto sobre el proyecto;
   - criticidad;
   - componentes afectados.

3. **Priorización**

   Los riesgos se priorizarán para determinar el orden en que deberán gestionarse.

4. **Mitigación**

   Se definirán acciones destinadas a reducir la probabilidad o el impacto del riesgo.

5. **Seguimiento**

   Los riesgos permanecerán bajo revisión hasta su cierre o hasta que dejen de representar una amenaza para el proyecto.

---

# Clasificación

Los riesgos podrán clasificarse según su naturaleza.

| Categoría | Descripción |
|-----------|-------------|
| Arquitectónico | Riesgos relacionados con decisiones de diseño o arquitectura. |
| Técnico | Riesgos derivados del desarrollo o la implementación. |
| Funcional | Riesgos asociados a reglas de negocio o requisitos. |
| Operacional | Riesgos relacionados con la operación y mantenimiento del sistema. |
| Seguridad | Riesgos que comprometan la confidencialidad, integridad o disponibilidad. |
| Organizacional | Riesgos asociados a recursos, planificación o coordinación entre equipos. |
| Externo | Riesgos derivados de terceros o dependencias externas. |

---

# Evaluación

Cada riesgo deberá evaluarse utilizando los siguientes criterios.

## Probabilidad

| Valor | Descripción |
|--------|-------------|
| Alta | Es muy probable que ocurra. |
| Media | Existe una posibilidad moderada de ocurrencia. |
| Baja | Es poco probable que ocurra. |

## Impacto

| Valor | Descripción |
|--------|-------------|
| Alto | Compromete significativamente el proyecto o la operación del sistema. |
| Medio | Afecta parcialmente el desarrollo o funcionamiento del proyecto. |
| Bajo | Tiene un impacto limitado y fácilmente controlable. |

La prioridad del riesgo será determinada considerando la combinación entre impacto y probabilidad.

---

# Registro de riesgos

| ID | Riesgo | Categoría | Probabilidad | Impacto | Prioridad | Responsable | Estado | Plan de mitigación |
|----|---------|-----------|--------------|----------|-----------|-------------|--------|--------------------|

---

# Estados

| Estado | Descripción |
|---------|-------------|
| Identificado | El riesgo ha sido registrado. |
| En seguimiento | Se encuentra siendo monitoreado. |
| Mitigado | Se implementaron acciones que reducen el riesgo. |
| Cerrado | El riesgo dejó de representar una amenaza para el proyecto. |

---

# Buenas prácticas

Se recomienda:

- identificar riesgos desde las primeras etapas del proyecto;
- revisar periódicamente el registro de riesgos;
- documentar las acciones de mitigación implementadas;
- asignar un responsable para cada riesgo;
- actualizar el estado conforme evolucione el proyecto;
- evitar eliminar riesgos del historial.

---

# Relación con otros documentos

Este documento complementa:

- `technical-backlog.md`
- `dependencies.md`
- `open-questions.md`
- Arquitectura.
- ADR (Architecture Decision Records).
- DevOps.
- Operaciones.

Cuando un riesgo origine cambios significativos en la arquitectura o en la planificación del proyecto, deberá actualizarse la documentación correspondiente.

---

# Mantenimiento

El registro de riesgos deberá revisarse periódicamente durante el desarrollo del proyecto y actualizarse cuando:

- se identifiquen nuevos riesgos;
- cambie la probabilidad o el impacto de un riesgo existente;
- se implementen acciones de mitigación;
- un riesgo deje de ser aplicable;
- la evolución del proyecto genere nuevas amenazas.

Los riesgos cerrados deberán conservarse en el historial para mantener la trazabilidad y facilitar el aprendizaje del proyecto.