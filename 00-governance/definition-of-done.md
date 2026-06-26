# Definition of Done

> Estado: 🟢 Aprobado | 
> Última actualización: 2026-06-23 | 
> Autor: Equipo de Arquitectura | 
> Equipo: Sistema de Gestión de Horarios SENA

---

# Objetivo

Definir los criterios mínimos que debe cumplir cualquier documento del repositorio para ser considerado finalizado (**Done**) y ser utilizado como referencia oficial del proyecto.

---

# Criterios de aceptación

Un documento se considera **Done** únicamente cuando cumple todos los siguientes criterios.

## 1. Estructura y contenido

* [ ] Posee un título claro y representativo.
* [ ] Incluye una descripción u objetivo del tema documentado.
* [ ] La información es clara y comprensible para cualquier integrante del proyecto.
* [ ] El contenido es coherente con la arquitectura y las convenciones definidas en el repositorio.
* [ ] No contiene secciones vacías o información marcada como pendiente.
* [ ] La documentación refleja el estado actual del proyecto.

---

## 2. Navegación y organización

* [ ] El documento se encuentra ubicado en la carpeta correspondiente.
* [ ] Está referenciado desde el `README.md` de su sección.
* [ ] Los enlaces relativos funcionan correctamente.
* [ ] Los nombres de archivos y carpetas siguen las convenciones establecidas.
* [ ] La estructura del documento es consistente con los demás documentos del repositorio.

---

## 3. Calidad de la documentación

* [ ] El contenido fue revisado por al menos un integrante del equipo.
* [ ] No presenta errores ortográficos ni inconsistencias evidentes.
* [ ] La información es precisa y está actualizada.
* [ ] El lenguaje utilizado es técnico, claro y consistente.
* [ ] La documentación es entendible tanto para integrantes nuevos como antiguos del proyecto.

---

## 4. Seguridad

* [ ] No contiene información sensible.
* [ ] No expone credenciales, contraseñas, tokens o secretos.
* [ ] No incluye configuraciones privadas o información que comprometa la seguridad del sistema.

---

## 5. Trazabilidad

* [ ] El cambio fue registrado en el `CHANGELOG.md` cuando afecta alguno de los siguientes elementos:

  * Gobernanza.
  * Estructura del repositorio.
  * Contratos compartidos.
  * APIs compartidas.
  * Modelos de datos.
  * Convenciones de Git.
  * Reglas de negocio globales.
  * Estándares o lineamientos de arquitectura.

---

## 6. Estado del documento

* [ ] El documento fue revisado y aprobado.
* [ ] El encabezado refleja el estado actual.
* [ ] El estado cambió a **🟢 Aprobado**.

---

# Exclusiones

Un documento **NO** se considera terminado cuando:

* Está incompleto.
* Contiene secciones pendientes.
* Requiere validación funcional o técnica.
* Presenta enlaces rotos.
* Hace referencia a información obsoleta.
* Se encuentra en revisión o discusión.
* Contradice otros documentos oficiales del repositorio.

---

# Estados de los documentos

| Estado         | Descripción                                                       |
| -------------- | ----------------------------------------------------------------- |
| 🔴 Borrador    | Documento inicial en construcción.                                |
| 🟡 En revisión | Documento en proceso de análisis o validación.                    |
| 🟢 Aprobado    | Documento validado y considerado referencia oficial del proyecto. |
| ⚫ Obsoleto     | Documento reemplazado o que ya no debe utilizarse.                |

---

# Regla general

> Ningún documento debe considerarse oficial mientras no cumpla todos los criterios anteriores y su estado no haya sido actualizado a **🟢 Aprobado**.
