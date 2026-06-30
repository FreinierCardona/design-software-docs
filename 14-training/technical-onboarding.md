# Technical Onboarding

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Desarrollo
> Equipo: Desarrollo, Arquitectura y DevOps

## Propósito

Este documento sirve como guía de incorporación para los nuevos integrantes técnicos del Sistema de Gestión de Horarios SENA.

Su objetivo es proporcionar una visión general del proyecto, su organización, arquitectura, metodología de trabajo y documentación, permitiendo que cualquier miembro del equipo pueda integrarse de forma rápida y comprender el contexto técnico antes de comenzar el desarrollo.

Este documento actúa como punto de entrada hacia el resto de la documentación técnica del proyecto.

---

# Objetivos

La guía de incorporación busca:

- Reducir la curva de aprendizaje.
- Facilitar la comprensión de la arquitectura del sistema.
- Presentar la organización del proyecto.
- Explicar el flujo general de desarrollo.
- Identificar la documentación esencial.
- Favorecer la adopción de buenas prácticas.
- Promover una incorporación homogénea para todos los equipos.

---

# Alcance

Esta guía está dirigida a integrantes de los equipos de:

- Desarrollo Backend.
- Desarrollo Frontend.
- Desarrollo Mobile.
- Arquitectura.
- DevOps.
- QA.
- Bases de Datos.

No sustituye la documentación técnica especializada de cada componente, sino que orienta al nuevo integrante sobre dónde encontrar la información necesaria.

---

# Conociendo el proyecto

Antes de comenzar cualquier actividad técnica, se recomienda comprender:

- la visión y alcance del producto;
- los objetivos del Sistema de Gestión de Horarios SENA;
- la organización funcional del sistema;
- los módulos de negocio;
- la arquitectura de software adoptada;
- la estrategia de desarrollo del proyecto.

Esta información se encuentra documentada en las secciones iniciales del repositorio.

---

# Arquitectura del sistema

El proyecto se desarrolla utilizando una arquitectura basada en microservicios con separación por dominios funcionales y aplicación de Clean Architecture por módulo.

Cada microservicio mantiene independencia funcional, lógica y de datos, favoreciendo la escalabilidad, el mantenimiento y la evolución del sistema.

Antes de realizar modificaciones en cualquier servicio, el nuevo integrante deberá familiarizarse con la documentación arquitectónica correspondiente.

---

# Organización del proyecto

La documentación del proyecto se encuentra organizada en diferentes secciones especializadas, entre ellas:

- Producto.
- Arquitectura.
- ADR (Architecture Decision Records).
- UML.
- Microservicios.
- DevOps.
- Calidad.
- UX/UI.
- Operaciones.
- Entrenamiento.

Cada sección documenta un aspecto específico del proyecto y debe consultarse según el tipo de actividad a desarrollar.

---

# Flujo general de trabajo

Todo desarrollo deberá seguir el flujo establecido por el proyecto, el cual contempla de manera general:

1. Comprender el requerimiento.
2. Revisar la documentación relacionada.
3. Implementar la funcionalidad correspondiente.
4. Validar el funcionamiento.
5. Someter el cambio a revisión técnica.
6. Integrar el cambio siguiendo el flujo definido para el repositorio.
7. Actualizar la documentación cuando sea necesario.

Los procedimientos específicos se documentan en las secciones de DevOps, Calidad y Gobernanza.

---

# Documentación esencial

Antes de comenzar el desarrollo, se recomienda revisar como mínimo:

- Visión del producto.
- Alcance del proyecto.
- Arquitectura del sistema.
- ADR vigentes.
- Documentación del microservicio correspondiente.
- Estrategia DevOps.
- Estrategia de calidad.
- Convenciones de desarrollo.
- Casos de uso e historias de usuario relacionadas.

La documentación deberá consultarse siempre antes de realizar cambios funcionales o arquitectónicos.

---

# Buenas prácticas

Durante la participación en el proyecto se recomienda:

- comprender el contexto funcional antes de desarrollar;
- respetar la arquitectura definida;
- mantener la separación de responsabilidades entre módulos;
- documentar los cambios relevantes;
- mantener consistencia con las decisiones arquitectónicas;
- realizar revisiones antes de integrar cambios;
- consultar al equipo de arquitectura cuando existan dudas sobre decisiones de diseño.

---

# Responsabilidades

Todo integrante técnico deberá:

- conocer la documentación relacionada con su componente;
- seguir las convenciones establecidas por el proyecto;
- mantener actualizada la documentación cuando corresponda;
- respetar los procesos de integración y revisión;
- contribuir a la calidad técnica del sistema.

---

# Recursos de consulta

La documentación oficial del proyecto constituye la fuente principal de información para el equipo técnico.

Dependiendo de la actividad, deberán consultarse los documentos correspondientes sobre:

- Arquitectura.
- Microservicios.
- DevOps.
- Calidad.
- UX/UI.
- Operaciones.
- ADR.
- APIs.
- Modelos de datos.

---

# Relación con otros documentos

Esta guía complementa:

- `README.md` de Entrenamiento.
- `user-manual.md`.
- `admin-manual.md`.
- Documentación de Arquitectura.
- Documentación de Microservicios.
- Documentación DevOps.
- Documentación de Calidad.
- ADR (Architecture Decision Records).

---

# Mantenimiento

La guía de incorporación técnica deberá actualizarse cuando ocurra alguno de los siguientes cambios:

- modificación de la arquitectura;
- incorporación de nuevos módulos;
- cambios en el flujo de desarrollo;
- actualización de la estrategia DevOps;
- modificación de las convenciones del proyecto;
- evolución significativa de la documentación técnica.

Toda actualización deberá mantenerse alineada con la arquitectura, las prácticas de desarrollo y la estrategia de gobernanza definidas para el Sistema de Gestión de Horarios SENA.