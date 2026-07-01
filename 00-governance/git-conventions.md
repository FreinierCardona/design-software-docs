# Convenciones de Git

> Estado: 🟢 Aprobado |
> Última actualización: 2026-06-23 |
> Autor: Equipo de Arquitectura |
> Equipo: Sistema de Gestión de Horarios SENA

---

# Objetivo

Definir las reglas, convenciones y flujo de trabajo que deben seguir todos los integrantes del proyecto para garantizar trazabilidad, control de cambios, colaboración organizada y promoción segura de la documentación a través de los diferentes ambientes.

---

# Alcance

Estas convenciones aplican a:

* Repositorio de documentación.
* Historias de Usuario (HU).
* Arquitectura.
* Diagramas.
* Reglas de negocio.
* Catálogo de microservicios.
* ADRs.
* Contratos de API.
* Cualquier documento almacenado dentro del repositorio.

---

# Estrategia de ramas

El proyecto utiliza una estrategia de promoción por ambientes basada en cuatro ramas padre permanentes.

| Rama      | Ambiente      | Propósito                                        |
| --------- | ------------- | ------------------------------------------------ |
| `develop` | Desarrollo    | Integración continua de cambios en construcción. |
| `qa`      | Calidad       | Validación funcional y técnica.                  |
| `staging` | Preproducción | Validación final antes de liberar cambios.       |
| `main`    | Producción    | Fuente oficial y estable de documentación.       |

---

## Reglas de las ramas padre

Las siguientes ramas son consideradas ramas protegidas:

```text
develop
qa
staging
main
```

Reglas:

* No se realizan commits directos.
* No se realizan pushes directos.
* Todo cambio debe ingresar mediante Pull Request.
* Toda promoción debe seguir el flujo oficial.
* Las ramas padre deben permanecer estables y actualizadas.

---

# Flujo oficial de promoción

```text
Rama de Trabajo de develop
       ↓
develop
       ↓
Rama de revision de qa
       ↓
qa
       ↓
Rama de revision de staging
       ↓
staging
       ↓
release iteration main
       ↓
main
```

Todo cambio deberá pasar obligatoriamente por cada ambiente antes de llegar a producción.

---

# Ramas de Historia de Usuario

Cada Historia de Usuario deberá desarrollarse en una rama independiente.

## Formato

```text
hu-<numero>-<nombre-rama>-<descripcion-corta>
```

## Ejemplos

```text
hu-01-develop-project-governance-framework
hu-01-qa-project-context
hu-01-staging-git-conventions
hu-01-main-architecture-foundation
```

## Reglas

* Deben crearse desde `develop`.
* Deben representar una única Historia de Usuario.
* Deben mantenerse pequeñas y trazables.
* No deben mezclar cambios de múltiples historias.

---

# Creación de una rama de Historia de Usuario

```bash
git checkout develop
git pull origin develop

git checkout -b hu-01-develop-project-governance-framework
```

Verificar la rama actual:

```bash
git branch
```

---

# Trabajo sobre la Historia de Usuario

Agregar cambios:

```bash
git add .
```

Crear commit:

```bash
git commit -m "docs(00-governance): add governance repository structure"
```

Publicar rama:

```bash
git push origin hu-01-develop-project-governance-framework
```

---

# Pull Request hacia Develop

Una vez finalizada la HU:

```text
hu-01-develop-project-governance-framework
            ↓
develop
```

Proceso:

1. Crear Pull Request.
2. Asociar la Historia de Usuario.
3. Validar Definition of Ready.
4. Revisar contenido.
5. Aprobar Pull Request.
6. Realizar Merge.

---

# Promoción hacia QA

Cuando la Historia de Usuario ha sido aprobada en desarrollo.

## Opción 1 - Promoción completa

Cuando toda la HU debe avanzar:

```bash
git checkout qa
git pull origin qa

git merge origin/develop

git push origin qa
```

---

## Opción 2 - Promoción selectiva

Cuando únicamente algunos commits deben avanzar:

```bash
git checkout qa

git cherry-pick <commit-sha>

git push origin qa
```

### Cuándo usar Cherry Pick

* Correcciones puntuales.
* HUs parcialmente aprobadas.
* Promociones selectivas.
* Hotfixes.

---

# Promoción hacia Staging

Una vez aprobados los cambios en QA.

## Promoción completa

```bash
git checkout staging
git pull origin staging

git merge origin/qa

git push origin staging
```

---

## Promoción selectiva

```bash
git checkout staging

git cherry-pick <commit-sha>

git push origin staging
```

---

# Release hacia Producción

Cuando una iteración está lista para liberarse.

## Crear rama Release

```bash
git checkout staging
git pull origin staging

git checkout -b release/iteration-01
```

---

## Agregar cambios específicos

```bash
git cherry-pick <commit-hu-01>
git cherry-pick <commit-hu-02>
git cherry-pick <commit-hu-03>
```

---

## Publicar Release

```bash
git push origin release/iteration-01
```

---

## Pull Request a Main

```text
release/iteration-01
            ↓
main
```

La rama release permite consolidar varias Historias de Usuario dentro de una misma liberación.

---

# Hotfix

Un Hotfix se utiliza únicamente para corregir errores críticos detectados en producción.

## Formato

```text
hotfix/<descripcion>
```

## Ejemplo

```text
hotfix/broken-navigation-links
```

---

## Crear Hotfix

```bash
git checkout main
git pull origin main

git checkout -b hotfix/broken-navigation-links
```

---

## Aplicar corrección

```bash
git add .

git commit -m "fix(00-governance): correct broken navigation links"

git push origin hotfix/broken-navigation-links
```

---

## Pull Request

```text
hotfix/broken-navigation-links
                ↓
main
```

---

## Sincronización posterior

Después de aprobar el Hotfix en producción:

```text
main
 ↓
staging
 ↓
qa
 ↓
develop
```

Esto evita divergencias entre ambientes.

---

# Conventional Commits

Todos los commits deben seguir el estándar Conventional Commits.

## Formato obligatorio

```text
<type>(NN-section): short description in english
```

---

## Ejemplo

```text
docs(00-governance): add definition of ready
```

---

# Tipos permitidos

| Tipo       | Uso                                                 |
| ---------- | --------------------------------------------------- |
| `docs`     | Crear o actualizar documentación                    |
| `fix`      | Corregir contenido incorrecto                       |
| `chore`    | Reorganizar, mover o renombrar archivos             |
| `refactor` | Reestructurar documentación sin cambiar significado |

---

## Tipos no permitidos

No utilizar:

```text
feat
style
test
perf
build
ci
```

Este repositorio es exclusivamente documental.

---

# Ejemplos válidos

```bash
docs(00-governance): add definition of done

docs(01-product): create project vision

docs(05-architecture): define service boundaries

docs(09-microservices): register scheduling service

fix(09-microservices): correct service ownership

chore(08-uml): reorganize diagram exports

refactor(00-governance): split governance documents
```

---

# Reglas para commits

* La descripción debe escribirse en inglés.
* El contenido de los documentos puede estar en español.
* Un commit debe representar un cambio lógico único.
* Evitar commits masivos sin contexto.
* Evitar mezclar múltiples secciones en un mismo commit.
* Mantener trazabilidad por Historia de Usuario.
* Realizar commits frecuentes y descriptivos.

---

# Pull Requests

Todo Pull Request debe:

* Tener un título descriptivo.
* Referenciar la Historia de Usuario asociada.
* Incluir descripción de cambios.
* Cumplir el Definition of Ready.
* Cumplir el Definition of Done.
* Ser aprobado por al menos un integrante distinto al autor.

---

# Buenas prácticas

* Mantener ramas actualizadas.
* Resolver conflictos antes de crear Pull Request.
* Utilizar nombres descriptivos.
* Mantener trazabilidad entre documentos y commits.
* Evitar trabajo directo sobre ramas protegidas.
* Mantener commits pequeños y comprensibles.

---

# Flujo resumido

```text
hu-xx-rh-descripcion
 ↓
Pull Request
 ↓
develop
 ↓
hu-xx-rh-descripcion
 ↓
qa
 ↓
hu-xx-rh-descripcion
 ↓
staging
 ↓
release/iteration-xx
 ↓
main
```

---

# Referencias

* `definition-of-ready.md`
* `definition-of-done.md`
* `documentation-rules.md`
* `security-rules.md`

---

# Regla general

> Ningún cambio podrá incorporarse a la documentación oficial del Sistema de Gestión de Horarios SENA sin seguir las convenciones de ramas, commits, Pull Requests y promoción entre ambientes definidas en este documento.
