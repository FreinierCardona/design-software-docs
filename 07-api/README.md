# API

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

## Propósito

Esta sección centraliza los estándares, lineamientos y contratos de las APIs del Sistema de Gestión de Horarios SENA (SGH SENA).

Su objetivo es garantizar que todos los microservicios expongan interfaces consistentes, seguras, versionadas y correctamente documentadas, facilitando la integración entre servicios internos y consumidores externos.

La documentación aquí contenida representa la referencia oficial aprobada por el equipo de arquitectura.

---

## Contenido

Esta carpeta contiene la documentación relacionada con el diseño, publicación y gobierno de las APIs del proyecto.

| Archivo | Descripción | Estado |
|---------|-------------|--------|
| [guidelines.md](./guidelines.md) | Estándares de diseño, convenciones REST, versionamiento, nomenclatura, manejo de errores y buenas prácticas para todas las APIs del proyecto. | 🟢 |
| [authentication.md](./authentication.md) | Estrategia de autenticación, autorización, gestión de tokens, seguridad entre microservicios y acceso de clientes externos. | 🟢 |
| [contracts/openapi/](./contracts/openapi/) | Contratos OpenAPI (Swagger) oficiales, validados y aprobados para publicación e integración. | 🟢 |

---

# Objetivos

La documentación de APIs busca garantizar:

- Consistencia entre todos los microservicios.
- Bajo acoplamiento entre consumidores y proveedores.
- Contratos estables y versionados.
- Integraciones seguras mediante autenticación y autorización.
- Documentación reutilizable para frontend, aplicaciones móviles y sistemas externos.
- Validación temprana de cambios mediante contratos OpenAPI.

---

# Organización de los contratos

Durante el ciclo de desarrollo existen dos tipos de contratos API.

| Tipo de contrato | Ubicación | Propósito |
|-----------------|-----------|-----------|
| Contrato de desarrollo | `09-microservices/services/<servicio>/api-contract.md` | Documento utilizado por el equipo durante el diseño e implementación del microservicio. Puede cambiar con frecuencia. |
| Contrato OpenAPI oficial | `07-api/contracts/openapi/<servicio>.yaml` | Contrato estable aprobado por Arquitectura para ser consumido por aplicaciones cliente, frontend, integraciones y terceros. |

---

# Flujo de publicación

El proceso de evolución de una API sigue el siguiente flujo documental:

1. Diseño funcional del endpoint.
2. Elaboración del contrato preliminar del microservicio.
3. Revisión técnica del contrato.
4. Validación arquitectónica.
5. Generación del contrato OpenAPI.
6. Publicación del contrato oficial.
7. Consumo por aplicaciones cliente.

---

# Alcance

Esta documentación aplica para todas las APIs del SGH SENA, incluyendo los microservicios de:

- IAM
- Reference Data
- Academic Management
- Training Environment
- Scheduling
- Actors
- Document Management
- Monitoring
- Audit

---

# Relación con el repositorio

Esta documentación complementa los siguientes artefactos del proyecto:

- Arquitectura de microservicios.
- Diagramas de componentes.
- Diseño de dominio.
- Casos de uso.
- Historias de usuario.
- Diseño de base de datos.
- Contratos entre servicios.
- Documentación técnica de cada microservicio.

---

# Regla de precedencia

El contrato ubicado en:

`07-api/contracts/openapi/`

es la **única versión oficial aprobada** para consumidores externos.

Los contratos almacenados dentro de cada microservicio son documentos de trabajo y pueden encontrarse en evolución.

En caso de discrepancia entre ambos documentos, siempre prevalece el contrato publicado en esta carpeta.

---

# Convenciones generales

Todas las APIs del proyecto deberán cumplir como mínimo con:

- Arquitectura REST.
- Versionamiento mediante `/api/v1`.
- Formato JSON.
- Documentación OpenAPI 3.x.
- Autenticación mediante JWT/OAuth2 según el tipo de consumidor.
- Códigos HTTP estandarizados.
- DTOs independientes del modelo de dominio.
- Validación de entradas.
- Manejo uniforme de errores.
- Trazabilidad mediante identificadores de correlación (Correlation ID).