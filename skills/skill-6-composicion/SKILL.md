---
name: skill-6-composicion
description: >
  Ensambla los outputs de todas las skills anteriores en un prototipo funcional de media
  fidelidad: toma el wireframe de Skill 3, le aplica el sistema visual de Skill 4 y el
  microcopy de Skill 5, e integra los flujos de compliance de Skill 2 y las restricciones
  de accesibilidad de Skill 1. El resultado es un artefacto React navegable que muestra
  cómo se ve y cómo suena el producto con todas las decisiones del stack aplicadas.
  No reemplaza Figma ni producción — es el punto de validación antes de entrar a
  cualquiera de los dos. Disparar cuando el diseñador tiene al menos Skill 3 y Skill 4
  completadas y quiere ver el resultado integrado. Al detectar que aplica, confirmar:
  "¿Ensamblamos todo en el prototipo? Voy a tomar las decisiones de las skills anteriores
  y armar un artefacto navegable para que puedas validar antes de pasar a Figma o
  a desarrollo."
---

# Skill 6 — Composición

Esta skill toma los outputs de las skills anteriores y produce un **prototipo funcional
de media fidelidad** — navegable, con el sistema visual aplicado, con microcopy real,
y con los flujos críticos interactivos.

No es un documento. No es un wireframe. Es el producto tal como va a verse y sentirse,
antes de que exista en Figma o en código de producción.

---

## Protocolo de ejecución

### Paso 1 — Inventariar los outputs disponibles

Buscar en la conversación los documentos y artefactos de skills anteriores.
Registrar qué hay y qué falta:

| Skill | Output esperado | Estado |
|-------|----------------|--------|
| Skill 0 | Documento de Contexto Base | ✓ / falta |
| Skill 1 | Documento de Accesibilidad | ✓ / falta |
| Skill 2 | Documento de Compliance | ✓ / no aplica / falta |
| Skill 3 | Documento de Interacción + artefacto de wireframe | ✓ / falta |
| Skill 4 | Documento Visual + tokens | ✓ / falta |
| Skill 5 | Guía de voz y microcopy | ✓ / falta |

**Mínimo requerido para ejecutar esta skill:** Skill 3 + Skill 4.
Sin estructura (Skill 3) no hay qué aplicar el visual encima.
Sin sistema visual (Skill 4) el prototipo queda en wireframe — eso ya lo hizo Skill 3.

**Si falta Skill 5:** el prototipo se genera con placeholders de texto claramente
marcados como `[MICROCOPY PENDIENTE]`. No inventar textos.

**Si falta Skill 1 o Skill 2:** generar igual, pero declarar al final qué validaciones
de accesibilidad y compliance no se pudieron aplicar.

---

### Paso 2 — Definir el alcance del prototipo

Preguntar antes de generar:

> "¿Qué quieres ver en el prototipo? Puedo hacer todo el producto o priorizar
> una sección o flujo específico."

Opciones:

**A — Pantalla principal + navegación**
La pantalla más importante del producto con la navegación funcional.
Suficiente para validar estructura, jerarquía y sistema visual.

**B — Flujo crítico completo**
El flujo más importante del producto de principio a fin (onboarding, checkout,
creación de un objeto, configuración). Incluye todos los estados del flujo.

**C — Biblioteca de componentes**
Todos los componentes del sistema en sus estados: botones, inputs, cards,
estados del sistema, overlays. Sin flujo narrativo — es la librería visual.

**D — Todo lo anterior**
La pantalla principal + el flujo crítico + la biblioteca. El prototipo más completo.
Recomendado cuando el stack está completo y se va a presentar a un cliente o equipo.

Si el diseñador no sabe qué elegir: recomendar A para validación rápida, D si hay
tiempo y el stack está completo.

---

### Paso 3 — Extraer y consolidar los tokens

Antes de generar el artefacto, consolidar todos los tokens de las skills anteriores
en un único bloque de CSS custom properties. Este bloque es el sistema nervioso
del prototipo — todo el artefacto lo referencia, nada tiene valores hardcodeados.

Estructura del bloque de tokens consolidado:

```css
:root {
  /* ── COLOR ── */
  /* De Skill 4 */
  --color-primary: [hex];
  --color-primary-hover: [hex];
  --color-primary-active: [hex];
  --color-primary-disabled: [hex];
  --color-secondary: [hex];
  --color-neutral-900: [hex];
  --color-neutral-700: [hex];
  --color-neutral-500: [hex];
  --color-neutral-300: [hex];
  --color-neutral-100: [hex];
  --color-neutral-050: [hex];
  --color-semantic-error: [hex];
  --color-semantic-success: [hex];
  --color-semantic-warning: [hex];
  --color-semantic-info: [hex];

  /* ── TIPOGRAFÍA ── */
  /* De Skill 4 */
  --font-display: [font-family];
  --font-body: [font-family];
  --font-ui: [font-family];
  --size-display: [rem];
  --size-h1: [rem];
  --size-h2: [rem];
  --size-h3: [rem];
  --size-body-lg: [rem];
  --size-body: [rem];
  --size-body-sm: [rem];
  --size-label: [rem];
  --size-caption: [rem];
  --weight-regular: 400;
  --weight-medium: 500;
  --weight-bold: 700;
  --line-height-body: 1.5;
  --line-height-heading: 1.2;

  /* ── ESPACIADO ── */
  /* De Skill 4 */
  --space-xs: [px];
  --space-sm: [px];
  --space-md: [px];
  --space-lg: [px];
  --space-xl: [px];
  --space-2xl: [px];
  --space-3xl: [px];

  /* ── ELEVACIÓN ── */
  /* De Skill 4 */
  --shadow-1: [value];
  --shadow-2: [value];
  --shadow-3: [value];
  --shadow-4: [value];
  --shadow-5: [value];

  /* ── RADIO ── */
  /* De Skill 4 */
  --radius-sm: [px];
  --radius-md: [px];
  --radius-lg: [px];
  --radius-full: 9999px;

  /* ── MOVIMIENTO ── */
  /* De Skill 3 */
  --duration-instant: 100ms;
  --duration-fast: 200ms;
  --duration-normal: 300ms;
  --duration-slow: 500ms;
  --easing-default: ease-out;
  --easing-enter: ease-out;
  --easing-exit: ease-in;

  /* ── ACCESIBILIDAD ── */
  /* De Skill 1 */
  --touch-target-min: [44px o el valor definido];
}

/* Modo oscuro — si Skill 4 lo definió */
@media (prefers-color-scheme: dark) {
  :root {
    --color-neutral-900: [hex dark];
    --color-neutral-050: [hex dark];
    /* etc. */
  }
}

/* Reduced motion — de Skill 1 */
@media (prefers-reduced-motion: reduce) {
  :root {
    --duration-instant: 0ms;
    --duration-fast: 0ms;
    --duration-normal: 0ms;
    --duration-slow: 0ms;
  }
}
```

---

### Paso 4 — Generar el artefacto

Generar un artefacto React autocontenido con el alcance elegido en el Paso 2.

**Principios de generación:**

**Fidelidad:**
- Sistema visual completo aplicado (colores, tipografía, espaciado, elevación de Skill 4)
- Microcopy real de Skill 5 en todos los componentes visibles
- Flujos de compliance de Skill 2 integrados donde correspondan (banner de cookies
  si aplica, modales de consentimiento, etc.)
- Áreas táctiles mínimas según Skill 1
- Reduced-motion aplicado via media query
- Navegación real según lo definido en Skill 3

**Interactividad:**
- La navegación principal funciona (cambio entre secciones)
- Los estados del sistema son navegables (botón que activa loading → success/error)
- Los overlays abren y cierran (modales, drawers, bottom sheets)
- Los formularios tienen validación inline visible
- El toggle de modo oscuro si Skill 4 lo definió

**Lo que NO incluye:**
- Datos reales o conexión a APIs
- Lógica de negocio compleja
- Funcionalidades que no estén definidas en las skills anteriores
- Animaciones de alta complejidad — solo las definidas en Skill 3, implementadas
  con CSS transitions usando los tokens de movimiento

**Estructura del artefacto:**

```
App
├── TokenProvider (CSS custom properties del Paso 3)
├── Navigation (según Skill 3, Área 2)
├── Screens
│   ├── MainScreen (pantalla principal)
│   ├── FlowScreen (flujo crítico, si aplica)
│   └── ComponentLibrary (biblioteca, si aplica)
├── Overlays
│   ├── Modal
│   ├── Drawer
│   ├── BottomSheet
│   └── Toast
└── ComplianceLayer (banner cookies, consentimiento, si Skill 2 aplica)
```

**Componentes mínimos a renderizar en cualquier alcance:**

- Botón primario, secundario, destructivo — con estados hover/focus/disabled/loading
- Input de texto — con estados default/focus/error/disabled
- Card de contenido — con el layout definido en Skill 3
- Estado de loading (skeleton según Skill 3)
- Estado empty (con el microcopy de Skill 5)
- Estado de error (con mensaje y acción de recovery de Skill 5)
- Toast de éxito y de error

---

### Paso 5 — Validación y ajuste

Después de renderizar, preguntar:

> "¿El prototipo refleja lo que imaginabas? ¿Hay algo que ajustar antes
> de llevarlo a Figma o a desarrollo?"

Áreas de ajuste más comunes — ofrecerlas como opciones concretas:

- **Visual:** "¿Quieres probar otra variante de color, tipografía o densidad?"
- **Estructura:** "¿El layout de la pantalla principal está bien o quieres reorganizar
  alguna zona?"
- **Microcopy:** "¿Algún texto no suena bien o no encaja con el tono?"
- **Estados:** "¿Falta algún estado del sistema que necesitas ver?"
- **Compliance:** "¿El banner de cookies / modal de consentimiento está en el lugar correcto?"

Iterar según el feedback. Cada iteración actualiza el artefacto — no genera uno nuevo.

---

### Paso 6 — Generar el handoff

Cuando el diseñador confirma que el prototipo está validado, generar el documento
de handoff:

```
## HANDOFF — [Nombre del producto]

### Estado del prototipo
- Alcance cubierto: [A / B / C / D]
- Skills aplicadas: [lista]
- Skills pendientes o no aplicadas: [lista + motivo]

### Decisiones validadas en el prototipo
- Navegación: [descripción + confirmado/ajustado]
- Sistema visual: [descripción + confirmado/ajustado]
- Microcopy: [confirmado/ajustado + qué cambió]
- Compliance: [confirmado/ajustado / no aplica]

### Supuestos revisables
- [lista de decisiones marcadas como supuestos en skills anteriores que
  todavía no fueron confirmadas con datos o con testing de usuarios]

### Próximos pasos recomendados
- [ ] Llevar el sistema de tokens a Figma Variables o equivalente
- [ ] Implementar los flujos críticos en el framework elegido
- [ ] Testing de accesibilidad con lector de pantalla real
- [ ] Testing de usabilidad con usuarios reales antes de lanzar
- [ ] Revisar supuestos de compliance con asesor legal si el producto va a producción

### Artefactos entregados en este stack
- Documento de Contexto Base (Skill 0)
- Documento de Accesibilidad (Skill 1) [si aplica]
- Documento de Compliance (Skill 2) [si aplica]
- Documento de Interacción + wireframe (Skill 3)
- Documento Visual + tokens (Skill 4)
- Guía de voz y/o microcopy (Skill 5)
- Prototipo funcional de media fidelidad (Skill 6)
```

---

## Reglas de comportamiento

- **No generar sin Skill 3 y Skill 4.** Sin estructura y sin sistema visual, el
  artefacto no es un prototipo — es un wireframe que Skill 3 ya generó.
- **Todo referencia tokens, nada tiene valores hardcodeados.** Si el diseñador
  quiere cambiar el color primario, cambia un token y se actualiza todo.
- **El microcopy faltante se marca, no se inventa.** `[MICROCOPY PENDIENTE]` es
  más honesto que un texto genérico que después nadie reemplaza.
- **Iterar sobre el artefacto existente, no generar uno nuevo.** Cada ajuste
  modifica el componente correspondiente. Reduce la fricción y mantiene el contexto.
- **El handoff es obligatorio.** El prototipo sin handoff es un artefacto sin
  instrucciones de uso. Los supuestos revisables son especialmente importantes —
  son las decisiones que todavía no tienen evidencia de usuario.
- **Adaptar el idioma.** Mismo idioma y registro que usa el diseñador.

---

## Conexión con el stack

| Dirección | Detalle |
|-----------|---------|
| Recibe de Skill 0 | Nombre del producto, acción principal, dispositivos |
| Recibe de Skill 1 | Restricciones de accesibilidad, touch targets, reduced-motion |
| Recibe de Skill 2 | Flujos de compliance, elementos de UI obligatorios |
| Recibe de Skill 3 | Wireframe estructural, documento de interacción, tokens de movimiento |
| Recibe de Skill 4 | Sistema visual completo, todos los tokens |
| Recibe de Skill 5 | Microcopy por componente, guía de voz |
| No entrega a ninguna skill | Es la última capa del stack |

El prototipo generado por esta skill puede entregarse directamente a desarrollo
como referencia de implementación, o a un diseñador de Figma como base para
el sistema de diseño definitivo.
