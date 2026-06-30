# Local Setup

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo DevOps
> Equipo: DevOps e Infraestructura

## Propósito

Este documento establece los lineamientos para la preparación del entorno local de desarrollo del Sistema de Gestión de Horarios SENA.

Su objetivo es garantizar que todos los integrantes del proyecto dispongan de un entorno consistente, reproducible y alineado con los estándares definidos por el equipo de arquitectura y DevOps.

La configuración del entorno local debe permitir el desarrollo, ejecución, integración y validación de los diferentes componentes del sistema sin depender de configuraciones particulares de cada estación de trabajo.

---

# Objetivos

La documentación del entorno local permite:

- Estandarizar la preparación del ambiente de desarrollo.
- Reducir diferencias entre equipos.
- Facilitar la incorporación de nuevos integrantes.
- Garantizar la reproducibilidad del entorno.
- Minimizar errores derivados de configuraciones locales.
- Mantener consistencia con los ambientes oficiales del proyecto.

---

# Alcance

Este documento describe los lineamientos generales para la preparación del entorno de desarrollo.

Incluye:

- Requisitos generales.
- Herramientas necesarias.
- Configuración básica.
- Organización del espacio de trabajo.
- Validaciones iniciales.
- Buenas prácticas.

No incluye procedimientos específicos de instalación, configuraciones sensibles ni credenciales de acceso.

---

# Requisitos generales

Todo entorno local deberá disponer, como mínimo, de:

- Sistema operativo compatible.
- Herramientas de control de versiones.
- Entorno de desarrollo (IDE o editor compatible).
- Runtime requerido por cada componente.
- Gestores de dependencias.
- Herramientas de construcción.
- Motor de base de datos cuando aplique.
- Herramientas de contenedorización, si forman parte de la arquitectura.
- Acceso a los repositorios autorizados.

Las versiones oficiales deberán mantenerse documentadas y actualizadas por el equipo de DevOps.

---

# Organización del entorno

El entorno local deberá estructurarse de manera consistente para facilitar:

- Clonado de repositorios.
- Gestión de dependencias.
- Configuración de variables de entorno.
- Ejecución de microservicios.
- Acceso a documentación.
- Integración con herramientas del proyecto.

Cada desarrollador deberá respetar la estructura definida por el equipo.

---

# Configuración inicial

Antes de iniciar el desarrollo deberán verificarse:

- Acceso a los repositorios.
- Configuración del control de versiones.
- Variables de entorno requeridas.
- Acceso a dependencias compartidas.
- Disponibilidad de servicios locales necesarios.
- Conectividad con herramientas corporativas.

---

# Validación del entorno

Una vez preparado el entorno deberá comprobarse que sea posible:

- Obtener el código fuente.
- Resolver dependencias.
- Construir los proyectos.
- Ejecutar los servicios correspondientes.
- Ejecutar pruebas locales.
- Acceder a la documentación.
- Verificar la comunicación entre componentes cuando corresponda.

---

# Buenas prácticas

Todo entorno local deberá:

- utilizar únicamente herramientas aprobadas por el proyecto;
- mantenerse actualizado con las versiones soportadas;
- evitar configuraciones específicas no documentadas;
- proteger la información sensible mediante variables de entorno;
- mantener separación entre configuraciones locales y configuraciones compartidas;
- documentar cualquier dependencia adicional requerida.

---

# Consideraciones de seguridad

Durante la preparación del entorno se deberá garantizar que:

- las credenciales nunca sean almacenadas en el código fuente;
- los archivos de configuración sensibles no sean versionados;
- las claves de acceso permanezcan protegidas;
- los certificados y secretos sean administrados mediante los mecanismos definidos por el proyecto.

---

# Relación con otros documentos

Este documento complementa:

- `README.md` de DevOps.
- `ci-cd.md`.
- `environments.md`.
- Estrategia de ramas.
- Arquitectura del sistema.
- Documentación de microservicios.
- Guías de desarrollo.

---

# Mantenimiento

La documentación del entorno local deberá actualizarse cuando exista alguno de los siguientes cambios:

- incorporación de nuevas herramientas;
- actualización de versiones mínimas soportadas;
- modificación de la arquitectura tecnológica;
- cambios en el proceso de construcción;
- incorporación de nuevos componentes necesarios para el desarrollo.

Toda modificación deberá ser aprobada por el equipo de DevOps y mantenerse alineada con la arquitectura del Sistema de Gestión de Horarios SENA.