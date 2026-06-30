# Arquitectura

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

## Propósito

Esta sección documenta la arquitectura del Sistema de Gestión de Horarios SENA (SGH SENA), definiendo la estructura técnica del proyecto, los principios de diseño, la estrategia de despliegue y las decisiones arquitectónicas que guían el desarrollo de la solución.

La documentación busca proporcionar una visión común para todos los equipos involucrados (desarrollo, arquitectura, QA, DevOps y análisis funcional), permitiendo mantener consistencia técnica, facilitar el mantenimiento y asegurar la evolución del sistema.

## Alcance

La documentación arquitectónica comprende:

- Arquitectura general del sistema.
- Organización por módulos funcionales (Bounded Contexts).
- Arquitectura basada en microservicios.
- Implementación bajo Clean Architecture por módulo.
- Estrategia de despliegue por ambientes.
- Aspectos transversales de la plataforma.
- Registro de decisiones de arquitectura (ADR).

## Objetivos

- Estandarizar la arquitectura del proyecto.
- Definir responsabilidades entre los diferentes servicios.
- Reducir el acoplamiento entre módulos.
- Facilitar la escalabilidad y mantenibilidad del sistema.
- Documentar las decisiones técnicas tomadas durante el desarrollo.
- Servir como referencia para futuras evoluciones del proyecto.

## Organización

| Archivo | Descripción | Estado |
|---------|-------------|--------|
| [overview.md](./overview.md) | Describe la arquitectura general, principios, componentes y organización del sistema. | 🟢 |
| [deployment.md](./deployment.md) | Documenta la estrategia de despliegue, ambientes, infraestructura y flujo de publicación. | 🟢 |
| [cross-cutting.md](./cross-cutting.md) | Define los aspectos transversales aplicables a todos los microservicios, como seguridad, auditoría, observabilidad, manejo de errores y configuración. | 🟢 |
| [decisions/](./decisions/) | Contiene los Architecture Decision Records (ADR) utilizados para documentar las decisiones técnicas relevantes del proyecto. | 🟢 |

## Relación con el proyecto

La arquitectura documentada en esta sección soporta los diferentes módulos funcionales del Sistema de Gestión de Horarios SENA, entre ellos:

- IAM
- Reference Data
- Academic Management
- Training Environment
- Scheduling
- Actors
- Document Management
- Monitoring
- Audit

Cada módulo mantiene independencia funcional y de datos, comunicándose mediante contratos bien definidos, siguiendo los principios de una arquitectura de microservicios.

## Convenciones

Toda modificación arquitectónica deberá:

- Actualizar la documentación correspondiente.
- Registrar decisiones relevantes mediante un ADR.
- Mantener coherencia con la arquitectura definida.
- Evitar duplicidad de información con otras secciones del repositorio.