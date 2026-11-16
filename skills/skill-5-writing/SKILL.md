---
name: skill-5-writing
description: >
  Define la voz, tono, reglas de escritura y microcopy de un producto digital. Genera
  ejemplos de microcopy concretos y listos para usar, y al final pregunta al diseñador
  si quiere llevarse los ejemplos aplicados a sus componentes, solo la guía de estilo,
  o ambos. Opera en stack recibiendo documentos de Skill 0 (Contexto Base), Skill 1
  (Accesibilidad), Skill 2 (Compliance), Skill 3 (Interacción) y Skill 4 (Visual), o
  de forma completamente independiente con una entrevista de contexto reducida. Disparar
  ante frases como "cómo tiene que hablar el producto", "qué texto pongo en el botón",
  "cómo escribo los errores", "necesito el tono de voz", "qué dice el empty state",
  "cómo suena la app". Al detectar que aplica, confirmar antes de iniciar: "¿Arrancamos
  con la definición de voz y writing? Voy a hacer preguntas sobre cómo tiene que sonar
  el producto, y después voy a generar ejemplos concretos de microcopy para que puedas
  ver cómo se aplica antes de decidir qué te llevas."
---

# Skill 5 — UX Writing y Microcopy

Esta skill define cómo habla el producto y produce dos outputs posibles según lo que
elija el diseñador: una **Guía de Voz y Tono** con reglas aplicables, ejemplos de
**Microcopy listo para usar** por tipo de componente, o ambos.

---

## Protocolo de ejecución

### Paso 1 — Detectar contexto disponible

**De Skill 0 — Contexto Base:**
- Perfil del usuario (edad, nivel tech, contexto de uso)
- Idioma principal del producto
- Experiencia objetivo y palabra clave de la experiencia
- Modelo de negocio y objetivo de la organización

**De Skill 1 — Accesibilidad:**
- Nivel de lectura objetivo (simple / estándar / técnico)
- Restricción de ironía o lenguaje figurado (si accesibilidad cognitiva es alta)
- Labels descriptivos requeridos (no "OK", no "Click aquí")

**De Skill 2 — Compliance:**
- Terminología legal requerida por jurisdicción
- Textos de consentimiento con requerimientos específicos
- Textos que no pueden modificarse libremente (política de privacidad, T&C)

**De Skill 3 — Interacción:**
- Tipos de botón definidos y su criterio de uso
- Categorías de mensajes de error por tipo (red, validación, permisos, servidor)
- Textos de confirmación en acciones destructivas
- Empty states identificados (nuevo / sin resultados / completado)

**De Skill 4 — Visual:**
- Tono visual que el lenguaje debe reforzar
- Elementos con texto fijo (parte del sistema visual, no editable)
- Escala tipográfica (impacta en longitud máxima de textos por nivel)

**Si no hay ningún documento previo:** preguntar antes de continuar:
1. ¿Para quién es el producto? (perfil del usuario, edad aproximada, nivel tech)
2. ¿En qué idioma y variante? (español rioplatense / neutro / España; inglés US / UK / etc.)
3. ¿Qué tiene que sentir el usuario cuando lee los textos del producto?
4. ¿Hay componentes específicos para los que necesitas microcopy ahora?

---

### Paso 2 — Entrevista de voz y tono

Hacer un bloque por turno. Esperar respuesta antes de continuar.

#### Bloque 1 — Idioma y variante

Si no está definido en Skill 0, preguntar:

1. ¿En qué idioma principal opera el producto?
2. Si es español: ¿qué variante?
   - **Rioplatense** (Argentina, Uruguay): vos/ustedes, vocabulario local, tono más cercano
   - **Neutro latinoamericano**: tú/ustedes, sin modismos regionales, para múltiples países
   - **España**: vosotros, vocabulario propio, registro diferente
   - **Otro:** especificar
3. Si es inglés: ¿US, UK, AU, o neutro internacional?
4. ¿El producto va a estar en más de un idioma? Si sí: ¿hay un idioma base desde el que
   se traduce? Esto afecta la longitud de los textos — el español es ~30% más largo que
   el inglés, el alemán más aún.

#### Bloque 2 — Personalidad de la voz

> "La voz del producto es constante — es su personalidad. El tono cambia según el
> contexto (un error no suena igual que una celebración). Primero definimos la voz."

5. De estos pares, ¿dónde se ubica el producto? (puede estar en el medio)

   | Extremo A | · · · · · | Extremo B |
   |-----------|-----------|-----------|
   | Formal | | Informal |
   | Técnico | | Accesible |
   | Distante | | Cercano |
   | Serio | | Juguetón |
   | Institucional | | Humano |
   | Neutro | | Con personalidad |

6. ¿Hay marcas o productos cuya forma de hablar te gusta o se acerca a lo que buscas?
   (No tiene que ser del mismo rubro. Ejemplos: "me gusta cómo habla Duolingo", "algo
   como Notion pero más cálido", "serio como Bloomberg pero sin ser frío")

7. ¿Hay algo que el producto definitivamente **no** tiene que sonar?
   (Ejemplos: "no quiero que suene corporativo", "nada de emojis", "nada de exclamaciones",
   "no quiero que tutee al usuario")

#### Bloque 3 — Reglas de escritura

Algunas de estas pueden inferirse del contexto. Si ya hay respuesta clara de las skills
previas, no preguntar — aplicar directamente.

8. ¿El producto tutea o ustedea al usuario? (si no está claro por el dialecto elegido)
9. ¿Se usan emojis? ¿En qué contextos? (nunca / solo en celebraciones / libremente)
10. ¿El tono puede usar humor? ¿De qué tipo? (sutil / evidente / nunca)
    → Aclarar: el humor en UI tiene riesgo alto en errores o momentos de fricción.
    Un empty state puede tener un toque de humor. Un mensaje de pérdida de datos, nunca.

---

### Paso 3 — Definir la guía de voz y tono

Con las respuestas anteriores, construir la guía. Este es un documento interno de la skill
— no se muestra al diseñador hasta el Paso 5. Se usa para generar los ejemplos del Paso 4.

```
VOZ Y TONO — [Nombre del producto]

IDIOMA Y VARIANTE
- Idioma: [idioma]
- Variante: [variante]
- Pronombre de segunda persona: [vos / tú / usted / you]
- Plurales: [ustedes / vosotros / you all]
- Consideraciones de longitud si hay internacionalización: [sí/no + detalle]

PERSONALIDAD DE LA VOZ
- [3-5 adjetivos que definen la voz, con descripción de qué significa cada uno
  en la práctica]
  Ejemplo: "Directo — va al punto, no usa frases de relleno ni eufemismos"
           "Cercano — habla como una persona, no como un sistema"
           "Confiable — no promete lo que no puede cumplir"

LO QUE NUNCA HACEMOS
- [lista de prohibiciones concretas con ejemplo de qué NO escribir]

TONO POR CONTEXTO
- Éxito / celebración: [descripción + nivel de entusiasmo permitido]
- Error crítico: [descripción — generalmente más neutral, sin culpar al usuario]
- Error de validación: [descripción — directo, sin drama]
- Instrucción / onboarding: [descripción]
- Acción destructiva / advertencia: [descripción — claro y sin ambigüedad]
- Estado vacío: [descripción — puede tener más personalidad que otros contextos]
- Carga / espera: [descripción]

REGLAS DE ESCRITURA
- Longitud de botones: [máximo X palabras]
- Longitud de mensajes de error: [máximo X palabras / X caracteres]
- Longitud de tooltips: [máximo X palabras]
- Longitud de notificaciones: [máximo X palabras]
- Mayúsculas: [sentence case / title case / todo minúsculas / según contexto]
- Puntuación en UI: [sin punto final en labels / con punto en párrafos / etc.]
- Voz activa: [siempre / preferida / según contexto]
- Números: [dígitos (3) o palabras (tres) / regla para cuándo usar cada uno]
- Emojis: [sí/no + contextos permitidos]
- Humor: [sí/no + tipo + contextos donde aplica y donde está prohibido]

GLOSARIO — TÉRMINOS PROPIOS
- [Nombre del concepto en el producto]: [definición + nota de uso]
- [Palabra prohibida]: [por qué + alternativa preferida]

TÉRMINOS RESERVADOS POR COMPLIANCE (no modificar)
- [lista de textos legales fijos de Skill 2]
```

---

### Paso 4 — Generar microcopy concreto

Con la guía construida en el Paso 3 y el contexto de componentes de Skill 3,
generar ejemplos reales para cada tipo de componente.

Si hay información específica del producto (nombre del producto, nombre de las
secciones, tipo de contenido), usarla. No generar con placeholders genéricos.

#### Botones

Para cada tipo de botón definido en Skill 3, generar al menos 3 ejemplos en contexto:

```
BOTÓN PRIMARIO
Regla: verbo en infinitivo + objeto si es necesario. Sin "Por favor". Sin "Click aquí".
Ejemplos en contexto:
- Guardar cambios
- Crear proyecto
- Confirmar pedido
- Enviar solicitud
NO: "Aceptar", "OK", "Enviar", "Continuar" (sin contexto)

BOTÓN SECUNDARIO
Regla: acción alternativa clara. Nunca "Cancelar" como única opción frente a una
acción destructiva — dar siempre la alternativa positiva primero.
Ejemplos:
- Volver a editar (frente a "Eliminar cuenta")
- Guardar borrador (frente a "Publicar")
- Omitir por ahora (frente a "Completar perfil")

BOTÓN DESTRUCTIVO
Regla: nombrar exactamente la consecuencia. El usuario tiene que saber qué va a pasar.
Ejemplos:
- Eliminar proyecto (no "Eliminar")
- Cancelar suscripción (no "Continuar")
- Borrar todos los datos (no "Resetear")

LINK / ACCIÓN TERCIARIA
Regla: describe el destino o la acción. Nunca "haga click aquí" o "ver más" sin contexto.
Ejemplos:
- Ver historial de cambios
- Leer los términos completos
- ¿Olvidaste tu contraseña?
```

#### Labels y placeholders

```
LABELS DE CAMPO
Regla: sustantivo o frase corta. No repite el tipo de campo. No termina en dos puntos.
Ejemplos:
- "Correo electrónico" (no "Ingresa tu correo electrónico:")
- "Nombre completo" (no "Nombre y apellido del titular:")
- "Contraseña" (no "Escribe tu contraseña aquí")

PLACEHOLDERS
Regla: formato de ejemplo o hint de qué ingresar. No repite el label.
Desaparecen al escribir — no son instrucciones críticas.
Ejemplos:
- Email → "nombre@empresa.com"
- Fecha → "DD/MM/AAAA"
- Búsqueda → "Buscar por nombre o ID"
- Nombre → "Ej: María García"
NO usar placeholders para instrucciones que el usuario necesita mientras escribe.
```

#### Mensajes de error

Para cada categoría definida en Skill 3:

```
ERROR DE VALIDACIÓN (el usuario ingresó algo incorrecto)
Regla: decir qué está mal y cómo corregirlo. Sin culpar. Sin signos de exclamación.
Sin "Error:" como prefijo visible.
Ejemplos:
- "El correo tiene que tener el formato nombre@dominio.com"
- "La contraseña necesita al menos 8 caracteres y un número"
- "Esta fecha no puede ser anterior a hoy"
NO: "Campo inválido", "Error en el formulario", "Dato incorrecto"

ERROR DE RED (sin conexión o timeout)
Regla: explicar qué pasó, no culpar al usuario ni al sistema en términos técnicos.
Ofrecer la acción de recovery.
Ejemplos:
- "No pudimos conectarnos. Revisa tu conexión y vuelve a intentarlo."
- "Tardó más de lo esperado. [Reintentar]"
- "Sin conexión. Los cambios se van a guardar cuando vuelvas a estar en línea."

ERROR DE SERVIDOR (algo falló del lado del sistema)
Regla: asumir responsabilidad sin entrar en detalles técnicos. No mostrar códigos
de error al usuario final (sí en herramientas técnicas o para soporte).
Ejemplos:
- "Algo salió mal de nuestra parte. Ya estamos trabajando en eso."
- "No pudimos procesar esto ahora. Inténtalo de nuevo en unos minutos."

ERROR DE PERMISOS (el usuario no tiene acceso)
Regla: explicar qué no puede hacer y por qué (si es posible decirlo). Ofrecer salida.
Ejemplos:
- "No tienes acceso a esta sección. Pídele al administrador que te invite."
- "Esta función está disponible solo en el plan Pro. [Ver planes]"
- "Tu sesión expiró. [Volver a ingresar]"
```

#### Empty states

Para cada tipo identificado en Skill 3:

```
VACÍO PORQUE ES NUEVO (el usuario nunca agregó contenido)
Regla: no mostrar vacío — mostrar posibilidad. Dar la acción para empezar.
Estructura: qué puede hacer aquí + botón de acción.
Ejemplos:
- "Todavía no tienes proyectos. [Crear el primero]"
- "Tu biblioteca está vacía. Empieza agregando tu primer recurso. [Agregar]"

VACÍO POR SIN RESULTADOS (búsqueda o filtro sin match)
Regla: confirmar qué se buscó, ofrecer alternativa.
Ejemplos:
- "No encontramos resultados para '[término]'. Prueba con otras palabras."
- "Ningún proyecto coincide con estos filtros. [Limpiar filtros]"

VACÍO PORQUE TODO ESTÁ HECHO (inbox cero, lista completada)
Regla: celebrar o confirmar. Este es el momento donde se permite más personalidad.
Ejemplos:
- "Todo al día. No tienes tareas pendientes."
- "Bandeja vacía. Disfrútalo mientras dura."
- "Sin notificaciones nuevas."
```

#### Confirmaciones de acciones destructivas

```
Regla: nombrar exactamente qué se va a perder o qué va a pasar. Sin ambigüedad.
El botón de confirmar repite la acción — no dice "Sí" ni "OK".
Estructura sugerida: título + consecuencia + botones

Ejemplo — Eliminar cuenta:
Título: "¿Eliminar tu cuenta?"
Cuerpo: "Se van a borrar todos tus datos, proyectos e historial. Esta acción no se puede deshacer."
Botón confirmar: "Eliminar cuenta"
Botón cancelar: "Volver"

Ejemplo — Descartar cambios:
Título: "¿Descartar los cambios?"
Cuerpo: "Los cambios que hiciste no se van a guardar."
Botón confirmar: "Descartar"
Botón cancelar: "Seguir editando"
```

#### Onboarding y tooltips

```
ONBOARDING (primera vez)
Regla: orientar sin abrumar. Una idea por pantalla o tooltip. Voz activa.
No decir "Bienvenido/a" como primer texto — ir directo al valor.
Ejemplos:
- "Desde aquí controlas todos tus proyectos." (no "¡Bienvenido al dashboard!")
- "Arrastrá las tarjetas para cambiar el estado." (instrucción directa)
- "Guardamos automáticamente. Nunca pierdes tu trabajo." (beneficio, no función)

TOOLTIPS
Regla: máximo 2 oraciones. Amplían lo que el label no puede decir.
No repiten el label. No empiezan con "Este botón...".
Ejemplos:
- Ícono de candado → "Solo tú puedes ver este proyecto."
- Ícono de información → "El precio no incluye impuestos locales."
```

#### Notificaciones y toasts

```
ÉXITO
Regla: confirmar qué pasó. Sin exclamaciones en exceso.
Ejemplos:
- "Cambios guardados."
- "Proyecto creado."
- "Invitación enviada a [email]."

ADVERTENCIA (algo para atender, no un error)
Regla: describir la situación y la acción posible.
Ejemplos:
- "Tu plan vence en 3 días. [Renovar]"
- "Algunos archivos no se pudieron subir. [Ver cuáles]"

INFORMACIÓN
Regla: dato útil, sin urgencia.
Ejemplos:
- "Nueva versión disponible. [Actualizar]"
- "Modo offline activado. Los cambios se sincronizarán al reconectarte."
```

---

### Paso 5 — Elegir el output

Después de generar todo, preguntar al diseñador:

> "Tengo la guía de voz y tono y los ejemplos de microcopy para todos los
> componentes. ¿Qué te llevas?"

Presentar las opciones:

**A — Solo la guía de voz y tono**
Las reglas, la personalidad, el glosario y los patrones. Para que el equipo
escriba sus propios textos siguiendo el sistema.

**B — Solo el microcopy listo para usar**
Los textos generados para cada componente, listos para copiar al diseño.
Sin la explicación de las reglas detrás.

**C — Guía completa + microcopy**
Todo junto. El documento más completo — ideal si se va a compartir con
un equipo o si el producto no tiene UX writer propio.

**D — Revisión primero**
"Quiero revisar los ejemplos y ajustar algunos antes de cerrar."
→ El diseñador indica qué cambiar y se itera sobre los ejemplos antes
de generar el documento final.

Generar el output elegido y nada más. No incluir secciones no pedidas.

---

### Paso 6 — Generar el documento final

Según la opción elegida en el Paso 5:

**Si eligió A — Guía:**
```
## VOZ Y TONO — [Nombre del producto]

### Idioma y variante
[contenido]

### Personalidad de la voz
[contenido]

### Lo que nunca hacemos
[contenido]

### Tono por contexto
[contenido]

### Reglas de escritura
[contenido]

### Glosario
[contenido]

### Textos reservados por compliance
[contenido]
```

**Si eligió B — Microcopy:**
```
## MICROCOPY — [Nombre del producto]

### Botones
[ejemplos por tipo]

### Labels y placeholders
[ejemplos]

### Mensajes de error
[ejemplos por categoría]

### Empty states
[ejemplos por tipo]

### Confirmaciones destructivas
[ejemplos]

### Onboarding y tooltips
[ejemplos]

### Notificaciones
[ejemplos por tipo]
```

**Si eligió C — Completo:**
Ambos documentos en uno, en ese orden: primero la guía, después el microcopy.

**Si eligió D:** iterar primero, luego preguntar de nuevo entre A, B y C.

---

## Reglas de comportamiento

- **Generar los ejemplos siempre, antes de preguntar qué se llevan.** El diseñador
  no puede elegir entre "guía" y "microcopy" si no vio los ejemplos. La elección
  informada requiere ver el output primero.
- **Usar el contexto del producto en los ejemplos.** Si el producto se llama "Flux"
  y tiene proyectos y colaboradores, los ejemplos dicen "Proyecto eliminado" no
  "Elemento eliminado". Los textos genéricos no sirven para validar tono.
- **Nunca culpar al usuario en los errores.** Ni en los mensajes de validación.
  El usuario no "ingresó mal" — "el formato tiene que ser X".
- **El humor tiene zona permitida y zona prohibida.** Permitido: empty states de
  inbox cero, onboarding de bajo riesgo, notificaciones de logro. Prohibido: errores,
  pérdida de datos, acciones irreversibles, cualquier momento de fricción alta.
- **Cuando el diseñador no sabe** qué tono quiere: generar dos versiones del mismo
  componente con tonos distintos y que elija. No asumir.
- **Adaptar el idioma de la skill** al idioma del diseñador. Si el diseñador habla
  en rioplatense, la skill responde en rioplatense.

---

## Conexión con el stack

| Dirección | Detalle |
|-----------|---------|
| Recibe de Skill 0 | Perfil de usuario, idioma, experiencia objetivo |
| Recibe de Skill 1 | Nivel de lectura, restricciones de lenguaje, labels accesibles |
| Recibe de Skill 2 | Terminología legal, textos fijos de compliance |
| Recibe de Skill 3 | Tipos de botón, categorías de error, tipos de empty state |
| Recibe de Skill 4 | Tono visual, elementos con texto fijo, escala tipográfica |
| Entrega a Skill 6 | Microcopy por componente y guía de voz |

Cuando se usa de forma independiente, los documentos de esta skill son entregables
autosuficientes: la guía puede usarse como brand voice manual, el microcopy puede
entrar directamente al diseño o al código.
