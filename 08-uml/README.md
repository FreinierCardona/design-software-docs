# UML

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura de Software

## Propósito

Esta sección centraliza todos los diagramas UML utilizados durante el análisis, diseño, evolución y mantenimiento del Sistema de Gestión de Horarios SENA.

Los diagramas representan visualmente la arquitectura lógica, los procesos del negocio, las interacciones entre componentes y el comportamiento del sistema, sirviendo como apoyo para la toma de decisiones técnicas y la comprensión del proyecto.

Esta documentación forma parte de la documentación oficial del proyecto y debe mantenerse sincronizada con los cambios funcionales y arquitectónicos.

---

# Objetivos

Los diagramas UML permiten:

- Documentar el comportamiento del sistema.
- Representar relaciones entre módulos y componentes.
- Facilitar el entendimiento entre equipos técnicos y funcionales.
- Reducir ambigüedades durante el desarrollo.
- Apoyar revisiones de arquitectura.
- Facilitar el onboarding de nuevos integrantes.
- Servir como soporte para decisiones arquitectónicas (ADR).

---

# Alcance

La documentación UML cubre:

- Procesos del negocio.
- Casos de uso.
- Relaciones entre entidades.
- Componentes de software.
- Arquitectura lógica.
- Arquitectura física.
- Flujo de interacción entre microservicios.
- Estados de entidades críticas.
- Diagramas necesarios para explicar decisiones de diseño.

No reemplaza la documentación funcional ni la documentación técnica detallada de cada microservicio.

---

# Organización

```
08-uml/
│
├── diagrams/
│   ├── source/
│   └── exports/
│
├── diagram-index.md
└── README.md
```

---

# Estructura de almacenamiento

## diagrams/source

Contiene los archivos editables utilizados para mantener los diagramas.

Ejemplos:

- PlantUML (.puml)
- WebSequenceDiagrams (.wsd)
- Draw.io (.drawio)

Los archivos fuente constituyen la versión oficial del diagrama.

---

## diagrams/exports

Contiene las versiones publicadas para consulta.

Formatos recomendados:

- SVG (preferido)
- PNG (cuando sea necesario)
- PDF (documentación formal)

Los archivos exportados nunca deben modificarse manualmente.

---

# Convenciones de nombramiento

Todos los diagramas deben seguir la estructura:

```
<modulo>-<tipo>.<extensión>
```

Ejemplos:

```
iam-use-case.puml

academic-management-class.drawio

scheduling-sequence.puml

training-environment-component.drawio

actors-state.puml
```

---

# Tipos de diagramas utilizados

| Tipo | Objetivo |
|--------|----------|
| Casos de uso | Representar funcionalidades del sistema y actores involucrados. |
| Clases | Modelar entidades y relaciones del dominio. |
| Secuencia | Mostrar la interacción temporal entre componentes. |
| Actividad | Representar procesos del negocio y flujos operativos. |
| Estado | Documentar el ciclo de vida de entidades importantes. |
| Componentes | Mostrar la organización lógica de los microservicios. |
| Despliegue | Representar la infraestructura y distribución del sistema. |

---

# Lineamientos de elaboración

Todo diagrama debe:

- representar una única responsabilidad;
- utilizar nomenclatura consistente con el dominio del proyecto;
- reflejar el estado actual de la arquitectura;
- evitar información duplicada;
- mantenerse sincronizado con la documentación técnica;
- contar con archivo fuente editable;
- contar con versión exportada para consulta.

---

# Control de versiones

Los diagramas evolucionan junto con el software.

Cualquier modificación arquitectónica que afecte:

- módulos;
- entidades;
- relaciones;
- flujos;
- componentes;
- infraestructura;

debe reflejarse en los diagramas correspondientes dentro del mismo ciclo de desarrollo.

---

# Relación con la documentación

Los diagramas UML complementan la información disponible en:

- Arquitectura del sistema.
- ADR.
- Modelo de dominio.
- Diseño de microservicios.
- APIs.
- Casos de uso.
- Historias de usuario.

En caso de inconsistencias, la arquitectura aprobada y los ADR tendrán prioridad.

---

# Índice de diagramas

Todos los diagramas existentes deben registrarse en:

- `diagram-index.md`

El índice permite conocer:

- nombre del diagrama;
- tipo;
- módulo relacionado;
- ubicación del archivo fuente;
- ubicación de la exportación;
- versión vigente.

---

# Mantenimiento

Es responsabilidad del Equipo de Arquitectura garantizar que:

- los diagramas representen el estado real del sistema;
- las exportaciones correspondan a la última versión aprobada;
- las fuentes editables permanezcan disponibles;
- no existan diagramas obsoletos sin identificar.

---

# Archivos relacionados

| Archivo | Descripción | Estado |
|----------|-------------|--------|
| diagram-index.md | Inventario oficial de todos los diagramas UML del proyecto. | 🟢 |
| diagrams/source/ | Archivos fuente editables utilizados para mantener los diagramas. | 🟢 |
| diagrams/exports/ | Versiones exportadas para consulta y documentación. | 🟢 |