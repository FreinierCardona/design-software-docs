# Definition of Ready

> Estado: 🟢 Aprobado |
> Última actualización: 2026-06-23 |
> Autor: Equipo de Arquitectura |
> Equipo: Sistema de Gestión de Horarios SENA 

---

# Objetivo

Definir los criterios mínimos que debe cumplir cualquier documento antes de ser sometido a revisión mediante un Pull Request (PR).

El propósito de este documento es garantizar que las revisiones se enfoquen en la calidad del contenido y no en corregir errores básicos de estructura, formato o ubicación dentro del repositorio.

---

# Criterios de aceptación

Un documento se considera **Ready** cuando cumple todos los siguientes criterios.

---

## 1. Información básica

* [ ] Tiene un título claro y representativo.
* [ ] Incluye estado del documento.
* [ ] Incluye fecha de última actualización.
* [ ] Identifica al autor o equipo responsable.
* [ ] El nombre del archivo sigue las convenciones del repositorio.

---

## 2. Contexto y propósito

* [ ] Explica el contexto del tema documentado.
* [ ] Define claramente su propósito.
* [ ] Identifica el alcance del contenido.
* [ ] Está alineado con la arquitectura y lineamientos del proyecto.

---

## 3. Contenido mínimo

* [ ] Contiene información útil y desarrollada.
* [ ] No posee secciones vacías.
* [ ] No contiene únicamente comentarios o texto temporal.
* [ ] El contenido es entendible por cualquier integrante del proyecto.
* [ ] Las reglas, decisiones o definiciones documentadas son claras y verificables.

---

## 4. Organización y navegación

* [ ] Está ubicado en la carpeta correcta.
* [ ] Se encuentra enlazado desde el `README.md` de su sección.
* [ ] Los enlaces relativos funcionan correctamente.
* [ ] La estructura del documento es consistente con el resto del repositorio.

---

## 5. Diagramas y artefactos

Cuando aplique:

* [ ] Los diagramas referenciados existen en el repositorio.
* [ ] Los diagramas cuentan con versión editable.
* [ ] Los diagramas se encuentran en la ubicación definida por las convenciones del proyecto.
* [ ] Los diagramas representan la información descrita en el documento.

---

## 6. Seguridad

* [ ] No contiene credenciales.
* [ ] No contiene contraseñas.
* [ ] No contiene tokens.
* [ ] No contiene datos personales.
* [ ] No contiene información sensible o confidencial.
* [ ] No expone configuraciones privadas del proyecto.

---

## 7. Validación del autor

* [ ] El autor revisó completamente el documento antes de crear el Pull Request.
* [ ] Se verificó ortografía y redacción.
* [ ] Se verificaron enlaces internos.
* [ ] Se verificó consistencia con otros documentos relacionados.

---

## 8. Preparación para revisión

* [ ] El documento está listo para recibir observaciones.
* [ ] No existen tareas pendientes conocidas dentro del documento.
* [ ] El contenido se considera suficientemente maduro para ser evaluado por revisores.
* [ ] El Pull Request asociado contiene una descripción clara de los cambios realizados.

---

# Exclusiones

Un documento **NO** se considera Ready cuando:

* Está incompleto.
* Tiene secciones vacías.
* Presenta información contradictoria.
* Carece de contexto o propósito.
* Tiene enlaces rotos.
* Requiere investigación adicional antes de ser revisado.
* Contiene contenido temporal o borradores sin desarrollar.

---

# Relación con Definition of Done

La secuencia oficial para la documentación del proyecto es:

```text
Draft → Ready → Review → Done
```

Donde:

* **Draft**: Documento en construcción.
* **Ready**: Documento preparado para revisión.
* **Review**: Documento en proceso de validación.
* **Done**: Documento aprobado y considerado oficial.

---

# Regla general

> Ningún documento debe ser sometido a revisión mediante Pull Request si no cumple previamente todos los criterios definidos en este Definition of Ready.
