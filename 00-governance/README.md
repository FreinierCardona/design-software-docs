# Gobierno Documental

> Estado: 🟢 Aprobado
> Última actualización: 2026-06-23
> Autor: Equipo de Arquitectura
> Equipo: Sistema de Gestión de Horarios SENA

---

# Objetivo

Esta sección define las normas, convenciones y lineamientos que regulan la creación, mantenimiento y evolución de la documentación oficial del Sistema de Gestión de Horarios SENA.

Su propósito es garantizar que todos los equipos trabajen bajo un conjunto común de criterios, asegurando:

* Consistencia documental.
* Trazabilidad de cambios.
* Calidad de la documentación.
* Seguridad de la información.
* Estandarización de procesos.
* Facilidad de mantenimiento del repositorio.

---

# Alcance

Las reglas definidas en esta sección aplican a:

* Historias de Usuario.
* Reglas de negocio.
* Arquitectura.
* Diagramas UML.
* Modelos de datos.
* Contratos API.
* Microservicios.
* Infraestructura.
* ADRs.
* Cualquier documento almacenado en este repositorio.

---

# ¿Cuándo consultar esta sección?

Todo integrante del proyecto debe revisar esta sección antes de:

* Crear un nuevo documento.
* Crear una nueva carpeta.
* Crear documentación de un microservicio.
* Realizar un Pull Request.
* Modificar documentación existente.
* Incorporarse al proyecto.

---

# Estructura de la sección

| Documento                                                          | Propósito                                                                                       | Estado |
| ------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------- | ------ |
| [documentation-rules.md](./documentation-rules.md)                 | Define convenciones de nombres, estructura documental, estados, índices y gestión de diagramas. | 🟢     |
| [git-conventions.md](./git-conventions.md)                         | Define la estrategia de ramas, flujo de promoción, Pull Requests y Conventional Commits.        | 🟢     |
| [microservices-documentation.md](./microservices-documentation.md) | Define cómo registrar, documentar y mantener los microservicios del proyecto.                   | 🟢     |
| [security-rules.md](./security-rules.md)                           | Establece las reglas para proteger información sensible dentro de la documentación.             | 🟢     |
| [definition-of-ready.md](./definition-of-ready.md)                 | Define cuándo un documento está listo para ser revisado.                                        | 🟢     |
| [definition-of-done.md](./definition-of-done.md)                   | Define cuándo un documento puede considerarse terminado y aprobado.                             | 🟢     |

---

# Flujo documental oficial

Todo documento deberá seguir el siguiente ciclo de vida:

```text
Borrador
   ↓
Ready
   ↓
Pull Request
   ↓
Revisión
   ↓
Aprobado
```

Los criterios de transición entre estados están definidos en:

* `definition-of-ready.md`
* `definition-of-done.md`

---

# Relación con Git

La documentación del proyecto sigue la estrategia oficial de ramas:

```text
develop
   ↓
qa
   ↓
staging
   ↓
main
```

Las convenciones completas se encuentran en:

```text
git-conventions.md
```

---

# Relación con Arquitectura

Las decisiones arquitectónicas que impacten la documentación deberán registrarse mediante ADRs y mantenerse alineadas con:

```text
05-architecture/
```

La documentación nunca debe contradecir una ADR aprobada.

---

# Relación con Microservicios

Todo microservicio documentado debe cumplir las reglas definidas en:

```text
microservices-documentation.md
```

Ningún servicio podrá registrarse en el catálogo oficial sin cumplir dichas reglas.

---

# Seguridad

Toda la documentación almacenada en el repositorio deberá cumplir las políticas definidas en:

```text
security-rules.md
```

La publicación de información sensible constituye motivo de rechazo inmediato de un Pull Request.

---

# Responsabilidades

## Autores

Responsables de:

* Crear documentación siguiendo las convenciones establecidas.
* Mantener información actualizada.
* Cumplir los criterios de Ready y Done.

## Revisores

Responsables de:

* Validar calidad y consistencia.
* Verificar cumplimiento de las políticas documentales.
* Aprobar o solicitar correcciones.

## Equipo de Arquitectura

Responsable de:

* Mantener estas políticas.
* Resolver dudas de gobernanza documental.
* Aprobar cambios estructurales del repositorio.

---

# Regla General

> Todo documento del Sistema de Gestión de Horarios SENA debe cumplir las normas definidas en esta sección antes de ser considerado documentación oficial del proyecto.
