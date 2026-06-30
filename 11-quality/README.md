# Calidad

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Calidad
> Equipo: QA y Arquitectura de Software

## Propósito

Esta sección centraliza la documentación relacionada con el aseguramiento de la calidad del Sistema de Gestión de Horarios SENA.

Su objetivo es establecer los lineamientos, criterios y prácticas que permitan verificar que cada componente del sistema cumpla con los requisitos funcionales, no funcionales y arquitectónicos definidos para el proyecto.

La calidad constituye una responsabilidad compartida entre los equipos de desarrollo, arquitectura, QA y DevOps durante todo el ciclo de vida del software.

---

# Objetivos

La documentación de calidad permite:

- Definir la estrategia general de pruebas del proyecto.
- Estandarizar los criterios para la revisión del código.
- Promover la detección temprana de defectos.
- Garantizar el cumplimiento de los estándares de desarrollo.
- Mantener la estabilidad de la arquitectura.
- Facilitar la mejora continua del proceso de desarrollo.

---

# Alcance

Esta sección documenta:

- Estrategia de pruebas.
- Niveles de validación.
- Criterios de aceptación.
- Revisión técnica del código.
- Buenas prácticas de calidad.
- Responsabilidades de los equipos.

No incluye casos de prueba específicos, scripts automatizados ni configuraciones propias de herramientas de testing.

---

# Principios de calidad

El proyecto adopta los siguientes principios:

- Calidad desde el diseño.
- Automatización cuando sea posible.
- Validación continua.
- Prevención antes que corrección.
- Trazabilidad de cambios.
- Mejora continua.
- Responsabilidad compartida.
- Cumplimiento de estándares arquitectónicos.

---

# Estrategia general

La calidad del software se garantiza mediante actividades realizadas durante todo el ciclo de desarrollo, incluyendo:

- Validación de requisitos.
- Revisión técnica.
- Desarrollo conforme a estándares.
- Ejecución de pruebas.
- Integración continua.
- Revisión arquitectónica.
- Validación antes del despliegue.

Cada cambio deberá superar los controles definidos antes de ser promovido al siguiente ambiente.

---

# Relación con la arquitectura

Las prácticas de calidad deberán respetar los principios establecidos para la arquitectura del proyecto, incluyendo:

- Arquitectura basada en microservicios.
- Clean Architecture.
- Domain-Driven Design (DDD).
- Separación de responsabilidades.
- Bajo acoplamiento.
- Alta cohesión.
- Independencia de los servicios.

---

# Archivos relacionados

| Archivo | Descripción | Estado |
|----------|-------------|--------|
| testing-strategy.md | Estrategia de pruebas, niveles de validación y criterios generales de aseguramiento de la calidad. | 🟢 |
| code-review.md | Proceso, responsabilidades y criterios para la revisión técnica del código fuente. | 🟢 |

---

# Relación con otros documentos

Esta sección complementa la documentación disponible en:

- Arquitectura del sistema.
- Microservicios.
- DevOps.
- ADR (Architecture Decision Records).
- Guías de desarrollo.
- Estrategia de ramas.
- Documentación de APIs.

---

# Mantenimiento

La documentación de calidad deberá actualizarse cuando exista alguno de los siguientes cambios:

- incorporación de nuevos procesos de validación;
- modificación de la estrategia de pruebas;
- actualización de los criterios de revisión;
- cambios en los estándares de desarrollo;
- evolución de la arquitectura del proyecto.

Toda actualización deberá mantenerse alineada con las políticas de arquitectura, desarrollo y gobernanza definidas para el Sistema de Gestión de Horarios SENA.