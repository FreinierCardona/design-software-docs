# Overview

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

# Vista General de la Arquitectura

## Propósito

El Sistema de Gestión de Horarios SENA (SGH SENA) está diseñado bajo una arquitectura de microservicios con enfoque Domain-Driven Design (DDD) y Clean Architecture por módulo, permitiendo construir una plataforma escalable, mantenible y desacoplada para la administración integral de la planeación académica y los recursos institucionales.

La arquitectura busca aislar las responsabilidades de negocio, facilitar el despliegue independiente de cada servicio y permitir la evolución del sistema sin afectar componentes no relacionados.

---

# Objetivos de la arquitectura

La arquitectura del proyecto tiene como objetivos principales:

- Separar claramente las responsabilidades funcionales.
- Reducir el acoplamiento entre módulos.
- Facilitar el mantenimiento y evolución del software.
- Permitir el despliegue independiente de cada servicio.
- Mejorar la escalabilidad horizontal.
- Centralizar la autenticación y autorización.
- Garantizar la trazabilidad mediante auditoría y monitoreo.
- Facilitar las pruebas unitarias, de integración y aceptación.

---

# Estilo arquitectónico

El sistema adopta los siguientes patrones arquitectónicos:

- Arquitectura basada en Microservicios.
- Domain-Driven Design (DDD).
- Clean Architecture por módulo.
- API First.
- Base de datos por servicio.
- Comunicación mediante APIs REST.
- Separación de responsabilidades mediante Bounded Contexts.

---

# Arquitectura lógica

La solución está organizada en servicios independientes, cada uno responsable de un dominio específico del negocio.

## Módulos principales

| Módulo | Responsabilidad |
|---------|-----------------|
| IAM | Gestión de usuarios, autenticación, autorización, roles, permisos, sesiones y tokens. |
| Reference Data | Administración de catálogos, estados, parámetros, centros de formación y datos maestros. |
| Academic Management | Gestión de programas de formación, competencias, RAP, fichas y oferta educativa. |
| Training Environment | Administración de ambientes de formación, inventario, reservas, mantenimientos y disponibilidad. |
| Scheduling | Planeación de horarios, sesiones de clase, franjas horarias, asignaciones y validación de conflictos. |
| Actors | Administración de instructores, aprendices, empresas, etapa productiva y bitácoras. |
| Document Management | Gestión documental, plantillas, versiones y almacenamiento de documentos institucionales. |
| Monitoring | Seguimiento mediante indicadores, alertas, notificaciones y planes de mejoramiento. |
| Audit | Registro de auditoría de todas las operaciones realizadas sobre los diferentes servicios. |

---

# Organización de los microservicios

Cada microservicio implementa los principios de Clean Architecture, organizando su código en capas independientes.

```
API

Application

Domain

Infrastructure
```

## Responsabilidades por capa

### API

Expone los endpoints REST y controla la comunicación con clientes externos.

### Application

Implementa los casos de uso y coordina la lógica de aplicación.

### Domain

Contiene las reglas de negocio, entidades, agregados, objetos de valor y contratos del dominio.

### Infrastructure

Implementa persistencia, integración con servicios externos, mensajería, almacenamiento y demás adaptadores tecnológicos.

---

# Independencia de datos

Cada microservicio mantiene su propia base de datos.

No existen consultas directas entre bases de datos de diferentes servicios.

La comunicación entre módulos se realiza únicamente mediante contratos de servicio, garantizando el desacoplamiento y la independencia tecnológica.

---

# Principios de diseño

La arquitectura sigue los siguientes principios:

- Alta cohesión.
- Bajo acoplamiento.
- Responsabilidad única.
- Inversión de dependencias.
- Separación de preocupaciones.
- Escalabilidad.
- Observabilidad.
- Seguridad desde el diseño (Security by Design).
- Principio API First.
- Independencia tecnológica entre servicios.

---

# Comunicación entre servicios

La interacción entre los diferentes módulos se realiza mediante APIs REST utilizando contratos bien definidos.

Cada servicio expone únicamente las funcionalidades necesarias para el resto del sistema, evitando dependencias directas sobre la implementación interna.

---

# Gestión de la seguridad

La autenticación y autorización se centralizan en el módulo IAM.

Las responsabilidades del módulo incluyen:

- Autenticación de usuarios.
- Gestión de sesiones.
- Gestión de tokens.
- Administración de roles.
- Administración de permisos.
- Validación de acceso a los servicios.

Todos los microservicios delegan la validación de identidad al servicio IAM.

---

# Persistencia

Cada microservicio posee:

- Modelo de datos propio.
- Base de datos independiente.
- Migraciones independientes.
- Repositorios propios.
- Control de versiones de esquema.

Esta estrategia evita el acoplamiento entre dominios y facilita el despliegue individual de cada componente.

---

# Escalabilidad

La arquitectura permite escalar cada microservicio de forma independiente según su carga de trabajo.

Esto posibilita optimizar el consumo de recursos y mejorar la disponibilidad del sistema sin afectar otros componentes.

---

# Mantenibilidad

La separación por dominios y la aplicación de Clean Architecture permiten:

- Incorporar nuevas funcionalidades sin modificar otros módulos.
- Reducir el impacto de cambios.
- Facilitar pruebas automatizadas.
- Mejorar la reutilización del código.
- Favorecer el trabajo paralelo entre equipos.

---

# Relación con la documentación

La presente vista general se complementa con los siguientes documentos de arquitectura:

- **deployment.md**: describe la estrategia de despliegue, ambientes e infraestructura.
- **cross-cutting.md**: documenta los aspectos transversales como seguridad, auditoría, observabilidad, manejo de errores y configuración.
- **decisions/**: contiene los Architecture Decision Records (ADR) que justifican las decisiones técnicas adoptadas durante el proyecto.