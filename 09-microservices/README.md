# Microservicios

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura de Software

## Propósito

Esta sección centraliza la documentación relacionada con la arquitectura de microservicios del Sistema de Gestión de Horarios SENA.

Cada microservicio representa un contexto de negocio independiente (Bounded Context), con responsabilidades claramente definidas, su propia base de datos, APIs, eventos, documentación técnica y ciclo de vida.

La documentación aquí almacenada permite comprender la organización general del sistema, las relaciones entre servicios y las convenciones utilizadas para su evolución.

---

# Objetivos

Esta documentación tiene como finalidad:

- Mantener un inventario oficial de todos los microservicios.
- Documentar la responsabilidad de cada servicio.
- Registrar los patrones de comunicación utilizados.
- Facilitar el mantenimiento de la arquitectura.
- Servir como guía para la incorporación de nuevos servicios.
- Estandarizar la documentación técnica de todos los equipos.

---

# Alcance

Esta sección documenta:

- Catálogo oficial de microservicios.
- Responsabilidades funcionales.
- Límites de cada contexto de negocio.
- Patrones de comunicación.
- Integraciones entre servicios.
- Plantillas de documentación.
- Documentación individual de cada microservicio.

No sustituye la documentación interna de cada repositorio ni la documentación de implementación.

---

# Organización

```
09-microservices/
│
├── _template/
│
├── services/
│
├── service-catalog.md
├── communication-patterns.md
└── README.md
```

---

# Principios de la arquitectura

Todos los microservicios del proyecto deben cumplir los siguientes principios:

- Responsabilidad única.
- Bajo acoplamiento.
- Alta cohesión.
- Independencia de despliegue.
- Propiedad exclusiva de sus datos.
- Comunicación mediante APIs y eventos.
- Versionamiento independiente.
- Documentación propia.
- Observabilidad.
- Seguridad desde el diseño.

---

# Estructura de la documentación

Cada microservicio debe disponer de documentación suficiente para comprender:

- propósito;
- responsabilidades;
- límites funcionales;
- modelo de dominio;
- APIs expuestas;
- eventos publicados y consumidos;
- dependencias;
- consideraciones técnicas;
- decisiones arquitectónicas relevantes.

---

# Incorporación de nuevos microservicios

Todo nuevo servicio deberá:

1. Definir claramente su responsabilidad.
2. Delimitar su contexto de negocio.
3. Contar con documentación propia.
4. Registrarse en el catálogo oficial.
5. Documentar sus patrones de integración.
6. Mantener consistencia con la arquitectura definida para el proyecto.

---

# Relación con la arquitectura

La documentación de esta sección complementa:

- Arquitectura del sistema.
- Modelo de dominio.
- ADR (Architecture Decision Records).
- Documentación de APIs.
- UML.
- DevOps.
- Observabilidad.
- Seguridad.

---

# Archivos relacionados

| Archivo | Descripción | Estado |
|---------|-------------|--------|
| service-catalog.md | Catálogo oficial de todos los microservicios del proyecto. | 🟢 |
| communication-patterns.md | Patrones de comunicación e integración entre microservicios. | 🟢 |
| _template/ | Plantilla base para documentar nuevos microservicios. | 🟢 |
| services/ | Documentación individual de cada microservicio. | 🟢 |

---

# Mantenimiento

El Equipo de Arquitectura es responsable de garantizar que esta documentación permanezca sincronizada con la arquitectura vigente del Sistema de Gestión de Horarios SENA.

Toda modificación que implique la creación, división, eliminación o cambio de responsabilidades de un microservicio deberá reflejarse en esta sección antes de considerarse finalizada.