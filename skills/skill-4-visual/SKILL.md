---
name: skill-4-visual
description: >
  Define el sistema visual de un producto digital: identidad, color, tipografía, espaciado,
  elevación, iconografía, imágenes y tokens. Si hay brand existente, lo valida y documenta.
  Si no hay brand, genera una propuesta visual desde cero a partir de preguntas de emoción,
  tono y referencias. Opera en stack recibiendo documentos de Skill 0 (Contexto Base),
  Skill 1 (Accesibilidad), Skill 2 (Compliance) y Skill 3 (Interacción), o de forma
  completamente independiente con una entrevista de contexto reducida. Disparar ante frases
  como "cómo tiene que verse", "qué colores uso", "qué tipografía elijo", "necesito un
  sistema visual", "quiero definir el estilo", "no tengo brand". Al detectar que aplica,
  confirmar antes de iniciar: "¿Arrancamos con la definición visual? Primero voy a entender
  qué existe y qué hay que construir, y después vamos área por área."
---

# Skill 4 — Visual

Esta skill define el sistema visual completo del producto y produce un **Documento Visual**
con decisiones concretas, valores de tokens, y restricciones para la skill de Writing.

Opera en dos modos:
- **Modo validación:** hay brand existente. La skill lo lee, detecta gaps, y documenta
  lo que falta para que el sistema sea completo.
- **Modo generación:** no hay brand. La skill hace preguntas de emoción y referencias,
  y propone un sistema visual desde cero.

---

## Protocolo de ejecución

### Paso 1 — Detectar contexto disponible

**De Skill 0 — Contexto Base:**
- Sentimiento buscado y palabra clave de la experiencia
- Tipo de producto y modelo de negocio
- Perfil del usuario (edad, nivel tech)

**De Skill 1 — Accesibilidad:**
- Ratio mínimo de contraste (AA o AAA)
- Restricciones de fuentes decorativas
- Modo oscuro: requerido / opcional / no aplica
- Animaciones permitidas y prohibidas

**De Skill 2 — Compliance:**
- Elementos de UI obligatorios y su posicionamiento
- Restricciones de diseño de consentimiento (opt-in no puede ser más prominente que opt-out)

**De Skill 3 — Interacción:**
- Tokens de duración de animaciones
- Estados de componentes definidos
- Comportamiento de elevaciones (qué flota, qué está en el plano base)
- Direcciones de transición

**Si no hay ningún documento previo:** preguntar antes de continuar:
1. ¿Existe algún brand, guía visual, o paleta de colores ya definida para este producto?
2. ¿Cuál es la experiencia que se quiere crear? (una palabra o frase: confianza,
   eficiencia, energía, calidez, precisión, modernidad, etc.)
3. ¿Quién es el usuario principal? (edad, contexto, nivel tech)

---

### Paso 2 — Detectar el modo

Preguntar directamente:

> "¿Existe ya algún brand, guía visual, logo, o paleta de colores para este producto?
> ¿O partimos de cero?"

**Si hay brand existente → Modo validación (ir al Paso 3A)**
**Si no hay brand → Modo generación (ir al Paso 3B)**

---

### Paso 3A — Modo validación (brand existente)

Pedir al diseñador que comparta lo que tiene. Puede ser:
- Un link a una guía de estilo
- Colores en hex / tokens existentes
- Tipografías usadas
- Capturas de pantalla del producto actual

Evaluar lo que se recibe contra esta checklist. Por cada ítem faltante,
preguntar o proponer:

**Color:**
- ¿Hay color primario, secundario y neutrales definidos?
- ¿Hay colores semánticos? (error, éxito, warning, info)
- ¿Hay versión de modo oscuro?
- ¿Los colores existentes pasan el ratio de contraste definido en Skill 1?
  → Si no pasan: alertar y proponer ajuste. No modificar sin confirmación del diseñador.

**Tipografía:**
- ¿Hay tipografía definida para cuerpo, títulos y UI (labels, botones)?
- ¿Hay escala tipográfica? (tamaños por nivel jerárquico)
- ¿La tipografía existente es legible en los tamaños mínimos definidos en Skill 1?

**Espaciado:**
- ¿Hay una escala de espaciado? (o solo valores sueltos)
- ¿Los componentes existentes usan la escala o tienen valores arbitrarios?

**Elevación:**
- ¿Hay sistema de sombras definido?

**Iconografía:**
- ¿Hay un set de iconos definido? ¿Es consistente en estilo?

Documentar qué existe y qué hay que completar. Proceder área por área
solo para los gaps detectados.

---

### Paso 3B — Modo generación (sin brand)

Hacer las preguntas de identidad antes de proponer nada. No generar sin entender.
Un bloque por turno.

#### Bloque 1 — Emoción y tono

> "Antes de elegir colores o tipografías, necesito entender qué tiene que
> transmitir este producto. Respondé lo que puedas — no hay respuestas incorrectas."

1. Si este producto fuera una persona, ¿cómo sería? (formal / informal, joven / maduro,
   preciso / cálido, serio / juguetón, minimalista / expresivo)

2. ¿Qué tiene que sentir el usuario cuando lo usa? Elegir las que apliquen:
   - Confianza y seguridad
   - Eficiencia y control
   - Energía y motivación
   - Calma y claridad
   - Curiosidad y descubrimiento
   - Pertenencia y comunidad
   - Prestigio y exclusividad
   - Diversión y ligereza

3. ¿Hay productos, apps, o marcas (del rubro o de otro rubro) cuyo visual te gusta
   o se acerca a lo que buscas? No tiene que ser competencia directa.
   (Ejemplos: "me gusta cómo se ve Linear", "algo como la estética de Apple pero
   más cálido", "pienso en algo como Notion pero con más personalidad")

#### Bloque 2 — Restricciones de identidad

4. ¿Hay algún color que definitivamente no puede estar? (por competencia, por
   connotación negativa en el contexto, por preferencia del cliente)

5. ¿Hay alguna restricción tipográfica? (fuentes de pago que no se pueden usar,
   fuentes corporativas ya existentes, necesidad de soporte para caracteres
   especiales o idiomas no latinos)

6. ¿El producto necesita sentirse parte de un ecosistema mayor? (una empresa, una
   marca paraguas, una familia de productos) ¿O es completamente independiente?

#### Bloque 3 — Propuesta visual interactiva

Con las respuestas anteriores y el contexto de las skills previas, generar un
**artefacto visual renderizable** — no un documento de texto.

El artefacto es un React component (o HTML/CSS si el entorno no soporta React) que
funciona como un style guide preview interactivo. El diseñador lo ve, lo evalúa, y
solo después de dar el ok se genera el documento de tokens.

**El artefacto debe mostrar, en este orden:**

**1. Concepto**
2-3 oraciones sobre la dirección visual y por qué responde al sentimiento buscado.
Mostrar con la tipografía y el color ya aplicados — no en texto plano.

**2. Paleta de color**
- Cada color como un bloque visual con: muestra de color, nombre del rol, valor hex
- Agrupados por categoría: primarios, neutrales, semánticos
- Cada neutral mostrado sobre fondo blanco Y sobre fondo oscuro
- Indicador de ratio de contraste junto a cada color que va a usarse con texto:
  valor numérico + badge AA/AAA/✗

**3. Tipografía en vivo**
- Cada nivel de la escala renderizado con la fuente real (usar Google Fonts import
  si es una fuente web, o font-family stack si es sistema)
- Mostrar: nivel, tamaño en rem y px, peso, line-height, y un texto de ejemplo real
  (no "Lorem ipsum" — usar texto del dominio del producto)
- Mostrar al menos: Display, H1, H2, Body, Body small, Label, Caption

**4. Espaciado**
- Escala visual: barras horizontales de cada tamaño de espaciado con su valor en px
- Dos ejemplos de componente con la densidad elegida (compacta vs espaciosa)

**5. Elevación**
- Cards apiladas que muestran las 5 capas del sistema de elevación
- Cada capa con su nombre, nivel, y valor de shadow

**6. Componentes de muestra**
Renderizar con el sistema aplicado:
- Un botón primario, uno secundario, uno destructivo — con sus estados (hover, disabled)
- Un campo de input — con estado default, focus, error
- Una card de contenido — con el espaciado, radio y elevación correctos
- Un badge / tag en color semántico (error, éxito, warning)

**7. Si aplica modo oscuro:**
Toggle que cambia entre modo claro y oscuro en tiempo real para todos los elementos.

---

**Instrucción de generación del artefacto:**

Usar solo Google Fonts disponibles en CDN para tipografías web.
Usar CSS custom properties (variables) para todos los tokens — no valores hardcodeados.
El artefacto tiene que ser autocontenido: funcionar sin imports externos salvo
Google Fonts y React si aplica.
Los ratios de contraste se calculan en el código con la fórmula WCAG (luminancia
relativa) — no se declaran a mano.

---

**Después de renderizar el artefacto, preguntar:**

> "¿Esta dirección se acerca a lo que imaginas? Podemos ajustar colores, tipografía,
> densidad o cualquier decisión antes de generar el documento final."

Iterar sobre el artefacto según el feedback. Cada ajuste se refleja en el artefacto
antes de avanzar al Paso 4.

No generar el Documento de Tokens hasta recibir confirmación explícita del diseñador.

---

### Paso 4 — Generar los tokens

Una vez validada la dirección visual (modo generación) o completados los gaps
(modo validación), documentar todo como tokens con nomenclatura consistente.

**Formato de nomenclatura recomendado:**
`[categoría]-[rol]-[variante]`

Ejemplos:
```
color-primary-default: #[hex]
color-primary-hover: #[hex]
color-primary-active: #[hex]
color-primary-disabled: #[hex]

color-neutral-900: #[hex]
color-neutral-500: #[hex]
color-neutral-100: #[hex]

color-semantic-error: #[hex]
color-semantic-success: #[hex]

typography-size-h1: 2rem
typography-size-body: 1rem
typography-weight-regular: 400
typography-weight-medium: 500
typography-weight-bold: 700
typography-lineheight-body: 1.5

spacing-xs: 4px
spacing-sm: 8px
spacing-md: 16px
spacing-lg: 24px
spacing-xl: 32px
spacing-2xl: 48px
spacing-3xl: 64px

elevation-1: 0 1px 3px rgba(0,0,0,0.12)
elevation-2: 0 4px 6px rgba(0,0,0,0.12)
elevation-3: 0 10px 20px rgba(0,0,0,0.15)
elevation-4: 0 20px 40px rgba(0,0,0,0.2)

radius-sm: 4px
radius-md: 8px
radius-lg: 16px
radius-full: 9999px
```

Incluir también los tokens de animación definidos en Skill 3:
```
motion-duration-instant: 100ms
motion-duration-fast: 200ms
motion-duration-normal: 300ms
motion-duration-slow: 500ms
motion-easing-default: ease-out
motion-easing-enter: ease-out
motion-easing-exit: ease-in
motion-easing-spring: cubic-bezier(0.34, 1.56, 0.64, 1)
```

---

### Paso 5 — Generar el Documento Visual completo

```
## VISUAL — [Nombre del producto]

### Modo de operación
- [Validación de brand existente / Generación desde cero]

### Concepto visual
- [Descripción de la dirección visual y su relación con la experiencia objetivo]

### Sistema de color
[paleta completa con hex y roles]
[verificación de contraste contra requisitos de Skill 1]
[modo oscuro si aplica]

### Sistema tipográfico
[fuentes elegidas con justificación]
[escala completa con valores rem y px]
[pesos y line heights]

### Sistema de espaciado
[base unit + escala + densidad]

### Sistema de elevación
[capas 0-5 con valores de shadow]

### Iconografía
[estilo + set + tamaños + uso de color]

### Imágenes y media
[ratio + tratamiento + estilo + placeholder]

### Tokens completos
[lista de todos los tokens con nombre y valor]

### Restricciones para Skill 5 — Writing
- Tipografía máxima para microcopy: [nivel de escala]
- Tono visual que el lenguaje debe reforzar: [descripción]
- Elementos de UI con texto fijo (no editable por writing): [lista]
- Textos que forman parte del sistema visual (onboarding illustrations, empty states
  con ilustración): [lista]
```

---

## Reglas de comportamiento

- **No proponer sin entender.** En modo generación, las preguntas del Bloque 1 y 2
  son obligatorias. Una paleta de colores sin responder "qué tiene que transmitir"
  es decoración aleatoria.
- **Verificar contraste siempre.** Cada color propuesto se verifica contra el ratio
  definido en Skill 1 antes de incluirlo en el documento. Si no pasa, ajustar y declarar
  el ajuste.
- **No cerrar la propuesta sin confirmación.** En modo generación, la propuesta es una
  hipótesis. El diseñador la valida o la ajusta. No es el output final hasta que haya
  confirmación explícita.
- **Cuando el diseñador no sabe:** en modo validación, completar el gap con la opción
  más coherente con lo que ya existe y documentarlo como supuesto revisable. En modo
  generación, la propuesta entera es una recomendación fundamentada — no un "no sé".
- **Los tokens son el output más importante.** El documento visual vale por los tokens
  que produce. Sin tokens, el sistema no es usable por desarrollo.
- **Adaptar el idioma.** Mismo idioma y registro que usa el diseñador.

---

## Conexión con el stack

| Dirección | Detalle |
|-----------|---------|
| Recibe de Skill 0 | Sentimiento buscado, tipo de producto, perfil de usuario |
| Recibe de Skill 1 | Ratio de contraste, restricciones tipográficas, modo oscuro, animaciones |
| Recibe de Skill 2 | Posicionamiento de elementos obligatorios, restricciones de diseño de consentimiento |
| Recibe de Skill 3 | Tokens de duración, estados de componentes, comportamiento de elevaciones |
| Entrega a Skill 5 | Escala tipográfica, tono visual, tokens de texto, elementos con texto fijo |
| Entrega a Skill 6 | Sistema visual completo y todos los tokens |

Cuando se usa de forma independiente, el Documento Visual es un entregable
autosuficiente: puede usarse como base de un design system, como brief para un
diseñador visual, o como especificación de tokens para desarrollo.
