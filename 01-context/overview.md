# Overview

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Sistema de Gestión de Horarios SENA |

# Contexto institucional

El Servicio Nacional de Aprendizaje (SENA) es una entidad pública colombiana encargada de ofrecer formación profesional integral, educación complementaria y servicios tecnológicos orientados al desarrollo social, económico y productivo del país.

Dentro de cada Centro de Formación, la programación académica requiere coordinar múltiples elementos de manera simultánea, entre ellos:

- Programas de formación.
- Competencias y Resultados de Aprendizaje (RAP).
- Fichas.
- Instructores.
- Ambientes de formación.
- Recursos e inventario.
- Jornadas académicas.
- Disponibilidad institucional.

Actualmente, gran parte de esta información se administra mediante hojas de cálculo, documentos independientes o procesos manuales, generando dificultades para mantener una programación académica consistente, trazable y actualizada.

El proyecto **Sistema de Gestión de Horarios SENA (SGH SENA)** surge como una solución integral para centralizar la administración de los horarios académicos mediante una plataforma basada en arquitectura de microservicios, permitiendo que cada dominio del negocio sea administrado de forma independiente, escalable y desacoplada.

El sistema está diseñado para apoyar la operación académica de los Centros de Formación, facilitando la planificación, asignación, seguimiento y control de todos los recursos involucrados en el proceso de programación.

---

# Problema

La construcción y administración de horarios dentro del SENA implica coordinar una gran cantidad de información perteneciente a diferentes áreas institucionales.

Cuando estos procesos se realizan de forma manual o mediante herramientas no integradas, aparecen problemas como:

- Duplicidad de asignaciones de ambientes.
- Cruce de horarios entre instructores.
- Asignación simultánea de una misma ficha en diferentes sesiones.
- Uso incorrecto de recursos e inventario.
- Baja trazabilidad sobre cambios realizados en la programación.
- Dificultad para conocer la disponibilidad real de ambientes e instructores.
- Procesos lentos para crear, modificar o aprobar horarios.
- Dependencia de múltiples archivos distribuidos entre diferentes responsables.
- Ausencia de mecanismos automáticos para detectar conflictos de programación.
- Escasa integración entre los procesos académicos, administrativos y de infraestructura.

Estas situaciones afectan la planeación institucional, incrementan el trabajo operativo y reducen la confiabilidad de la información utilizada durante la ejecución de la formación.

---

# Objetivos

## Objetivo general

Desarrollar una plataforma de gestión de horarios para el SENA que permita administrar de manera centralizada la programación académica, integrando los procesos relacionados con la formación, los ambientes, los recursos, los instructores y los aprendices mediante una arquitectura basada en microservicios.

## Objetivos específicos

- Centralizar la información relacionada con la programación académica.
- Gestionar de forma independiente cada dominio funcional del sistema mediante microservicios.
- Administrar la disponibilidad de ambientes, recursos e inventario.
- Controlar la asignación de instructores, fichas y sesiones de formación.
- Detectar automáticamente conflictos de horarios antes de publicar la programación.
- Garantizar la trazabilidad de todas las operaciones mediante auditoría.
- Facilitar la administración de usuarios, roles y permisos.
- Proporcionar mecanismos de seguimiento mediante alertas, notificaciones e indicadores.
- Permitir la evolución independiente de cada módulo del sistema.
- Reducir errores operativos derivados de procesos manuales.

---

# Alcance funcional general

El SGH SENA se estructura alrededor de dominios funcionales independientes que colaboran entre sí para soportar el proceso completo de programación académica.

Los principales dominios son:

- Gestión de Identidad y Accesos (IAM).
- Datos Maestros (Reference Data).
- Gestión Académica.
- Gestión de Infraestructura y Ambientes.
- Gestión de Horarios.
- Gestión de Actores.
- Gestión Documental.
- Seguimiento y Monitoreo.
- Auditoría.

Cada dominio implementa su propia lógica de negocio y administra de manera autónoma su base de datos, siguiendo los principios de arquitectura de microservicios y Clean Architecture.

---

# Arquitectura del proyecto

El sistema adopta una arquitectura de microservicios orientada al dominio (Domain-Driven Design), donde cada servicio representa un contexto de negocio claramente delimitado.

Cada microservicio:

- Es autónomo.
- Posee su propia base de datos.
- Expone contratos mediante APIs.
- Implementa Clean Architecture.
- Puede evolucionar y desplegarse de forma independiente.
- Mantiene bajo acoplamiento con los demás servicios.

Esta arquitectura permite mejorar la mantenibilidad, escalabilidad y disponibilidad del sistema conforme aumenten las necesidades institucionales.

---

# Usuarios principales

El sistema está orientado principalmente a los siguientes actores institucionales:

- Coordinadores académicos.
- Programadores de horarios.
- Instructores.
- Aprendices.
- Administradores del sistema.
- Personal de infraestructura.
- Personal administrativo.

Cada usuario accede únicamente a las funcionalidades autorizadas mediante el módulo de Gestión de Identidad y Accesos (IAM).

---

# Referencias

- Acuerdo 009 de 2024.
- Lineamientos institucionales del Servicio Nacional de Aprendizaje (SENA).
- Arquitectura del proyecto SGH SENA.
- Documentación funcional y técnica del proyecto.