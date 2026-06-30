# API Contract

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura de Software

## Propósito

Este documento define la estructura que debe seguir la documentación del contrato API de cualquier microservicio del Sistema de Gestión de Horarios SENA.

El contrato API constituye el acuerdo formal entre el proveedor del servicio y sus consumidores, estableciendo las operaciones disponibles, las reglas de intercambio de información y los comportamientos esperados, independientemente de su implementación.

La documentación debe mantenerse sincronizada con la especificación OpenAPI vigente del servicio.

---

# Objetivos

El contrato API debe permitir:

- Comprender las capacidades funcionales del microservicio.
- Documentar las operaciones expuestas.
- Definir el formato de intercambio de información.
- Facilitar la integración entre microservicios.
- Reducir ambigüedades entre equipos.
- Servir como referencia durante el desarrollo y las pruebas.

---

# Información mínima requerida

Todo contrato API deberá documentar como mínimo:

- Nombre del microservicio.
- Descripción funcional.
- Versión de la API.
- URL base.
- Estrategia de versionamiento.
- Protocolos utilizados.
- Formato de intercambio (JSON, entre otros).
- Mecanismos de autenticación y autorización.
- Convenciones generales de consumo.

---

# Operaciones

Cada endpoint deberá especificar:

- Nombre de la operación.
- Método HTTP.
- URI.
- Descripción funcional.
- Parámetros de ruta.
- Parámetros de consulta.
- Encabezados requeridos.
- Cuerpo de la solicitud.
- Cuerpo de la respuesta.
- Códigos HTTP posibles.
- Reglas de validación.
- Restricciones de negocio aplicables.

---

# Modelos de intercambio

La documentación deberá identificar claramente:

- Request DTO.
- Response DTO.
- Objetos de error.
- Enumeraciones.
- Tipos de datos.
- Campos obligatorios.
- Campos opcionales.

---

# Manejo de errores

Cada operación deberá documentar:

- Código HTTP.
- Tipo de error.
- Descripción.
- Posibles causas.
- Respuesta esperada.

Los errores deberán seguir un formato consistente en todos los microservicios del proyecto.

---

# Seguridad

La documentación deberá indicar:

- Mecanismo de autenticación.
- Requisitos de autorización.
- Permisos necesarios.
- Tokens requeridos.
- Consideraciones de seguridad aplicables.

---

# Versionamiento

Todo cambio del contrato deberá indicar:

- Versión.
- Fecha.
- Cambios realizados.
- Compatibilidad con versiones anteriores.

Los cambios incompatibles deberán documentarse explícitamente.

---

# Relación con otros documentos

Este documento debe mantenerse alineado con:

- Especificación OpenAPI.
- Documentación Swagger.
- Modelo de dominio.
- Documentación del microservicio.
- ADR relacionados.
- Patrones de comunicación entre servicios.

---

# Buenas prácticas

La documentación del contrato API debe:

- describir el comportamiento esperado y no la implementación;
- utilizar terminología consistente con el dominio del negocio;
- mantenerse sincronizada con la API publicada;
- evitar duplicar información presente en OpenAPI cuando pueda referenciarse;
- actualizarse en cada cambio funcional que modifique el contrato.

---

# Observaciones

Este documento corresponde a una plantilla de documentación y deberá adaptarse a las necesidades particulares de cada microservicio, respetando los estándares definidos para el proyecto.