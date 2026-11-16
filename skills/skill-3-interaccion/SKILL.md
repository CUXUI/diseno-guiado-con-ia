---
name: skill-3-interaccion
description: >
  Define los parámetros de interacción, layout y animación de un producto digital y genera
  restricciones concretas para las skills de Visual y Writing. Cubre estrategia responsive,
  navegación, layout, formularios, controles avanzados, zonas de interacción, overlays,
  estados del sistema, animaciones y consistencia de componentes. Opera en stack recibiendo
  los documentos de Skill 0, Skill 1 y Skill 2, o de forma independiente con una entrevista
  de contexto reducida. Disparar ante frases como "cómo organizo la navegación", "qué pasa
  en mobile", "cómo diseño este formulario", "qué animaciones uso", "cómo se comportan las
  cards", o cualquier pregunta sobre estructura, layout o comportamiento de un producto
  digital. Al detectar que aplica, confirmar: "¿Arrancamos con la definición de interacción
  y layout? Voy a recorrer todas las áreas — desde la navegación hasta las animaciones —
  para que queden definidas antes de empezar a construir componentes."
---

# Skill 3 — Interacción y Layout

Esta skill define cómo se comporta el producto: cómo se navega, cómo se organiza en
pantalla, cómo responden los componentes, qué pasa en cada estado, y cómo se mueve.
Produce un **Documento de Interacción** con decisiones concretas y restricciones para
las skills de Visual y Writing.

---

## Protocolo de ejecución

### Paso 1 — Detectar contexto disponible

Buscar en la conversación documentos de skills anteriores y extraer:

**De Skill 0 — Contexto Base:**
- Dispositivos principales y secundarios
- Acción principal del usuario
- Frecuencia de uso
- Experiencia objetivo (eficiencia, enganche, confianza, etc.)
- Restricciones técnicas

**De Skill 1 — Accesibilidad:**
- Nivel WCAG definido
- Accesibilidad motora (tamaño de áreas táctiles, gestos con alternativa, teclado)
- Movimiento permitido / reduced-motion requerido
- Carga cognitiva máxima (opciones por pantalla)
- Patrones de memoria de trabajo a auditar

**De Skill 2 — Compliance:**
- Flujos obligatorios (consentimiento, verificación de edad, confirmación de transacciones)
- Restricciones de visibilidad por rol

**Si no hay ningún documento previo:** hacer entrevista reducida antes de continuar:
1. ¿En qué dispositivos se usa principalmente? (mobile, desktop, tablet)
2. ¿Cuál es la acción principal que hace el usuario?
3. ¿Qué experiencia se busca? (rápida y eficiente / exploratoria / de aprendizaje / transaccional)
4. ¿Hay restricciones de accesibilidad conocidas?

---

### Paso 2 — Entrevista por áreas

Recorrer todas las áreas en orden. Cada área produce decisiones que alimentan las siguientes.
Un área por turno. Esperar respuesta antes de continuar.

---

#### Área 1 — Estrategia responsive

Preguntar:
- ¿Cuál es el dispositivo principal? ¿El diseño arranca desde mobile y escala (mobile-first)
  o desde desktop y se adapta?
- ¿Los breakpoints son fijos (puntos de quiebre definidos) o el layout es fluido
  (se adapta continuamente al ancho disponible)?

Orientación para el diseñador si no sabe cuál elegir:
- **Mobile-first** recomendado si más del 50% del uso esperado es en mobile, o si el
  producto es de consumo frecuente en movimiento.
- **Desktop-first** tiene sentido para herramientas internas, dashboards complejos,
  o productos de uso prolongado sentado.
- **Fluido** reduce casos edge pero requiere más cuidado en tipografía y componentes
  que no se comportan bien en anchos intermedios.

Definir:
- Estrategia elegida
- Breakpoints principales si aplica (mobile / tablet / desktop / wide)

---

#### Área 2 — Navegación principal

Preguntar:
- ¿Cuántos destinos principales tiene el producto? (secciones de primer nivel)
- ¿La navegación tiene que estar siempre visible o puede ocultarse al hacer scroll?

Según la cantidad de destinos y el dispositivo principal, presentar opciones concretas:

**Mobile:**
| Patrón | Cuándo usarlo |
|--------|---------------|
| Bottom navigation bar | 3-5 destinos principales, acceso frecuente |
| Hamburger + drawer | Más de 5 destinos, o navegación secundaria compleja |
| Tabs (top) | 2-4 destinos relacionados entre sí, contenido del mismo nivel |
| Drawer izquierdo | Convención para apps con muchas secciones (nav principal) |
| Drawer derecho | Convención para acciones contextuales o filtros |

**Desktop:**
| Patrón | Cuándo usarlo |
|--------|---------------|
| Header fijo con links | Hasta 6-7 destinos, contenido de marketing o público |
| Side panel persistente | Herramientas, dashboards, apps con navegación densa |
| Mega menu | E-commerce o productos con categorías profundas |
| Tabs | Contenido del mismo nivel dentro de una sección |

Preguntar también:
- ¿El producto tiene navegación secundaria (subniveles)? ¿Cómo se expone?
- ¿Se necesitan breadcrumbs? (recomendado si hay más de 2 niveles de profundidad)
- ¿La posición del drawer/hamburger es izquierda o derecha?
  → Aclarar: izquierda es convención universal; derecha puede confundirse con acciones
  contextuales. Cambiarla solo si hay una razón de negocio o de diseño muy clara.

---

#### Área 3 — Comportamiento en resize

Preguntar:
- ¿El producto tiene colecciones de elementos repetidos (cards, items de lista, tiles)?
- ¿Qué debe pasar con esos elementos cuando la pantalla se achica?

Opciones a presentar:
- **Stack vertical:** los elementos se apilan uno abajo del otro. Simple, seguro,
  accesible. Recomendado por defecto.
- **Carrusel horizontal:** los elementos quedan en fila y se hace scroll lateral.
  Más compacto, pero puede ocultar contenido. Requiere indicador visible de que hay
  más elementos. Revisar contra restricciones de Skill 1 (accesibilidad motora).
- **Grid responsivo:** cambia de columnas según el ancho (3 col → 2 col → 1 col).
  Bueno para contenido visual o de igual jerarquía.
- **Hide/show selectivo:** algunos elementos se ocultan en mobile y aparecen en
  desktop. Usar con cuidado — lo que se oculta tiene que ser realmente prescindible.

Definir para cada tipo de colección identificada en el producto.

---

#### Área 4 — Patrones de layout

Preguntar:
- ¿El contenido principal se navega con scroll o las pantallas son de altura fija?
- ¿El producto tiene paneles laterales (filtros, detalles, configuración)?
  → Si sí: ¿los paneles empujan el contenido central o se abren encima?
- ¿Hay secciones con contenido que el usuario puede reorganizar? (dashboard con
  widgets, listas reordenables)

Definir según respuestas:
- Modelo de scroll: scroll libre / scroll por secciones / pantallas fijas
- Comportamiento de paneles: overlay (se abre encima, el fondo queda visible) vs
  push (empuja y reduce el área central). Aclarar: overlay es más liviano visualmente
  pero el usuario pierde contexto del contenido debajo; push mantiene contexto pero
  requiere más espacio.
- Si hay elementos reordenables: definir si es drag & drop, si necesita alternativa
  de teclado (requerido si Skill 1 definió navegación por teclado), y cómo se
  confirma el nuevo orden.

---

#### Área 5 — Formularios

Preguntar:
- ¿El producto tiene formularios? ¿Son simples (pocos campos) o complejos
  (muchos campos, condicionales, múltiples pasos)?
- ¿Los datos del formulario tienen que guardarse automáticamente si el usuario
  interrumpe el flujo?

Definir según respuestas:

**Estructura:**
- **Single page:** todos los campos visibles. Para formularios cortos (hasta ~6 campos)
  o cuando el usuario necesita ver todo para tomar decisiones.
- **Multi-step wizard:** dividido en pasos. Para formularios largos o cuando los
  pasos tienen lógica condicional. Requiere indicador de progreso visible y posibilidad
  de volver al paso anterior sin perder datos.

**Validación:**
- **On blur (al salir del campo):** el error aparece cuando el usuario sale del campo.
  Menos intrusivo, recomendado por defecto.
- **On submit:** todos los errores aparecen al intentar enviar. Solo recomendado
  para formularios muy cortos.
- **En tiempo real (mientras escribe):** para campos con formato específico (contraseña,
  email, CUIT/DNI). Usar con moderación — puede generar ansiedad si aparece antes de
  que el usuario termine de escribir.
- Nunca mostrar error antes de que el usuario haya interactuado con el campo.

**Autosave:**
- ¿Cada cuánto se guarda? ¿Se le indica al usuario que sus datos están guardados?
- Definir comportamiento si el usuario vuelve a un formulario incompleto.

---

#### Área 6 — Controles avanzados

Preguntar según las funcionalidades del producto:

**Listas largas:**
- ¿El contenido es infinito o tiene un total conocido?
  - **Infinite scroll:** para contenido de consumo continuo (feeds, exploración).
    Requiere footer accesible — el infinite scroll lo entierra. Revisar con Skill 1
    si hay usuarios con TDAH (el scroll infinito puede ser problemático).
  - **Paginación:** para contenido donde el usuario necesita orientación (resultados
    de búsqueda, tablas). Permite volver a una página específica.
  - **Load more button:** híbrido. El usuario controla cuándo cargar más. Más accesible
    que el infinite scroll automático.

**Reordenamiento:**
- ¿Los elementos se pueden reordenar? → Drag & drop requiere alternativa de teclado
  si Skill 1 lo definió. Definir si hay snap points o posicionamiento libre.

**Pull-to-refresh:**
- Solo en mobile. ¿El contenido del producto necesita actualizarse manualmente?
  Si sí: definir el indicador de carga durante el refresh.

---

#### Área 7 — Zonas de interacción

Esta área no requiere preguntas si el dispositivo principal ya está definido.
Aplicar las siguientes reglas según el contexto:

**Mobile — Thumb zone:**
El pulgar llega cómodamente a la zona inferior de la pantalla. Las acciones
principales deben estar ahí. La zona superior izquierda es la más difícil de alcanzar
con la mano derecha (la más común).

Definir:
- Las acciones primarias van en la zona inferior (bottom nav, botón principal al fondo)
- Las acciones destructivas o poco frecuentes van arriba (más difícil de activar
  por accidente)
- Los elementos de solo lectura pueden ir donde mejor sirvan visualmente

**Safe areas (notch, home indicator):**
- Ningún elemento interactivo puede quedar debajo del home indicator de iOS o detrás
  del notch. Usar `env(safe-area-inset-*)` en CSS.

**Teclado virtual:**
- Cuando aparece el teclado en mobile, ¿qué pasa con el layout?
- El campo activo tiene que seguir siendo visible (no quedar detrás del teclado)
- Los botones de acción del formulario tienen que ser accesibles con el teclado abierto
- Definir si el layout se comprime o si el contenido hace scroll para acomodar el teclado

---

#### Área 8 — Notificaciones y overlays

Preguntar:
- ¿El producto muestra mensajes de feedback al usuario? (confirmaciones, errores,
  advertencias, información)
- ¿El producto tiene modales o diálogos de confirmación?
- ¿Usa bottom sheets en mobile?

**Toasts / Snackbars:**
- Posición: bottom center en mobile, top right o bottom center en desktop.
  No usar esquina superior izquierda — es la zona de menor atención visual.
- Duración: 3-5 segundos para mensajes informativos. Los errores no deben
  desaparecer automáticamente — el usuario tiene que dismissirlos.
- No apilar más de un toast a la vez. Si hay múltiples mensajes, hacer queue.
- Si hay acción posible ("Deshacer", "Ver"), incluirla en el toast.

**Modales:**
- Usar para acciones que requieren decisión o confirmación explícita.
- No usar para información que no requiere acción (usar toast o inline).
- Siempre tienen que poder cerrarse con Escape (teclado) y click fuera.
- El foco del teclado tiene que quedar atrapado dentro del modal mientras está abierto.

**Bottom sheets (mobile):**
- Alternativa al modal en mobile. Más natural para el pulgar.
- Cuándo usar en lugar de modal: acciones contextuales, selección de opciones,
  contenido complementario que no reemplaza la pantalla actual.
- Definir snap points: ¿el sheet tiene altura fija, media pantalla, o pantalla completa?
- Siempre dismissible con swipe hacia abajo.

---

#### Área 9 — Estados del sistema

Todos los estados deben estar definidos antes de construir cualquier componente.
Sin excepción.

Para cada flujo principal del producto, definir:

**Loading:**
- ¿Qué se muestra mientras carga el contenido?
  - **Skeleton screen:** placeholder con la forma del contenido. Recomendado para
    contenido estructurado (cards, listas, perfiles). Reduce la percepción de espera.
  - **Spinner / progress indicator:** para acciones puntuales (guardar, enviar, cargar
    más). Lineal si hay progreso medible, radial (spinner) si el tiempo es indeterminado.
  - **Nada (optimistic UI):** la acción se muestra como completada antes de confirmación
    del servidor. Solo para acciones de bajo riesgo (like, toggle). Requiere manejo
    de error si falla.

**Empty state:**
- ¿Qué ve el usuario cuando no hay contenido todavía?
- Los empty states deben ser accionables: explicar por qué está vacío y ofrecer
  la acción para llenarlo. No son solo ilustraciones decorativas.
- Distinguir entre: vacío porque es nuevo (onboarding), vacío porque no hay resultados
  (búsqueda sin match), vacío porque todo está hecho (inbox cero).

**Error state:**
- Distinguir entre: error de red (sin conexión), error del servidor (500), error
  de validación (datos incorrectos), error de permisos (no autorizado).
- Cada tipo tiene un mensaje distinto y una acción de recovery distinta.
- Los errores críticos (pantalla completa) deben ofrecer siempre una salida.
- Los errores inline (en formularios) deben decir qué está mal y cómo corregirlo,
  no solo que algo está mal.

**Success state:**
- Cuándo confirmar que algo funcionó y cómo (toast, pantalla de confirmación,
  cambio de estado del componente).

---

#### Área 10 — Animaciones: propósito y duración

Antes de definir cualquier animación, definir su propósito. Una animación sin
propósito funcional es ruido visual.

**Categorías de propósito:**

| Propósito | Descripción | Ejemplos |
|-----------|-------------|---------|
| **Feedback inmediato** | Confirma que el sistema recibió la acción | Button press, toggle, checkbox |
| **System status** | Comunica que algo está pasando | Loading spinner, progress bar |
| **Navegación** | Orienta al usuario en el espacio de la app | Transición entre pantallas, slide de panel |
| **Data change** | Señala que el contenido cambió | Item que se agrega/elimina de lista, contador |
| **Delight / reward** | Refuerza un logro o momento positivo | Confetti, animación de éxito, micro-win |
| **Onboarding** | Enseña cómo funciona algo | Coach marks animados, primera vez |

Definir para el producto: ¿cuáles de estas categorías son relevantes? ¿Cuáles no aplican?

**Duraciones recomendadas:**

| Tipo | Duración | Motivo |
|------|----------|--------|
| Feedback inmediato (tap, toggle) | 100–200ms | Tiene que sentirse instantáneo |
| Microinteracciones (hover, focus) | 150–250ms | Perceptible pero no disruptivo |
| Transiciones de componentes | 200–300ms | Balance entre fluidez y velocidad |
| Transiciones de pantalla | 300–500ms | Da contexto de navegación sin demorar |
| Animaciones de delight / reward | 500–800ms | Pueden durar más porque son el momento |
| Animaciones de onboarding | 600ms–1.2s | El usuario necesita tiempo para leer y entender |

Preguntar: ¿hay algún tipo de animación que el producto necesita especialmente?
¿Hay alguno que está explícitamente fuera del tono del producto?

---

#### Área 11 — Patrones específicos de animación

Definir el comportamiento de los patrones más comunes. Solo incluir los que aplican
al producto según lo que ya se definió.

**Button press:**
- Feedback táctil visual: leve scale down (0.96–0.98) + cambio de color de estado.
- Duración: 100–150ms ease-out.

**Long-press (hold 3–5 segundos para acciones sensibles):**
- Indicador de progreso obligatorio durante el hold. Opciones:
  - Borde circular que se llena (stroke progress alrededor del botón)
  - Fill interno que crece de abajo hacia arriba
  - Scale que crece de chico a grande (para acciones de "activar")
  - Scale que decrece de grande a chico (para acciones de "eliminar" o "desactivar")
- Si el usuario suelta antes de completar: el indicador regresa a cero sin ejecutar.
- Duración del indicador: igual al tiempo de hold requerido.

**Toggle:**
- El thumb se desplaza suavemente, el track cambia de color.
- Duración: 200ms ease-in-out.
- El estado debe ser perceptible sin depender solo del color (forma o posición).

**Progress indicators:**
- Lineal: para procesos con progreso medible (carga de archivo, paso de wizard).
- Radial (spinner): para esperas indeterminadas. Nunca para procesos que tienen
  fin conocido.
- Skeleton → contenido: el skeleton se disuelve (fade out) y el contenido aparece
  (fade in). No hacer pop repentino.

**Modal enter / exit:**
- Enter: fade in + leve scale up (0.95 → 1.0). Duración 250ms ease-out.
- Exit: fade out + leve scale down (1.0 → 0.95). Duración 200ms ease-in.
- El backdrop aparece ligeramente antes que el modal (50ms de diferencia).

**Card interactions:**
- Hover (desktop): leve elevación (shadow) o leve scale up (1.02). No ambas.
- Tap (mobile): leve scale down (0.98) como feedback. Duración 100ms.
- Expand / collapse: height animada. Usar `max-height` con cuidado — preferir
  transforms para mejor performance.

**List stagger:**
- Cuando una lista de items aparece, los items entran en secuencia con un delay
  entre cada uno (30–60ms por item).
- Solo para listas cortas (hasta 8-10 items). En listas largas, el stagger se
  vuelve lento y molesto.

**Transición entre pantallas:**
- Definir la dirección que comunica la jerarquía:
  - Avanzar en flujo: slide de derecha a izquierda (convención universal)
  - Volver: slide de izquierda a derecha
  - Ir a sección de igual nivel: fade o ninguna transición
  - Abrir detalle desde lista: la card "se expande" hacia la pantalla de detalle
    (shared element transition, si la tecnología lo permite)

---

#### Área 12 — Degradación con reduced-motion

Si Skill 1 definió `prefers-reduced-motion` como obligatorio o recomendado, definir
el comportamiento alternativo para cada animación del producto.

Regla general: **reemplazar movimiento por cambios de opacidad o estado inmediato.**

| Animación original | Versión reduced-motion |
|--------------------|----------------------|
| Slide entre pantallas | Fade o cambio inmediato sin transición |
| Scale en button press | Solo cambio de color, sin movimiento |
| Skeleton → contenido | Fade rápido, sin transición elaborada |
| List stagger | Todos los items aparecen a la vez |
| Long-press progress | El indicador puede seguir (es funcional, no decorativo) |
| Modal enter/exit | Solo fade, sin scale |
| Transición de panel | Aparece/desaparece sin deslizamiento |

Aclarar: reduced-motion no significa "sin animación". Significa "sin movimiento
que pueda causar malestar". El feedback inmediato (cambios de color, opacidad)
sigue siendo válido.

---

#### Área 13 — Consistencia de componentes

Definir las reglas de consistencia antes de construir. Esto evita que los componentes
se vuelvan inconsistentes a medida que el producto crece.

Preguntar:
- ¿Cuántos niveles de botón necesita el producto? (primario, secundario, terciario,
  ghost, destructivo, link)
- ¿Cuándo usar cada uno? Definir criterio, no solo nombre.

**Criterio para tipos de botón:**
- **Primario:** la acción más importante de la pantalla. Solo uno por vista.
- **Secundario:** acción importante pero no la principal. Máximo dos por vista.
- **Terciario / Ghost:** acciones opcionales o de bajo peso visual.
- **Destructivo:** acciones irreversibles (eliminar, cancelar). Siempre requiere
  confirmación antes de ejecutar.
- **Link:** navegación, no acción. No usar para submit ni para ejecutar lógica.

**Estados obligatorios para todos los botones:**
Default → Hover (desktop) → Focus (teclado) → Active (pressed) → Disabled → Loading

Todos los botones del mismo tipo deben tener exactamente los mismos estados.
No hay excepciones por pantalla o por flujo.

**Regla de gestos:**
Si un gesto (swipe, hold, drag) se usa para una función en una parte del producto,
no puede usarse para una función diferente en otra parte del mismo producto.
Los gestos globales (swipe para navegar entre pantallas) no pueden colisionar con
gestos locales (swipe en un componente). Definir prioridad explícitamente.

---

### Paso 3 — Generar el Documento de Interacción

```
## INTERACCIÓN Y LAYOUT — [Nombre del producto]

### Estrategia responsive
- Enfoque: [mobile-first / desktop-first]
- Breakpoints: [mobile Xpx / tablet Xpx / desktop Xpx / wide Xpx]
- Layout fluido entre breakpoints: [sí/no]

### Navegación principal
- Patrón mobile: [bottom nav / hamburger+drawer / tabs / etc.]
- Patrón desktop: [header fijo / side panel / mega menu / etc.]
- Posición del drawer: [izquierda / derecha] + justificación si no es izquierda
- Navegación secundaria: [descripción]
- Breadcrumbs: [sí/no + a partir de qué nivel de profundidad]
- Comportamiento al hacer scroll: [fijo / se oculta / se minimiza]

### Comportamiento en resize
- [Para cada tipo de colección: nombre del componente → comportamiento elegido + motivo]

### Layout
- Modelo de scroll: [libre / por secciones / pantallas fijas]
- Paneles: [overlay / push] + en qué contextos
- Elementos reordenables: [sí/no + método + alternativa de teclado si aplica]

### Formularios
- Estructura: [single page / multi-step wizard]
- Validación: [on blur / on submit / en tiempo real para campos específicos]
- Autosave: [sí/no + frecuencia + indicador al usuario]
- Comportamiento al volver a formulario incompleto: [descripción]

### Controles avanzados
- Listas largas: [infinite scroll / paginación / load more] + justificación
- Drag & drop: [sí/no + alternativa de teclado]
- Pull-to-refresh: [sí/no]

### Zonas de interacción
- Acciones primarias mobile: [zona inferior confirmada]
- Acciones destructivas / poco frecuentes: [zona superior]
- Safe areas: [aplicadas]
- Teclado virtual: [comportamiento definido]

### Notificaciones y overlays
- Toasts: [posición + duración + comportamiento de errores]
- Modales: [cuándo se usan + comportamiento de cierre + foco atrapado]
- Bottom sheets: [cuándo se usan + snap points + dismiss]

### Estados del sistema
Para cada flujo principal:
- Loading: [skeleton / spinner / optimistic UI]
- Empty state: [descripción + acción disponible]
- Error: [tipos definidos + mensajes + recovery]
- Success: [cómo se confirma]

### Animaciones — propósito
- Categorías activas en este producto: [lista]
- Categorías descartadas: [lista + motivo]

### Animaciones — duraciones definidas
- [tabla con tipo de animación → duración elegida para este producto]

### Patrones específicos
- Button press: [descripción]
- Long-press: [tipo de indicador de progreso + duración]
- Toggle: [descripción]
- Progress indicators: [lineal / radial / cuándo cada uno]
- Modal enter/exit: [descripción]
- Transición entre pantallas: [dirección + tipo]
- List stagger: [sí/no + delay entre items]

### Reduced-motion
- [tabla: animación original → versión degradada]

### Consistencia de componentes
- Niveles de botón definidos: [lista con criterio de uso de cada uno]
- Estados obligatorios: default / hover / focus / active / disabled / loading
- Regla de gestos: [mapa de gestos → funciones, sin colisiones]

### Restricciones para las demás skills

**→ Skill 4 — Visual:**
- [restricciones: elevaciones permitidas, direcciones de transición, tokens de duración,
  comportamiento de sombras en hover, etc.]

**→ Skill 5 — Writing:**
- [restricciones: textos de empty states, labels de botones por tipo, mensajes de error
  por categoría, textos de confirmación en acciones destructivas, etc.]
```

---

### Paso 4 — Generar el artefacto de validación estructural

Antes de cerrar esta skill y pasar a Skill 4 Visual, generar un **artefacto de wireframe
interactivo** que permita validar la arquitectura definida.

El artefacto es en escala de grises, sin tokens visuales, sin tipografía definitiva.
Solo estructura, jerarquía y comportamiento. El diseñador valida que la arquitectura
es correcta antes de que Skill 4 le aplique el sistema visual encima.

**El artefacto debe mostrar:**

**1. Layout base**
La estructura de la pantalla principal con la navegación definida en el Área 2:
- Dónde va la navegación (top, bottom, side)
- Cómo se relacionan las zonas principales de contenido
- Vista mobile y vista desktop side by side si el producto es responsivo

**2. Comportamiento de navegación**
- Si hay drawer: botón que lo abre, el drawer aparece (overlay o push según lo definido)
- Si hay bottom nav: tabs activos e inactivos visibles
- Si hay breadcrumbs: en qué nivel aparecen

**3. Colección de elementos principal**
El componente más importante del producto (cards, lista, grid) en sus dos estados
de resize: desktop y mobile. Mostrando el comportamiento elegido (stack, carrusel, grid).

**4. Estados del sistema**
Para el flujo principal, mostrar los cuatro estados en una grilla:
- Loading (skeleton)
- Empty state (con placeholder de acción)
- Error state (con placeholder de mensaje y recovery)
- Estado con contenido (el estado normal)

**5. Un flujo clave interactivo**
Si hay formulario o flujo crítico definido: renderizarlo navegable con los pasos,
la validación inline, y el estado de error de un campo. Sin datos reales — con
placeholders que representen la estructura.

**Instrucción de generación:**
- Paleta: solo grises (#F8F8F8 fondo, #E0E0E0 bordes, #BDBDBD elementos secundarios,
  #757575 texto secundario, #212121 texto principal, #1976D2 único color de acento
  para indicar elementos interactivos o activos)
- Tipografía: system font stack (no importar fuentes externas en el wireframe)
- Todos los componentes usan CSS custom properties para que Skill 6 pueda
  reemplazarlos con los tokens reales de Skill 4 sin reescribir el artefacto
- El artefacto tiene que ser autocontenido y navegable

**Después de renderizar, preguntar:**

> "¿La estructura y el comportamiento se ven como lo imaginabas?
> Podemos ajustar la navegación, el layout o los estados antes de pasar al sistema visual."

Iterar sobre el artefacto según el feedback. No avanzar a Skill 4 hasta que
la estructura esté validada.

---

## Reglas de comportamiento

- **Consumir el contexto disponible.** No re-preguntar lo que ya está en Skill 0, 1 o 2.
  Leer y aplicar. Solo preguntar lo que genuinamente falta.
- **Cuando el diseñador no sabe:** aplicar la convención más establecida para ese patrón
  y documentarla como supuesto revisable. Las convenciones existen porque reducen la
  carga cognitiva del usuario.
- **Explicar el trade-off, no solo la opción.** "Overlay vs push" tiene implicancias
  reales en la experiencia — el diseñador tiene que entenderlas para decidir bien.
- **Las decisiones de esta skill son vinculantes para Skill 4.** Los tokens de duración,
  las direcciones de animación, los estados de componentes — todo lo que se define aquí
  la skill de Visual no puede contradecirlo, solo refinarlo visualmente.
- **Adaptar el idioma.** Mismo idioma y registro que usa el diseñador.

---

## Conexión con el stack

| Dirección | Detalle |
|-----------|---------|
| Recibe de Skill 0 | Dispositivos, acción principal, frecuencia, experiencia objetivo, restricciones técnicas |
| Recibe de Skill 1 | Accesibilidad motora, reduced-motion, carga cognitiva, patrones a auditar |
| Recibe de Skill 2 | Flujos obligatorios de compliance, restricciones de visibilidad por rol |
| Entrega a Skill 4 | Tokens de duración, direcciones de transición, estados de componentes, comportamiento de elevaciones |
| Entrega a Skill 5 | Labels de botones, textos de estados, mensajes de error, textos de confirmación |
| Entrega a Skill 6 | Artefacto de wireframe con CSS custom properties listas para recibir tokens visuales |

Cuando se usa de forma independiente, el Documento de Interacción es un entregable
autosuficiente: puede usarse como especificación técnica para desarrollo, como base
para un design system, o como guía de QA de comportamiento.
