# Events

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura de Software

## Propósito

Este documento define la estructura para documentar los eventos publicados y consumidos por un microservicio dentro del Sistema de Gestión de Horarios SENA.

La documentación de eventos permite comprender cómo el microservicio participa en la comunicación asíncrona de la arquitectura, garantizando trazabilidad, desacoplamiento y consistencia entre los diferentes contextos de negocio.

---

# Objetivos

La documentación de eventos tiene como finalidad:

- Identificar los eventos emitidos por el microservicio.
- Identificar los eventos consumidos.
- Documentar el flujo de integración entre servicios.
- Definir el contrato funcional de cada evento.
- Facilitar la evolución de la arquitectura basada en eventos.
- Reducir el acoplamiento entre equipos de desarrollo.

---

# Alcance

Este documento debe registrar únicamente los eventos relacionados con el microservicio documentado.

No incluye:

- lógica de procesamiento;
- implementación del broker de mensajería;
- configuración de infraestructura;
- código productor o consumidor;
- detalles internos del framework utilizado.

---

# Información general

Cada microservicio deberá documentar:

- Estrategia de comunicación utilizada.
- Broker o plataforma de mensajería.
- Tipo de intercambio.
- Convenciones de nombramiento.
- Estrategia de versionamiento.
- Garantías de entrega aplicables.

---

# Eventos publicados

Para cada evento publicado deberá registrarse como mínimo:

- Nombre del evento.
- Descripción funcional.
- Contexto de negocio.
- Condición que genera el evento.
- Productor.
- Consumidores conocidos.
- Estructura del mensaje.
- Versión del evento.
- Consideraciones de compatibilidad.

---

# Eventos consumidos

Para cada evento consumido deberá documentarse:

- Nombre del evento.
- Servicio productor.
- Propósito del consumo.
- Acción ejecutada.
- Validaciones realizadas.
- Reglas de negocio asociadas.
- Estrategia ante errores.

---

# Contrato del evento

Cada evento deberá describir:

- Nombre.
- Descripción.
- Payload.
- Campos obligatorios.
- Campos opcionales.
- Identificador único.
- Fecha de ocurrencia.
- Versión.
- Metadatos adicionales.

---

# Versionamiento

Todo cambio del contrato deberá indicar:

- Versión.
- Fecha.
- Motivo del cambio.
- Compatibilidad con consumidores existentes.

Los cambios incompatibles deberán planificarse y documentarse previamente.

---

# Trazabilidad

La documentación deberá indicar, cuando aplique:

- Identificador de correlación.
- Identificador de causalidad.
- Servicio productor.
- Servicios consumidores.
- Flujo de negocio relacionado.

---

# Manejo de errores

Se deberán documentar las estrategias utilizadas para:

- reintentos;
- eventos duplicados;
- procesamiento idempotente;
- mensajes inválidos;
- eventos descartados;
- recuperación ante fallos.

---

# Relación con otros documentos

Este documento complementa:

- Contrato API.
- Patrones de comunicación.
- Modelo de dominio.
- ADR.
- Arquitectura del sistema.
- Documentación del microservicio.

---

# Buenas prácticas

La documentación de eventos deberá:

- describir el comportamiento funcional del evento y no su implementación;
- mantener nombres consistentes con el lenguaje del dominio;
- documentar únicamente eventos vigentes;
- mantenerse sincronizada con la evolución del negocio;
- evitar duplicidad con la documentación de APIs.

---

# Observaciones

Este documento corresponde a una plantilla de documentación y deberá adaptarse a las necesidades particulares de cada microservicio. La publicación y el consumo de eventos deberán respetar los principios de desacoplamiento, autonomía y comunicación definidos para la arquitectura del Sistema de Gestión de Horarios SENA.