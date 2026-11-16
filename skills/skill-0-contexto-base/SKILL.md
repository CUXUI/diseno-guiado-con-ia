---
name: skill-0-contexto-base
description: >
  Establece el contexto base de un producto digital antes de tomar cualquier decisión de diseño.
  Funciona como Skill 0 del stack de diseño guiado por IA (alimenta las skills de Accesibilidad,
  Interacción, Visual y Writing) pero también opera de forma completamente independiente: produce
  un Documento de Contexto Base útil por sí solo para cualquier proyecto de diseño de producto.
  Disparar ante frases como "quiero crear una app", "tengo un challenge de diseño", "voy a
  diseñar un producto", "ayúdame a armar un prototipo", "estoy pensando en una idea de producto",
  o cualquier mención de un producto digital a construir. Al detectar que esta skill aplica,
  confirmar con el usuario antes de iniciar: "Veo que estás por arrancar un proyecto de diseño.
  ¿Quieres que empecemos definiendo el contexto base del producto? (Esto después te sirve para
  cualquier decisión de diseño que tomes, solo o en conjunto con las otras skills del stack.)"
---

# Skill 0 — Contexto Base del Producto

Esta skill establece el **lenguaje compartido** que alimenta todas las demás skills del stack.
No tomar decisiones de diseño hasta completar este contexto.

---

## Objetivo de esta skill

Obtener toda la información necesaria para fundamentar cualquier decisión de diseño de producto.
El output es un **Documento de Contexto Base** que:
- Usado en stack: alimenta las skills de Accesibilidad, Compliance, Interacción, Visual y Writing
- Usado solo: es un documento de definición de producto completo y autosuficiente

En ambos casos el documento es copiable, editable y reutilizable en futuras conversaciones.

---

## Protocolo de ejecución

### Paso 1 — Detectar cuánto contexto ya existe

Antes de preguntar nada, revisar si en la conversación ya hay información sobre:
- Qué es el producto
- Para quién es
- Cuál es el objetivo principal

Si hay contexto parcial, **no repetir preguntas ya respondidas**. Completar solo lo que falta.

---

### Paso 2 — Entrevista guiada

Hacer las preguntas en bloques. No lanzar todo de una. Esperar respuesta antes de seguir.

#### Bloque A — El producto

1. ¿Qué es este producto? (app, dashboard, e-commerce, herramienta interna, PWA, etc.)
2. ¿Cuál es la acción principal que el usuario va a hacer? (la más frecuente, la más crítica)
3. ¿En qué dispositivos se va a usar principalmente? (mobile, desktop, tablet, wearable, TV)
4. ¿Hay restricciones técnicas conocidas? (framework, librería, acceso offline, limitaciones de plataforma)

#### Bloque B — El usuario

4. ¿Quién es el usuario? Describilo sin usar personas genéricas. Incluir:
   - Edad aproximada o rango
   - Nivel de familiaridad con tecnología
   - Contexto de uso (en movimiento, sentado, con prisa, con tiempo, en voz alta, en silencio)
   - Si tiene alguna necesidad especial relevante (visual, motora, cognitiva, idiomática)

5. ¿Hay más de un tipo de usuario? Si sí, ¿cuál es el principal y cuáles son secundarios?

#### Bloque C — La experiencia que se quiere crear

6. ¿Qué tiene que sentir o lograr el usuario después de usar el producto?
   Ejemplos orientativos (no limitantes):
   - "Completó algo rápido sin pensar demasiado"
   - "Aprendió algo nuevo y quiere volver"
   - "Confía en que lo que hizo está bien hecho"
   - "Se divirtió o sintió satisfacción"
   - "No notó que usó una app, solo pasó algo"

7. ¿Cuál es la frecuencia de uso esperada?
   - Varias veces al día
   - Una vez por día
   - Semanal o esporádico
   - Una sola vez (onboarding, flujo de compra único, etc.)

#### Bloque D — El negocio

8. ¿Cuál es el modelo de negocio? (B2C, B2B, uso interno, herramienta open source, etc.)
9. ¿Qué quiere lograr la organización o el cliente con este producto?
   Ejemplos orientativos: aumentar conversión, reducir churn, bajar tickets de soporte,
   educar usuarios, retener clientes, escalar sin sumar personas, posicionarse en un mercado.
10. ¿Cómo se va a medir que esto funcionó? ¿Qué número o comportamiento cambiaría?
    (aunque sea aproximado: "más gente termina el onboarding", "menos llamadas al soporte",
    "más tiempo dentro de la app", "más compras completadas")

#### Bloque E — Prioridades y trade-offs

11. Si en algún momento hay que elegir entre estas dimensiones, ¿cuál gana?
    Pedir que las ordenen de más a menos importante para este proyecto:
    - Velocidad de desarrollo
    - Calidad de la interacción
    - Profundidad de accesibilidad
    - Estética / impacto visual

    Aclarar: no hay respuesta correcta. El orden cambia según el proyecto.
    Un challenge para demo no tiene el mismo orden que un producto de salud para adultos mayores.

---

### Paso 3 — Detectar el nivel del diseñador

Evaluar en base a las respuestas si el usuario:

| Nivel | Señales |
|-------|---------|
| **Junior / Explorador** | Respuestas vagas, no menciona métricas ni usuarios específicos, no tiene claro el objetivo |
| **Semi-senior / Practicante** | Tiene el problema claro pero no sabe cómo traducirlo en decisiones de diseño |
| **Senior / Experto** | Respuestas precisas, menciona patrones, tiene hipótesis propias |

Según el nivel detectado, **ajustar la profundidad de las preguntas siguientes** en las demás skills.
No comunicarle al usuario su nivel de forma explícita. Solo adaptar el tono y la profundidad.

---

### Paso 4 — Generar el Documento de Contexto Base

Una vez completados los bloques, producir un documento estructurado con este formato:

```
## CONTEXTO BASE — [Nombre del producto o challenge]

### El producto
- Tipo: [app / dashboard / e-commerce / herramienta interna / PWA / etc.]
- Acción principal: [qué hace el usuario con más frecuencia o criticidad]
- Dispositivos: [principal y secundarios]
- Restricciones técnicas: [sí/no + cuáles]

### El usuario principal
- Perfil: [descripción concreta, no persona genérica]
- Nivel tech: [básico / intermedio / avanzado]
- Contexto de uso: [descripción]
- Necesidades especiales detectadas: [sí/no + cuáles]

### Usuarios secundarios (si aplica)
- [lista con diferencias clave respecto al principal]

### Experiencia objetivo
- Sentimiento buscado: [descripción]
- Frecuencia de uso: [varias veces al día / diaria / semanal / única vez]
- Palabra clave de la experiencia: [eficiencia / confianza / enganche / simplicidad / etc.]

### El negocio
- Modelo: [B2C / B2B / uso interno / open source / etc.]
- Objetivo de negocio principal: [qué quiere lograr la organización]
- Métricas de éxito (aproximadas): [qué número o comportamiento cambiaría]

### Prioridades y trade-offs
Orden de importancia para este proyecto específico:
1. [primera prioridad]
2. [segunda]
3. [tercera]
4. [cuarta]
(Opciones: velocidad de desarrollo / calidad de interacción / profundidad de accesibilidad / estética)

### Nivel del diseñador detectado
- [Junior / Semi-senior / Senior]
- Implicancias para las demás skills: [qué ajustar en profundidad y tono]

### Skills recomendadas a continuar
1. Skill 1 — Accesibilidad ← prioridad si hay usuarios con necesidades especiales
2. Skill 2 — Compliance ← se activa solo si el producto opera en jurisdicciones reguladas
   o pertenece a sectores con normativa específica (salud, fintech, educación, menores)
3. Skill 3 — Interacción y Layout
4. Skill 4 — Visual
5. Skill 5 — UX Writing
6. Skill 6 — Composición ← ensambla los outputs de todas las skills en un prototipo navegable
(Pueden usarse en cualquier orden o de forma independiente, excepto Skill 6 que requiere al menos Skill 3 + Skill 4)
```

---

## Reglas de comportamiento

- **No asumir.** Si falta información, preguntar. No inventar perfiles de usuario ni inferir objetivos de negocio. Cada supuesto que se cuele en el documento base contamina todas las decisiones de diseño que vienen después.
- **El entendimiento es el trabajo.** Si el diseñador se impacienta con la cantidad de preguntas, explicarle que una definición sólida ahora evita retrabajo en todas las capas siguientes. Las preguntas no son un obstáculo, son el proceso.
- **Adaptar el idioma.** Si el usuario escribe en español rioplatense, responder en español rioplatense. Si usa inglés, responder en inglés.
- **No hacer todas las preguntas de una.** Bloque por bloque. Esperar respuesta antes de continuar.
- **El documento de contexto es editable.** Antes de cerrarlo, preguntar: "¿Hay algo que corregir o agregar antes de seguir?"

---

## Output esperado

Un **Documento de Contexto Base** completo que pueda ser pegado al inicio de cualquier conversación con las skills siguientes, para que operen sin necesidad de re-preguntar el contexto.

---

## Conexión con el resto del stack

| Skill | Campos que consume de este documento |
|-------|--------------------------------------|
| Skill 1 — Accesibilidad | Necesidades especiales, frecuencia de uso, nivel tech, trade-offs |
| Skill 2 — Compliance | Modelo de negocio, tipo de producto, perfil de usuario (edad, jurisdicción), sector |
| Skill 3 — Interacción | Dispositivos, acción principal, experiencia objetivo, frecuencia, trade-offs |
| Skill 4 — Visual | Sentimiento buscado, modelo de negocio, brand existente, trade-offs |
| Skill 5 — UX Writing | Perfil del usuario, idioma/dialecto, tono, objetivo de negocio |
| Skill 6 — Composición | Nombre del producto, acción principal, dispositivos |

Cuando esta skill se usa de forma independiente (sin el stack), el Documento de Contexto Base
es igualmente válido como entregable: puede compartirse con el equipo, pegarse en Notion,
usarse como brief de proyecto, o servir de base para decisiones de diseño manuales.
