# Navigation Map

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo UX/UI
> Equipo: Diseño de Experiencia e Interfaces

## Propósito

Este documento define la arquitectura de navegación del Sistema de Gestión de Horarios SENA.

Su objetivo es establecer la organización general de las pantallas, módulos y flujos de navegación del sistema, garantizando una experiencia consistente, intuitiva y alineada con la arquitectura funcional del proyecto.

El mapa de navegación constituye la referencia para el diseño de interfaces, el desarrollo frontend y la evolución de la experiencia de usuario.

---

# Objetivos

La documentación de navegación busca:

- Definir la estructura general de navegación.
- Organizar las funcionalidades por módulos.
- Facilitar el acceso a las diferentes capacidades del sistema.
- Mantener consistencia entre plataformas.
- Reducir la complejidad de los recorridos del usuario.
- Favorecer la escalabilidad del producto.

---

# Alcance

Este documento describe:

- Estructura general de navegación.
- Jerarquía de módulos.
- Organización de pantallas.
- Flujos principales de usuario.
- Relaciones entre funcionalidades.
- Reglas generales de navegación.

No incluye wireframes, prototipos, diseños visuales ni especificaciones de componentes gráficos.

---

# Principios de navegación

La navegación del sistema deberá cumplir los siguientes principios:

- Simplicidad.
- Consistencia.
- Claridad.
- Predictibilidad.
- Accesibilidad.
- Escalabilidad.
- Orientación a tareas.
- Mínima cantidad de pasos para completar una acción.

---

# Organización funcional

La navegación deberá estructurarse de acuerdo con los módulos funcionales definidos por la arquitectura del sistema.

Cada módulo representará un conjunto de funcionalidades relacionadas dentro de un mismo contexto de negocio y mantendrá independencia respecto a los demás módulos.

La incorporación de nuevas funcionalidades deberá respetar esta organización para evitar duplicidades y mantener una experiencia coherente.

---

# Jerarquía de navegación

La estructura general deberá organizarse mediante niveles jerárquicos claramente definidos, por ejemplo:

- Acceso al sistema.
- Área principal (Dashboard).
- Módulos funcionales.
- Funcionalidades.
- Detalle de información.
- Operaciones específicas.

La profundidad de navegación deberá mantenerse tan reducida como sea posible para favorecer la usabilidad.

---

# Flujos principales

Los recorridos del usuario deberán documentarse para las funcionalidades críticas del sistema.

Cuando corresponda, cada flujo deberá identificar:

- Punto de inicio.
- Pantallas involucradas.
- Decisiones relevantes.
- Resultado esperado.
- Posibles rutas alternativas.

---

# Navegación entre módulos

La transición entre módulos deberá:

- respetar los permisos del usuario;
- mantener el contexto de trabajo cuando sea necesario;
- evitar cambios innecesarios de flujo;
- conservar una experiencia uniforme.

Toda navegación entre contextos funcionales deberá responder a una necesidad claramente identificada.

---

# Navegación por plataforma

La arquitectura de navegación deberá mantenerse consistente entre las plataformas soportadas por el proyecto:

- Aplicación Web.
- Aplicación Móvil Android.

Cada plataforma podrá adaptar sus patrones de navegación de acuerdo con sus convenciones, sin alterar la estructura funcional ni la lógica del sistema.

---

# Accesibilidad

La navegación deberá favorecer una experiencia accesible mediante:

- rutas claras y comprensibles;
- identificación adecuada de las opciones de navegación;
- consistencia en la ubicación de elementos;
- reducción de pasos innecesarios;
- facilidad para regresar a niveles anteriores.

---

# Relación con la arquitectura

La estructura de navegación deberá mantenerse alineada con:

- los módulos funcionales del sistema;
- los límites de cada Bounded Context;
- los casos de uso definidos;
- las historias de usuario;
- la organización de microservicios cuando corresponda.

La navegación nunca deberá romper la separación funcional establecida por la arquitectura del proyecto.

---

# Relación con otros documentos

Este documento complementa:

- `README.md` de UX/UI.
- `design-system.md`.
- `wireframes.md`.
- Casos de uso.
- Historias de usuario.
- Arquitectura del sistema.
- Documentación funcional.

---

# Mantenimiento

El mapa de navegación deberá actualizarse cuando ocurra alguno de los siguientes cambios:

- incorporación de nuevos módulos;
- modificación de flujos funcionales;
- reorganización de pantallas;
- cambios en la arquitectura funcional;
- mejoras en la experiencia de usuario.

Toda actualización deberá mantenerse alineada con la arquitectura, la visión del producto y los objetivos funcionales del Sistema de Gestión de Horarios SENA.