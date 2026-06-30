# Dominio

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

## Propósito

Esta sección documenta el dominio de negocio del Sistema de Gestión de Horarios SENA desde una perspectiva funcional, independiente de cualquier tecnología o implementación.

Aquí se define el lenguaje ubicuo del proyecto, las entidades del negocio, las reglas que gobiernan el funcionamiento del sistema y los eventos relevantes que representan cambios importantes dentro del dominio.

La información contenida en esta carpeta constituye la base para el modelado de microservicios, la definición de casos de uso y la implementación de las reglas de negocio.

> **Diferencia con `06-data`:** esta sección describe el dominio en términos de negocio (entidades, invariantes, reglas y lenguaje ubicuo). No describe tablas, columnas, relaciones físicas ni esquemas de base de datos. Los aspectos de persistencia e implementación pertenecen a la carpeta [`06-data/`](../06-data/).

## Contenido

La documentación de dominio se organiza en tres componentes principales:

- **Mapa de dominio:** identifica los bounded contexts y la separación funcional de los módulos del sistema.
- **Entidades y reglas:** define las entidades principales del negocio, sus responsabilidades e invariantes.
- **Eventos de dominio:** documenta los sucesos significativos que representan cambios de estado dentro del negocio y permiten la comunicación entre módulos.

## Archivos

| Archivo | Descripción | Estado |
|---------|-------------|--------|
| [domain-map.md](./domain-map.md) | Mapa de dominio, bounded contexts y relaciones entre módulos del negocio. | 🟢 |
| [entities-and-rules.md](./entities-and-rules.md) | Entidades principales, invariantes, reglas de negocio y lenguaje ubicuo. | 🟢 |
| [domain-events.md](./domain-events.md) | Eventos de dominio que representan cambios funcionales relevantes dentro del sistema. | 🟢 |