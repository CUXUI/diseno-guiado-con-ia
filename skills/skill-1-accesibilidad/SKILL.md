---
name: skill-1-accesibilidad
description: >
  Define los parámetros de accesibilidad de un producto digital y genera restricciones concretas
  para las demás skills del stack (Interacción, Visual, Writing). Opera en stack recibiendo el
  Documento de Contexto Base de Skill 0, o de forma completamente independiente arrancando con
  una entrevista de contexto reducida. Disparar ante frases como "quiero definir accesibilidad",
  "qué tan accesible tiene que ser", "necesito cumplir WCAG", "estoy diseñando para usuarios con
  discapacidad", "qué nivel de accesibilidad elijo", o cuando el producto involucra usuarios con
  necesidades especiales detectadas en cualquier contexto. Al detectar que esta skill aplica,
  confirmar antes de iniciar: "¿Arrancamos con la definición de accesibilidad? Voy a hacerte
  preguntas por área — algunas pueden sorprenderte si no las habías pensado, pero cada una
  impacta en decisiones concretas de diseño."
---

# Skill 1 — Accesibilidad

Esta skill define los parámetros de accesibilidad del producto y produce un **Documento de
Accesibilidad** con restricciones concretas que las skills de Interacción, Visual y Writing
deben respetar.

Cubre todas las áreas de accesibilidad siempre — especialmente cuando el diseñador es junior
y no sabe lo que no sabe.

---

## Protocolo de ejecución

### Paso 1 — Detectar si hay Contexto Base (Skill 0)

Buscar en la conversación un Documento de Contexto Base. Si existe, extraer:
- Perfil del usuario principal (edad, nivel tech, necesidades especiales)
- Dispositivos principales
- Frecuencia de uso
- Trade-offs definidos (especialmente posición de "profundidad de accesibilidad")
- Nivel del diseñador detectado

**Si no hay Contexto Base**, hacer esta entrevista reducida antes de continuar:

> "Para definir bien la accesibilidad necesito entender tres cosas primero."

1. ¿Quién es el usuario principal? (edad aproximada, nivel de familiaridad con tecnología,
   si tiene alguna necesidad especial conocida — visual, motora, cognitiva, auditiva)
2. ¿En qué dispositivos se va a usar principalmente?
3. ¿Con qué frecuencia lo va a usar? (varias veces al día / diaria / esporádica / única vez)

No continuar hasta tener estas respuestas. Son el piso mínimo para que las recomendaciones
tengan sentido.

---

### Paso 2 — Definir el nivel WCAG global

Presentar las opciones con contexto real, no solo la definición técnica:

> "¿Qué nivel de conformidad WCAG quieres alcanzar como base del producto?"

| Nivel | Qué significa en la práctica |
|-------|------------------------------|
| **A** | El mínimo. Elimina las barreras más graves. Rara vez suficiente para producción. |
| **AA** | El estándar de la industria. Requerido legalmente en muchos países para productos públicos. |
| **AAA** | El nivel más alto. No siempre posible para todo el producto — se aplica por secciones críticas. |

Aclarar: el nivel elegido aquí es el **piso global**. En áreas específicas se puede ir más alto
si el usuario o el contexto lo requieren. Eso se define en el Paso 3.

---

### Paso 3 — Entrevista por áreas

Recorrer todas las áreas. No saltear ninguna. Si el diseñador no entiende el área, explicarla
con un ejemplo concreto antes de preguntar.

Hacer un área por turno. Esperar respuesta antes de continuar.

---

#### Área 1 — Contraste y percepción visual

Preguntar:
- ¿El producto puede usarse en condiciones de luz variable? (exterior, sol directo, oscuridad)
- ¿Hay usuarios con baja visión, daltonismo, o sensibilidad a la luz?
- ¿Existe modo oscuro como requerimiento, o es opcional?

Según el nivel WCAG elegido, informar el ratio de contraste mínimo que aplica:
- AA: 4.5:1 para texto normal, 3:1 para texto grande y componentes UI
- AAA: 7:1 para texto normal, 4.5:1 para texto grande

Si el diseñador no sabe qué es un ratio de contraste, explicarlo brevemente con un ejemplo
("blanco sobre gris claro falla AA, blanco sobre gris oscuro lo pasa").

---

#### Área 2 — Tipografía y legibilidad

**Requerimiento fijo (no preguntar):** el texto usa unidades relativas (rem/em) para respetar
el tamaño de fuente configurado por el usuario en su sistema operativo. Solo se rompe si hay
una restricción técnica declarada explícitamente. No es una variable de diseño, es una base.

Preguntar:
- ¿Hay usuarios mayores de 60 años o con baja visión?
- ¿El texto va a aparecer sobre fondos complejos como imágenes o gradientes?

Definir según respuestas:
- Tamaño mínimo de cuerpo de texto
- Si hay restricciones sobre uso de fuentes decorativas o de baja legibilidad

---

#### Área 3 — Carga cognitiva

**Si hay Contexto Base (Skill 0):** el contexto de uso ya está definido (Bloque B, pregunta 4).
No re-preguntar. Leer ese dato y usarlo directamente.
**Si no hay Contexto Base:** preguntar "¿En qué situaciones y contexto físico va a usar el
producto el usuario? (moviéndose, sentado, bajo presión, en silencio, con prisa)"

Preguntar siempre:
- ¿Hay usuarios con TDAH, dislexia, o cualquier diferencia cognitiva relevante?

**Sobre memoria de trabajo — no preguntar, detectar:**
Obligar al usuario a recordar información entre pantallas es una falla de diseño, no una
variable de accesibilidad. Sin embargo, ciertos patrones la demandan sin que el diseñador
lo note. La skill los señala preventivamente:

> Patrones de riesgo a revisar cuando los componentes estén definidos (Skill 2):
> - Formularios multipaso sin resumen de progreso visible
> - Dashboards con datos que no persisten en pantalla al navegar
> - Flujos donde el resultado de un paso no se muestra en el siguiente
> - Navegación sin breadcrumbs en estructuras de más de 2 niveles de profundidad

Documentar en el output como "patrones a auditar en Skill 2", no como restricción cerrada.

Definir según respuestas:
- Cantidad máxima de opciones por pantalla según contexto de uso y perfil cognitivo
- Si se necesita confirmación antes de acciones irreversibles
- Nivel de lectura objetivo del contenido y microcopy

---

#### Área 4 — Movimiento y animaciones

Preguntar:
- ¿Hay usuarios con sensibilidad al movimiento (vestibular disorders, epilepsia fotosensible)?
- ¿El producto tiene o planea tener animaciones, transiciones, o elementos en movimiento?
- ¿Qué tan central es el movimiento para la experiencia? (decorativo vs. funcional)

Definir según respuestas:
- Si se requiere `prefers-reduced-motion` como soporte obligatorio
- Tipos de animación permitidos o prohibidos
- Si las animaciones funcionales necesitan alternativa estática

---

#### Área 5 — Interacción motora

Preguntar:
- ¿El producto puede ser usado con una sola mano? ¿Es un requerimiento?
- ¿Hay usuarios con movilidad reducida, temblor, o uso de dispositivos de asistencia?
- ¿Se espera uso con guantes, en movimiento, o en condiciones de precisión reducida?

Definir según respuestas:
- Tamaño mínimo de áreas táctiles (WCAG recomienda 44x44px; AAA sube a 44x44px con
  espaciado adicional)
- Si los gestos complejos (swipe, pinch, hold) necesitan alternativa de un solo toque
- Si el foco de teclado tiene que ser visible y navegable completamente

---

#### Área 6 — Accesibilidad auditiva

Preguntar:
- ¿El producto usa audio como parte de la experiencia? (notificaciones, feedback, contenido)
- ¿Hay usuarios con hipoacusia o sordera?
- ¿El producto puede usarse en entornos de silencio obligatorio o ruido extremo?

Definir según respuestas:
- Si todo el contenido de audio necesita alternativa visual o textual
- Si los controles de audio deben ser siempre visibles (sin autoplay sin control)
- Si se necesitan subtítulos o transcripciones

---

#### Área 7 — Compatibilidad con tecnología asistiva

Preguntar:
- ¿Se espera uso con lectores de pantalla? (VoiceOver, TalkBack, NVDA)
- ¿El producto tiene que funcionar con teclado únicamente, sin mouse ni touch?
- ¿Hay requerimientos de soporte para voz? (voice control, dictado)

Definir según respuestas:
- Nivel de semántica HTML requerido
- Si todos los elementos interactivos necesitan labels accesibles
- Si el orden de foco tiene que estar explícitamente definido
- Si se necesita testing con lector de pantalla como parte del proceso

---

### Paso 4 — Validación cruzada

**Detectar el modo antes de ejecutar:**

**Modo audit** (hay decisiones de diseño, componentes, o un producto existente): ejecutar
la validación cruzada completa. Detectar contradicciones entre lo definido en esta skill
y las decisiones de diseño ya tomadas. Mostrar cada conflicto y preguntar cómo resolver
antes de continuar. No decidir por el diseñador.

**Modo stack desde cero** (se está definiendo el producto, aún no hay componentes ni
decisiones de interacción): omitir la validación activa. En cambio, agregar al documento
una sección de "Combinaciones de riesgo a verificar en Skill 3" con los conflictos
potenciales según lo definido en esta skill:

| Combinación a vigilar | Por qué es riesgo |
|-----------------------|-------------------|
| Scroll lateral en cards + accesibilidad motora alta | Puede ser inaccesible para usuarios con movilidad reducida |
| Animaciones de enganche + sensibilidad al movimiento | Las microinteracciones de gamificación pueden afectar a usuarios con trastornos vestibulares |
| Fuente decorativa + baja visión | Las fuentes de display pueden fallar en legibilidad |
| Gestos complejos (hold, swipe) + movilidad reducida | Requieren alternativa de toque simple o botón visible |
| Texto sobre imagen + condiciones de luz variable | Alto riesgo para legibilidad si no hay overlay garantizado |

Estas combinaciones no son errores todavía — son señales de alerta que Skill 3 tiene que
revisar cuando defina los componentes.

---

### Paso 5 — Generar el Documento de Accesibilidad

```
## ACCESIBILIDAD — [Nombre del producto]

### Nivel base
- WCAG: [A / AA / AAA]
- Excepciones por área: [si alguna área tiene nivel distinto al global, listarlo aquí]

### Área 1 — Contraste y percepción visual
- Ratio mínimo de contraste: [valor]
- Modo oscuro: [requerido / opcional / no aplica]
- Condiciones de uso variable: [sí/no + implicancias]

### Área 2 — Tipografía y legibilidad
- Texto escalable (rem/em): requerido por defecto
- Tamaño mínimo de cuerpo: [valor]
- Fondos complejos: [confirmado / supuesto — revisable en Skill 3]
- Restricciones de fuentes: [sí/no + cuáles]

### Área 3 — Carga cognitiva
- Contexto de uso: [tomado de Skill 0 / declarado aquí]
- Máximo de opciones por pantalla: [número]
- Confirmación en acciones irreversibles: [sí/no]
- Nivel de lectura objetivo: [simple / estándar / técnico]
- Diferencias cognitivas relevantes: [sí/no + cuáles]
- Patrones de memoria de trabajo a auditar en Skill 2: [lista]

### Área 4 — Movimiento y animaciones
- prefers-reduced-motion: [obligatorio / recomendado / no aplica]
- Tipos de animación permitidos: [lista]
- Tipos de animación prohibidos: [lista]
- Alternativa estática requerida: [sí/no]

### Área 5 — Interacción motora
- Tamaño mínimo de área táctil: [valor en px]
- Uso con una sola mano: [requerido / no requerido]
- Gestos complejos con alternativa: [sí/no + cuáles]
- Navegación por teclado: [requerida / no requerida]

### Área 6 — Accesibilidad auditiva
- Contenido de audio con alternativa: [sí/no]
- Subtítulos / transcripciones: [requeridos / no requeridos]
- Autoplay sin control: [prohibido / permitido]

### Área 7 — Tecnología asistiva
- Soporte para lector de pantalla: [requerido / no requerido]
- Navegación por teclado completa: [requerida / no requerida]
- Labels accesibles en todos los interactivos: [sí/no]
- Testing con lector de pantalla: [obligatorio / recomendado / no aplica]

### Combinaciones de riesgo a verificar en Skill 3
- [lista de combinaciones potencialmente problemáticas según lo definido arriba]

### Contradicciones detectadas y resolución (solo en modo audit)
- [lista de conflictos encontrados y cómo se resolvieron]

### Restricciones para las demás skills

**→ Skill 3 — Interacción:**
- [lista de restricciones concretas]

**→ Skill 4 — Visual:**
- [lista de restricciones concretas]

**→ Skill 5 — Writing:**
- [lista de restricciones concretas]
```

---

## Reglas de comportamiento

- **Cubrir todas las áreas siempre.** Un diseñador junior no sabe lo que no sabe. No preguntar
  cuáles áreas le importan — recorrerlas todas y que el diseñador decida el nivel en cada una.
- **Cuando el diseñador no sabe:** aplicar la restricción más conservadora posible para esa
  pregunta y documentarla como supuesto revisable. Nunca dejar un campo sin definir porque
  la respuesta fue "no sé". Un supuesto declarado es mejor que un vacío.
- **Explicar antes de preguntar** cuando el área es técnica o poco conocida. Un ejemplo concreto
  vale más que la definición.
- **No decidir por el diseñador** cuando hay una contradicción. Mostrarla, explicar el impacto,
  y preguntar cómo resolver.
- **Las restricciones son el output más importante.** El documento vale por las restricciones
  que genera para las demás skills, no solo por la definición interna.
- **Adaptar el idioma.** Mismo idioma y registro que usa el diseñador.

---

## Conexión con el stack

| Dirección | Detalle |
|-----------|---------|
| Recibe de Skill 0 | Perfil de usuario, dispositivos, frecuencia, trade-offs |
| Entrega a Skill 2 | Perfil de usuario con necesidades especiales (relevante para COPPA, salud) |
| Entrega a Skill 3 | Restricciones de interacción motora, movimiento, gestos |
| Entrega a Skill 4 | Restricciones de contraste, tipografía, animaciones |
| Entrega a Skill 5 | Restricciones de nivel de lectura, labels, lenguaje |
| Entrega a Skill 6 | Restricciones de accesibilidad aplicadas al prototipo (touch targets, reduced-motion) |

Cuando se usa de forma independiente, el Documento de Accesibilidad es un entregable
autosuficiente: puede usarse como checklist de QA, brief para el equipo de desarrollo,
o base para una auditoría de accesibilidad.
