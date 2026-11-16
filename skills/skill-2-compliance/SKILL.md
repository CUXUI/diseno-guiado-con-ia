---
name: skill-2-compliance
description: >
  Define los requerimientos legales y regulatorios que impactan el diseño del producto.
  Cubre privacidad de datos (GDPR, LGPD, CCPA), normativa sectorial (HIPAA para salud,
  PSD2 para fintech, COPPA para menores, FERPA para educación) y obligaciones de
  transparencia e información al usuario. Opera en stack recibiendo el Documento de
  Contexto Base de Skill 0, o de forma completamente independiente con una entrevista
  de contexto reducida. Se activa cuando el Contexto Base indica: usuarios en la UE o
  Brasil, modelo B2C o B2B con datos de usuarios, sector salud / fintech / educación /
  menores. Si no hay ninguno de estos indicadores, la skill se omite. Al detectar que
  aplica, confirmar: "Este producto tiene características que activan requerimientos
  legales de diseño. ¿Arrancamos con la definición de compliance? Esto va a impactar
  en cómo se diseñan los flujos de consentimiento, los formularios y la arquitectura
  de información."
---

# Skill 2 — Compliance

Esta skill define los requerimientos legales y regulatorios que el diseño del producto
debe respetar, y produce un **Documento de Compliance** con restricciones concretas
para las skills de Interacción, Visual y Writing.

No es una auditoría legal. Es una traducción de obligaciones legales en decisiones
de diseño concretas.

---

## Protocolo de ejecución

### Paso 1 — Detectar si aplica y en qué áreas

**Si hay Contexto Base (Skill 0):** leer los siguientes campos y evaluar:

| Campo de Skill 0 | Indicador de compliance |
|------------------|------------------------|
| Usuarios en UE o con residencia en UE | GDPR activo |
| Usuarios en Brasil | LGPD activo |
| Usuarios en California / EEUU | CCPA activo (si B2C) |
| Usuarios menores de 13 años (o producto dirigido a menores) | COPPA activo (EEUU) / regulación local equivalente |
| Sector salud | HIPAA activo (EEUU) / normativa local equivalente |
| Sector fintech / servicios financieros | PSD2 activo (UE) / normativa local equivalente |
| Sector educación con datos de menores | FERPA activo (EEUU) / normativa local equivalente |
| Recolección de datos personales (cualquier jurisdicción) | Política de privacidad + consentimiento requeridos |
| Modelo B2C con cookies o tracking | Banner de cookies requerido en UE/UK |

Si ningún indicador aplica: comunicar al diseñador que esta skill no es necesaria para
este producto y continuar con Skill 3. No forzar la ejecución.

**Si no hay Contexto Base:** preguntar antes de continuar:

1. ¿En qué países o regiones van a estar los usuarios del producto?
2. ¿El producto recolecta algún tipo de dato personal? (nombre, email, ubicación,
   comportamiento, salud, finanzas, datos de menores)
3. ¿El producto pertenece a alguno de estos sectores: salud, finanzas, educación?

---

### Paso 2 — Identificar las regulaciones activas

Según los indicadores detectados, declarar explícitamente qué regulaciones aplican
y cuáles no. No asumir — si hay duda sobre la jurisdicción, preguntar.

Ejemplo de declaración:
> "Para este producto aplican: GDPR (usuarios UE), COPPA (usuarios menores de 13).
> No aplica: HIPAA (no es salud), PSD2 (no es fintech)."

---

### Paso 3 — Entrevista por área regulatoria

Recorrer solo las áreas activas. No presentar áreas que no aplican.
Un área por turno. Esperar respuesta antes de continuar.

---

#### Área A — Privacidad y datos personales
*(activa si hay recolección de datos personales en cualquier jurisdicción)*

Preguntar:
- ¿Qué datos personales recolecta el producto? (email, nombre, ubicación, comportamiento,
  datos sensibles como salud o finanzas)
- ¿Los datos se comparten con terceros? (analytics, publicidad, integraciones)
- ¿El usuario puede ver, editar o eliminar sus datos desde el producto?

Definir según respuestas:
- Qué flujos de consentimiento necesita el producto (opt-in explícito vs implícito)
- Si se necesita una página o modal de política de privacidad accesible desde cualquier
  punto del producto
- Si se necesita un flujo de "eliminar mi cuenta y datos"
- Qué datos pueden recolectarse con consentimiento implícito vs cuáles requieren
  consentimiento explícito

---

#### Área B — GDPR
*(activa si hay usuarios en la Unión Europea o Reino Unido)*

Preguntar:
- ¿El producto usa cookies de tracking, analytics o publicidad?
- ¿Hay formularios que recolectan datos personales?
- ¿El producto envía comunicaciones de marketing (emails, notificaciones)?

Definir según respuestas:
- Requerimientos del banner de cookies: debe aparecer antes de cargar cookies
  no esenciales, no puede tener opciones pre-marcadas, "Rechazar" tiene que ser
  tan visible como "Aceptar"
- Consentimiento para marketing: opt-in explícito, nunca pre-marcado
- Formularios: solo pedir datos necesarios (principio de minimización)
- Derecho al olvido: flujo para solicitar eliminación de datos
- Acceso a datos: flujo para que el usuario descargue o vea sus datos

---

#### Área C — LGPD
*(activa si hay usuarios en Brasil)*

Similar a GDPR en estructura. Diferencias clave a declarar:
- El consentimiento tiene que ser específico por finalidad (no un consentimiento general)
- El titular tiene derecho a portabilidad de datos
- El DPO (Encarecargado de Datos) debe estar identificado en la política de privacidad
- Las bases legales para tratamiento de datos son las mismas que GDPR pero con
  terminología diferente — verificar que los textos legales usen la terminología correcta

---

#### Área D — CCPA
*(activa si hay usuarios en California, EEUU, y modelo B2C)*

Preguntar:
- ¿El producto vende datos de usuarios a terceros?
- ¿El producto tiene más de 100.000 usuarios en California o ingresos superiores a
  25 millones USD? (si no, CCPA puede no aplicar — verificar con el cliente)

Definir según respuestas:
- Si aplica: link "Do Not Sell My Personal Information" visible en footer
- Formulario para solicitar qué datos se tienen del usuario
- Política de no discriminación: no penalizar al usuario por ejercer sus derechos

---

#### Área E — COPPA
*(activa si hay usuarios menores de 13 años o si el producto puede atraer menores)*

Preguntar:
- ¿El producto está dirigido explícitamente a menores de 13 años?
- ¿El producto puede atraer menores aunque no esté dirigido a ellos?
- ¿Se recolectan datos de menores?

Definir según respuestas:
- Si hay recolección de datos de menores: consentimiento verificable de los padres
  antes de cualquier recolección
- Mecanismo de verificación de edad en el flujo de registro
- Si el producto puede atraer menores sin estar dirigido a ellos: considerar flujo
  de verificación de edad o diseño que minimice la recolección por defecto

---

#### Área F — Salud / HIPAA y equivalentes
*(activa si el producto maneja datos de salud)*

Preguntar:
- ¿El producto almacena o transmite datos de salud de usuarios identificables?
- ¿El producto está en EEUU o tiene usuarios en EEUU?
- ¿Hay integración con sistemas de salud o seguros?

Definir según respuestas:
- Si aplica HIPAA: los datos de salud (PHI) no pueden mostrarse en notificaciones
  push sin control del usuario, los formularios de salud necesitan cifrado visible,
  los logs de acceso a datos de salud son obligatorios
- Principio general (cualquier jurisdicción): datos de salud son categoría especial —
  requieren consentimiento explícito separado del consentimiento general de privacidad

---

#### Área G — Fintech / PSD2 y equivalentes
*(activa si el producto maneja dinero, pagos o datos financieros)*

Preguntar:
- ¿El producto procesa pagos o muestra información financiera del usuario?
- ¿Opera en la Unión Europea?
- ¿Tiene acceso a cuentas bancarias de terceros?

Definir según respuestas:
- PSD2 (UE): autenticación fuerte (SCA) requerida para pagos — diseñar el flujo de
  pago con paso de verificación de dos factores obligatorio
- Transparencia de fees: los costos deben mostrarse antes de confirmar cualquier
  transacción, no después
- Confirmación explícita antes de cualquier movimiento de dinero (no basta con un
  solo tap)
- Mensajes de error en transacciones: deben ser claros sobre qué falló sin exponer
  datos financieros sensibles

---

#### Área H — Educación / FERPA y equivalentes
*(activa si el producto maneja datos de estudiantes)*

Preguntar:
- ¿El producto es usado en instituciones educativas?
- ¿Maneja datos de rendimiento académico o asistencia de estudiantes?
- ¿Hay usuarios menores de 18 años en contexto educativo?

Definir según respuestas:
- FERPA (EEUU): los registros educativos no pueden compartirse sin consentimiento
  del estudiante (o padre/tutor si es menor)
- Los datos de rendimiento no pueden mostrarse públicamente ni a otros estudiantes
- El diseño de dashboards de progreso debe restringir la visibilidad por rol

---

### Paso 4 — Generar el Documento de Compliance

```
## COMPLIANCE — [Nombre del producto]

### Regulaciones activas
- [lista de regulaciones que aplican a este producto]
- [lista de regulaciones evaluadas y descartadas, con motivo]

### Área A — Privacidad y datos personales
- Datos recolectados: [lista]
- Compartidos con terceros: [sí/no + con quiénes]
- Consentimiento requerido: [implícito / explícito / explícito por categoría]
- Flujos obligatorios: [política de privacidad accesible / eliminar cuenta / ver mis datos]

### Área B — GDPR (si aplica)
- Banner de cookies: [requerido / no requerido] + requerimientos de diseño
- Consentimiento de marketing: [opt-in explícito requerido]
- Formularios: [campos mínimos necesarios declarados]
- Flujos obligatorios: [derecho al olvido / portabilidad de datos]

### Área C — LGPD (si aplica)
- Consentimiento por finalidad: [requerido]
- DPO identificado en política: [requerido]
- Diferencias terminológicas a aplicar en Writing: [lista]

### Área D — CCPA (si aplica)
- "Do Not Sell" link: [requerido / no requerido]
- Formulario de solicitud de datos: [requerido / no requerido]

### Área E — COPPA (si aplica)
- Verificación de edad: [requerida / no requerida] + en qué punto del flujo
- Consentimiento parental: [requerido / no requerido]
- Minimización de datos por defecto: [sí/no]

### Área F — Salud (si aplica)
- Datos de salud recolectados: [sí/no + cuáles]
- Consentimiento específico de salud: [requerido]
- Restricciones de notificaciones con datos de salud: [lista]

### Área G — Fintech (si aplica)
- Autenticación fuerte (SCA): [requerida / no requerida]
- Transparencia de fees antes de confirmar: [requerida]
- Confirmación explícita en movimientos de dinero: [requerida]

### Área H — Educación (si aplica)
- Restricciones de visibilidad por rol: [lista]
- Datos que no pueden compartirse: [lista]

### Restricciones para las demás skills

**→ Skill 3 — Interacción:**
- [flujos obligatorios que hay que diseñar: consentimiento, verificación de edad,
  confirmación de transacciones, eliminación de cuenta, etc.]

**→ Skill 4 — Visual:**
- [elementos de UI obligatorios: dónde va el banner de cookies, dónde el link de
  privacidad, cómo se diseña el opt-in para que sea legalmente válido, etc.]

**→ Skill 5 — Writing:**
- [textos con requerimientos legales: política de privacidad, textos de consentimiento,
  mensajes de error en transacciones, terminología específica por jurisdicción]
```

---

## Reglas de comportamiento

- **No activar si no aplica.** Si el producto no tiene ningún indicador de compliance,
  comunicarlo y pasar a Skill 3. No generar trabajo innecesario.
- **No es asesoría legal.** Esta skill traduce obligaciones conocidas en decisiones de
  diseño. Para productos en producción real, siempre recomendar revisión con un abogado
  especializado. Decirlo explícitamente al cerrar el documento.
- **Cuando el diseñador no sabe:** aplicar el requerimiento más conservador y documentarlo
  como supuesto revisable. En compliance, el "no sé" tiene consecuencias legales reales.
- **Explicar el impacto en diseño**, no solo la obligación legal. "GDPR requiere que el
  botón de rechazar cookies sea igual de visible que el de aceptar" es más útil que
  "GDPR requiere consentimiento libre".
- **Adaptar el idioma.** Mismo idioma y registro que usa el diseñador.

---

## Conexión con el stack

| Dirección | Detalle |
|-----------|---------|
| Recibe de Skill 0 | Modelo de negocio, tipo de producto, perfil de usuario (edad, jurisdicción), sector |
| Recibe de Skill 1 | Perfil de usuario con necesidades especiales (relevante para COPPA) |
| Entrega a Skill 3 | Flujos de diseño obligatorios (consentimiento, verificación, confirmación) |
| Entrega a Skill 4 | Elementos de UI obligatorios y su posicionamiento |
| Entrega a Skill 5 | Textos con requerimientos legales y terminología por jurisdicción |
| Entrega a Skill 6 | Flujos de compliance y elementos de UI obligatorios integrados en el prototipo |

Cuando se usa de forma independiente, el Documento de Compliance es un entregable
autosuficiente: puede usarse como checklist legal de diseño, brief para el equipo
legal, o base para una auditoría de compliance de UX.
