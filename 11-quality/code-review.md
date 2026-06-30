# Code Review

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Calidad
> Equipo: QA y Arquitectura de Software

## Propósito

Este documento establece los lineamientos para la revisión técnica del código fuente desarrollado para el Sistema de Gestión de Horarios SENA.

El proceso de revisión tiene como objetivo garantizar que cada cambio incorporado al proyecto cumpla los estándares de calidad, arquitectura, mantenibilidad y seguridad definidos por el equipo, antes de integrarse a las ramas oficiales.

La revisión de código constituye una actividad obligatoria dentro del ciclo de desarrollo y forma parte del proceso de aseguramiento de la calidad del software.

---

# Objetivos

La revisión de código busca:

- Detectar defectos antes de su integración.
- Verificar el cumplimiento de la arquitectura del proyecto.
- Promover buenas prácticas de desarrollo.
- Mejorar la mantenibilidad del software.
- Favorecer el intercambio de conocimiento entre los equipos.
- Reducir deuda técnica.
- Garantizar consistencia en todo el código fuente.

---

# Alcance

La revisión aplica a todos los cambios que impliquen:

- Nuevas funcionalidades.
- Corrección de errores.
- Refactorización.
- Actualización de dependencias.
- Cambios en la arquitectura.
- Modificaciones en APIs.
- Cambios en la documentación técnica cuando impacten el desarrollo.

Ningún cambio deberá integrarse a una rama principal sin haber pasado por el proceso de revisión correspondiente.

---

# Principios

Toda revisión deberá realizarse bajo los siguientes principios:

- Objetividad.
- Respeto entre los participantes.
- Enfoque constructivo.
- Consistencia técnica.
- Cumplimiento de estándares.
- Trazabilidad de observaciones.
- Mejora continua.

La revisión evalúa el cambio realizado y no a la persona que lo desarrolló.

---

# Criterios de revisión

Como mínimo deberán verificarse los siguientes aspectos:

## Arquitectura

- Cumplimiento de Clean Architecture.
- Respeto de los límites del Bounded Context.
- Bajo acoplamiento.
- Alta cohesión.
- Separación adecuada de responsabilidades.
- Uso correcto de patrones definidos por el proyecto.

---

## Calidad del código

- Legibilidad.
- Simplicidad.
- Consistencia.
- Reutilización.
- Eliminación de código muerto.
- Ausencia de duplicidad innecesaria.

---

## Funcionalidad

Verificar que el cambio:

- cumpla la historia de usuario;
- no altere funcionalidades existentes;
- respete las reglas del negocio;
- mantenga la compatibilidad cuando corresponda.

---

## Seguridad

Revisar, cuando aplique:

- Validación de entradas.
- Manejo adecuado de excepciones.
- Protección de información sensible.
- Control de acceso.
- Gestión segura de configuraciones.

---

## Persistencia

Validar que:

- el modelo de datos permanezca consistente;
- no existan dependencias entre bases de datos de distintos microservicios;
- las migraciones se encuentren documentadas cuando existan.

---

## APIs

Cuando existan cambios en interfaces públicas deberá verificarse:

- compatibilidad del contrato;
- documentación actualizada;
- versionamiento adecuado;
- manejo correcto de errores.

---

## Documentación

Confirmar que los cambios realizados se encuentren reflejados en la documentación correspondiente cuando sea necesario.

---

# Flujo de revisión

El proceso general comprende las siguientes etapas:

1. Finalización del desarrollo.
2. Preparación del cambio para revisión.
3. Revisión técnica por un integrante autorizado.
4. Registro de observaciones.
5. Corrección de hallazgos, cuando aplique.
6. Aprobación del cambio.
7. Integración mediante el flujo oficial de ramas.

---

# Roles

| Rol | Responsabilidad |
|-----|-----------------|
| Autor del cambio | Preparar el código, atender observaciones y mantener la documentación actualizada. |
| Revisor | Verificar el cumplimiento de los estándares técnicos y arquitectónicos. |
| Arquitectura | Participar en revisiones que involucren cambios estructurales o decisiones de diseño. |
| QA | Validar el impacto funcional cuando corresponda. |

---

# Criterios de aprobación

Un cambio podrá considerarse apto para integración cuando:

- cumpla los estándares definidos por el proyecto;
- no presente observaciones críticas pendientes;
- supere las validaciones automáticas de CI/CD;
- mantenga la consistencia arquitectónica;
- cuente con la documentación requerida cuando aplique.

---

# Buenas prácticas

Durante las revisiones se recomienda:

- realizar observaciones claras y fundamentadas;
- priorizar el impacto técnico sobre preferencias personales;
- mantener revisiones de alcance razonable;
- resolver las observaciones antes de la integración;
- utilizar un lenguaje respetuoso y profesional.

---

# Relación con otros documentos

Este documento complementa:

- `README.md` de Calidad.
- `testing-strategy.md`.
- Arquitectura del sistema.
- ADR (Architecture Decision Records).
- Guías de desarrollo.
- Estrategia de ramas.
- Documentación de microservicios.
- DevOps.

---

# Mantenimiento

La política de revisión de código deberá actualizarse cuando se modifiquen:

- los estándares de desarrollo;
- la arquitectura del proyecto;
- el flujo de integración;
- las herramientas utilizadas para revisión;
- los criterios de calidad definidos por el equipo.

Toda modificación deberá mantenerse alineada con la gobernanza y los estándares del Sistema de Gestión de Horarios SENA.