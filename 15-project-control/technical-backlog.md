# Technical Backlog

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura, Desarrollo y DevOps

## Propósito

Este documento registra las actividades técnicas pendientes identificadas durante el desarrollo del Sistema de Gestión de Horarios SENA.

Su objetivo es mantener un inventario de mejoras, refactorizaciones, optimizaciones, tareas de mantenimiento y deuda técnica que no corresponden directamente a funcionalidades del producto, pero que contribuyen a la estabilidad, mantenibilidad, escalabilidad y evolución de la plataforma.

El backlog técnico complementa la planificación funcional del proyecto y sirve como referencia para la priorización de iniciativas de mejora continua.

---

# Objetivos

El backlog técnico busca:

- Documentar la deuda técnica identificada.
- Priorizar mejoras de arquitectura e infraestructura.
- Planificar actividades de mantenimiento técnico.
- Favorecer la evolución continua del sistema.
- Reducir riesgos derivados de decisiones técnicas temporales.
- Facilitar la planificación de futuras iteraciones técnicas.

---

# Alcance

Este documento registra actividades relacionadas con:

- Refactorización.
- Optimización de rendimiento.
- Mejoras arquitectónicas.
- Actualización de componentes.
- Automatización.
- Mejoras de seguridad.
- Fortalecimiento de pruebas.
- Documentación técnica.
- Estandarización de procesos.

No registra historias de usuario, funcionalidades del producto, incidencias operativas ni tareas propias de la planificación diaria del equipo.

---

# ¿Qué es deuda técnica?

Se considera deuda técnica cualquier decisión temporal, limitación conocida o mejora pendiente que, si no se atiende, pueda afectar la calidad, mantenibilidad, rendimiento o evolución del sistema.

Registrar la deuda técnica permite hacerla visible, priorizar su atención y evitar que se convierta en un riesgo para el proyecto.

---

# Flujo de gestión

Toda actividad del backlog técnico deberá seguir el siguiente proceso:

1. **Identificación**

   Cualquier integrante del proyecto podrá registrar una mejora técnica o deuda identificada.

2. **Evaluación**

   El equipo correspondiente analizará el impacto técnico, el esfuerzo estimado y la prioridad.

3. **Priorización**

   La actividad se incorporará al backlog técnico con una prioridad definida.

4. **Planificación**

   Cuando exista capacidad disponible, la actividad podrá incorporarse a una iteración de trabajo.

5. **Cierre**

   Una vez implementada la mejora, el registro deberá actualizarse conservando su trazabilidad.

---

# Prioridades

| Prioridad | Descripción |
|-----------|-------------|
| Alta | Debe atenderse en el corto plazo debido a su impacto sobre la calidad, seguridad o mantenibilidad del sistema. |
| Media | Conviene resolverla durante próximas iteraciones de mejora técnica. |
| Baja | Puede programarse para futuras fases del proyecto sin afectar el avance inmediato. |

---

# Tipos de actividades

| Tipo | Descripción |
|------|-------------|
| Refactorización | Mejoras en la estructura del código sin modificar su comportamiento funcional. |
| Arquitectura | Evolución de componentes, patrones o decisiones de diseño. |
| Rendimiento | Optimizaciones relacionadas con tiempos de respuesta o consumo de recursos. |
| Seguridad | Fortalecimiento de controles y mecanismos de protección. |
| Automatización | Incorporación o mejora de procesos automáticos. |
| Documentación | Actualización o ampliación de la documentación técnica. |
| Calidad | Mejoras relacionadas con pruebas, revisión de código o estándares de desarrollo. |
| Infraestructura | Actividades relacionadas con ambientes, despliegues o configuración técnica. |

---

# Registro del backlog técnico

| ID | Actividad | Tipo | Prioridad | Responsable | Estado | Observaciones |
|----|-----------|------|-----------|-------------|--------|---------------|

---

# Estados

| Estado | Descripción |
|---------|-------------|
| Pendiente | La actividad ha sido registrada y espera priorización. |
| Planificada | Se encuentra programada para una iteración futura. |
| En progreso | Está siendo ejecutada por el equipo responsable. |
| Completada | La mejora fue implementada y validada. |
| Cancelada | La actividad dejó de ser necesaria o fue reemplazada por otra solución. |

---

# Buenas prácticas

Se recomienda:

- registrar la deuda técnica tan pronto sea identificada;
- describir claramente el problema y el beneficio esperado;
- asignar una prioridad justificada;
- revisar periódicamente el backlog técnico;
- evitar que las actividades permanezcan indefinidamente sin evaluación;
- mantener la trazabilidad de las mejoras implementadas.

---

# Relación con otros documentos

Este documento complementa:

- `risks.md`
- `dependencies.md`
- `open-questions.md`
- Arquitectura.
- ADR (Architecture Decision Records).
- Microservicios.
- DevOps.
- Calidad.

Cuando una actividad implique una modificación significativa de la arquitectura o de las decisiones técnicas del proyecto, deberá actualizarse la documentación correspondiente.

---

# Mantenimiento

El backlog técnico deberá revisarse de manera periódica durante el desarrollo del proyecto y actualizarse cuando:

- se identifique nueva deuda técnica;
- se propongan mejoras arquitectónicas;
- se detecten oportunidades de optimización;
- cambien las prioridades técnicas del proyecto;
- una actividad sea implementada o descartada.

Los registros completados o cancelados deberán conservarse como parte del historial para mantener la trazabilidad de la evolución técnica del Sistema de Gestión de Horarios SENA.