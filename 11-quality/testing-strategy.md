# Testing Strategy

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Calidad
> Equipo: QA y Arquitectura de Software

## Propósito

Este documento define la estrategia de pruebas adoptada para el Sistema de Gestión de Horarios SENA.

Su objetivo es establecer los principios, niveles, responsabilidades y criterios generales para la verificación y validación del software durante todo su ciclo de vida, garantizando que cada componente cumpla los requisitos funcionales, no funcionales y arquitectónicos antes de ser promovido a un ambiente superior.

La estrategia de pruebas forma parte integral del proceso de aseguramiento de la calidad y complementa las prácticas de integración continua y revisión técnica del código.

---

# Objetivos

La estrategia de pruebas busca:

- Detectar defectos de forma temprana.
- Verificar el cumplimiento de los requisitos funcionales.
- Validar las reglas de negocio.
- Garantizar la estabilidad de los microservicios.
- Reducir riesgos durante la integración y el despliegue.
- Mantener la calidad del sistema durante su evolución.
- Favorecer la mejora continua del proceso de desarrollo.

---

# Alcance

La estrategia aplica a todos los componentes del proyecto, incluyendo:

- Microservicios.
- APIs.
- Integraciones entre servicios.
- Persistencia.
- Procesos de negocio.
- Interfaces administrativas.
- Componentes compartidos.

No incluye el diseño detallado de casos de prueba, datos de prueba ni procedimientos específicos de herramientas de automatización.

---

# Principios

Las actividades de prueba deberán cumplir los siguientes principios:

- Calidad desde las primeras etapas del desarrollo.
- Automatización cuando sea viable.
- Independencia entre desarrollo y validación.
- Repetibilidad de las pruebas.
- Trazabilidad entre requisitos y validaciones.
- Cobertura progresiva de los diferentes niveles de prueba.
- Integración con el proceso de CI/CD.

---

# Niveles de prueba

El proyecto contempla los siguientes niveles de validación:

| Nivel | Objetivo |
|--------|----------|
| Pruebas unitarias | Verificar el comportamiento de componentes individuales de forma aislada. |
| Pruebas de integración | Validar la interacción entre módulos, microservicios y componentes relacionados. |
| Pruebas funcionales | Confirmar que las funcionalidades implementadas cumplen los requisitos del negocio. |
| Pruebas de sistema | Evaluar el comportamiento integral del sistema en un entorno representativo. |
| Pruebas de aceptación | Validar que la solución satisface las necesidades y criterios definidos por el negocio. |
| Pruebas de regresión | Confirmar que los cambios no afectan funcionalidades previamente validadas. |

---

# Tipos de prueba

Dependiendo de la naturaleza del cambio, podrán ejecutarse pruebas orientadas a:

- Funcionalidad.
- Integración.
- Compatibilidad.
- Rendimiento.
- Seguridad.
- Disponibilidad.
- Recuperación ante fallos.
- Regresión.

La selección del tipo de prueba dependerá del impacto del cambio y del componente afectado.

---

# Integración con el ciclo de desarrollo

Las actividades de prueba forman parte del flujo general del proyecto:

1. Desarrollo de la funcionalidad.
2. Validación local.
3. Revisión técnica del código.
4. Ejecución de pruebas automatizadas.
5. Validación en el ambiente de QA.
6. Validación en Staging.
7. Liberación a Producción.

Cada etapa deberá completarse satisfactoriamente antes de promover el cambio al siguiente ambiente.

---

# Responsabilidades

| Equipo | Responsabilidad |
|---------|-----------------|
| Desarrollo | Elaborar y ejecutar las pruebas correspondientes durante el desarrollo de la funcionalidad. |
| QA | Planificar, ejecutar y documentar las pruebas funcionales y de integración. |
| Arquitectura | Verificar que las pruebas cubran los aspectos arquitectónicos relevantes. |
| DevOps | Integrar las validaciones automatizadas dentro del proceso de CI/CD. |

---

# Criterios de aceptación

Una versión podrá considerarse apta para promoción cuando:

- las pruebas planificadas hayan sido ejecutadas;
- no existan defectos críticos abiertos;
- se cumplan los criterios funcionales definidos;
- las validaciones automáticas finalicen correctamente;
- la documentación correspondiente permanezca actualizada.

---

# Gestión de defectos

Todo defecto identificado deberá:

- registrarse de forma trazable;
- clasificarse según su impacto;
- priorizarse de acuerdo con su criticidad;
- verificarse nuevamente una vez implementada la corrección.

La resolución de defectos deberá documentarse conforme a los procesos definidos por el equipo.

---

# Buenas prácticas

Las actividades de prueba deberán:

- ejecutarse de manera continua durante el desarrollo;
- mantenerse alineadas con los requisitos del negocio;
- ser repetibles y verificables;
- evitar dependencias innecesarias entre ambientes;
- documentar claramente los resultados obtenidos;
- evolucionar junto con la arquitectura y las funcionalidades del sistema.

---

# Relación con otros documentos

Este documento complementa:

- `README.md` de Calidad.
- `code-review.md`.
- Documentación de DevOps.
- `ci-cd.md`.
- `environments.md`.
- Arquitectura del sistema.
- Documentación de microservicios.
- ADR (Architecture Decision Records).

---

# Mantenimiento

La estrategia de pruebas deberá revisarse y actualizarse cuando exista alguno de los siguientes cambios:

- incorporación de nuevos tipos de pruebas;
- modificación de la arquitectura;
- cambios en el proceso de desarrollo;
- actualización de la estrategia de integración continua;
- evolución de los criterios de calidad del proyecto.

Toda modificación deberá mantenerse alineada con la arquitectura, las prácticas de calidad y la estrategia DevOps del Sistema de Gestión de Horarios SENA.