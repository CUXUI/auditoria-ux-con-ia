---
name: audit-ux-0-contexto-y-acceso
description: >
  Establece qué producto se va a auditar, qué acceso real hay disponible para inspeccionarlo,
  y el alcance de la auditoría, antes de aplicar cualquier criterio de las 8 dimensiones del
  stack. Funciona como Skill 0 del stack de auditoría (alimenta las 8 skills de dimensión y la
  Skill 9 de síntesis) pero también opera de forma completamente independiente: produce un
  Documento de Contexto y Acceso útil por sí solo para planificar cualquier auditoría. Disparar
  ante frases como "quiero auditar este producto", "necesito revisar la UX de esta app", "vamos
  a hacer un audit de este sitio", o cualquier pedido de evaluar un producto digital existente.
  Al detectar que esta skill aplica, confirmar con el usuario: "¿Empezamos definiendo qué vamos
  a auditar y con qué acceso cuento? Así el resto de la auditoría no pierde tiempo adivinando."
---

# Skill 0 — Contexto y Acceso

Esta skill establece qué se audita, con qué acceso, y hasta dónde llega la auditoría. Ninguna
skill de dimensión debería empezar a inspeccionar un producto sin esto resuelto.

---

## Objetivo de esta skill

Producir un **Documento de Contexto y Acceso** que:
- Usado en stack: alimenta a las 8 skills de dimensión y a la Skill 9 de síntesis
- Usado sola: es una definición de alcance de auditoría completa y autosuficiente

---

## Protocolo de ejecución

### Paso 1 — Identificar el producto

Preguntar:
1. ¿Qué es el producto? Nombre y una descripción de una línea.
2. ¿En qué plataforma vive? Elegir una:
   - **Web** — pedir la URL o confirmar que ya se puede navegar.
   - **Mobile** — pedir nombre de la app y de qué sistema operativo (iOS/Android). Preguntar
     si hay un simulador o emulador abierto en la pantalla que se pueda controlar.
   - **Desktop** — pedir nombre de la app y sistema operativo.
3. ¿Quiénes usan el producto, y en qué contexto? Una línea alcanza: público general o perfil
   experto, uso ocasional o diario, algún rasgo relevante (edad, contexto laboral, urgencia).
   Varias dimensiones no se pueden calibrar sin esto — "universalidad" del lenguaje, la
   excepción de herramientas expertas en formularios, la coincidencia con el mundo real. Si la
   persona no lo sabe con precisión, registrar la mejor hipótesis disponible y etiquetarla como
   hipótesis.
4. ¿Es la primera vez que se audita este producto, o hay una auditoría previa a la que
   referenciar?
5. ¿Hay datos sobre el uso real del producto? Analytics, mapas de calor, grabaciones de
   sesiones, tickets de soporte, métricas de negocio. **Pedirlos siempre** — no solo cuando
   existe una auditoría previa: estos datos calibran la severidad (qué flujos importan más) y
   el foco de toda la auditoría.
6. ¿Hay casos de uso o tareas puntuales que preocupan especialmente? ("la gente abandona el
   registro", "nadie encuentra la facturación"). Si los hay, entran al alcance con nombre
   propio y las dimensiones los priorizan.

### Paso 2 — Evaluar el acceso real disponible

Según la plataforma identificada:

- **Web**: confirmar que se puede navegar directamente. Este es el caso de mayor autonomía.
- **Desktop**: antes de tocar cualquier ventana o aplicación, pedir permiso explícito para
  controlarla. No asumir permiso implícito por haber recibido el pedido de auditoría.
- **Mobile**: si hay un simulador o emulador visible y controlable en la pantalla, tratarlo
  como acceso autónomo (equivalente a una ventana de escritorio). Si no lo hay, avisar
  explícitamente: "No tengo forma de controlar un dispositivo mobile real. Voy a necesitar que
  navegues tú la app y me compartas capturas de pantalla o una grabación de cada pantalla o
  flujo que auditemos." Confirmar en qué formato se va a compartir esa evidencia.

**Contexto externo (solo web pública):** si el producto es un sitio público y hay acceso a la
red, buscar contexto que calibre la auditoría — tráfico estimado, tecnologías con las que está
construido, reseñas o quejas públicas de usuarios. Este material se documenta como **contexto
externo**, nunca como hallazgo: sirve para ponderar severidades y elegir foco, no entra a la
tabla de hallazgos.

Documentar el resultado como uno de estos tres niveles de acceso:
- **Autónomo total** — se puede navegar y operar el producto directamente.
- **Autónomo parcial** — se puede operar el producto, pero ciertas verificaciones (lectores de
  pantalla, hardware específico, condiciones de red reales) van a necesitar brecha de acceso.
- **Asistido** — no hay control directo del producto; toda la auditoría depende de evidencia
  que la persona comparte.

**Límites de operación (siempre que haya acceso autónomo):** el producto que se audita suele
estar en producción, con datos y personas reales del otro lado. Antes de operar nada, acordar:

1. ¿Es un entorno de prueba o producción? Si hay entorno de prueba o cuentas de test
   disponibles, usarlos.
2. ¿Qué acciones están permitidas? Recorrer y completar formularios sin enviar, enviar
   formularios de prueba, crear contenido, llegar hasta el paso previo al pago — la persona
   define hasta dónde.
3. ¿Dónde frenar siempre? Como piso, aplican las acciones prohibidas de
   `referencia-conducta-auditora.md` (pagos, publicaciones, envíos a terceros, borrado): ninguna
   se ejecuta sin confirmación explícita en el momento, aunque el acceso sea autónomo total.

Lo acordado queda escrito en el documento final. Un flujo cuyo tramo final quedó fuera de los
límites no se descarta: se audita hasta el último paso permitido y el resto se cubre por brecha
de acceso o con evidencia de la persona.

### Paso 3 — Definir el alcance

Preguntar:
1. ¿Cuánto tiempo hay disponible para esta auditoría?
2. Con ese tiempo, ¿se audita el producto completo, un flujo específico, o una sección
   puntual? Si el tiempo es acotado, recomendar explícitamente enfocarse en el flujo de mayor
   impacto en vez de cubrir todo de forma superficial.
3. ¿Cuáles de las 8 dimensiones del stack se van a correr? Nombrarlas todas y dejar que la
   persona elija todas, algunas, o pedir una recomendación según el tipo de producto:
   - Fundamentos de usabilidad
   - Accesibilidad
   - Contenido y lenguaje
   - Jerarquía y claridad visual
   - Navegación y arquitectura de información
   - Estados del sistema
   - Formularios e interacción
   - Técnico y bugs

### Paso 4 — Generar el Documento de Contexto y Acceso

```
## CONTEXTO Y ACCESO — [Nombre del producto]

### El producto
- Nombre: [nombre]
- Plataforma: [web / mobile / desktop]
- Detalle de plataforma: [URL, o app + SO, o app + SO de escritorio]
- Quiénes lo usan: [perfil y contexto de uso — marcar si es hipótesis]
- Auditoría previa: [sí/no, referencia si aplica]

### Acceso disponible
- Nivel: [autónomo total / autónomo parcial / asistido]
- Detalle: [qué se puede hacer directamente, qué va a necesitar brecha de acceso o evidencia
  compartida, en qué formato se va a compartir esa evidencia]
- Límites de operación: [entorno de prueba o producción; qué acciones están permitidas; dónde
  frenar siempre]

### Alcance
- Tiempo disponible: [duración]
- Cobertura: [producto completo / flujo específico / sección puntual — nombrar cuál]
- Dimensiones a correr: [lista de las elegidas]
- Casos de uso prioritarios: [tareas puntuales que preocupan, si las hay — o "ninguno declarado"]

### Datos y contexto
- Datos de uso disponibles: [analytics, mapas de calor, tickets, métricas — o "no hay"]
- Contexto externo: [tráfico, tecnologías, reseñas públicas si es web pública — o "no aplica"]

### Notas para las skills de dimensión
[cualquier limitación o condición especial que las 8 dimensiones deban tener en cuenta]
```

Antes de cerrar el documento, preguntar: "¿Hay algo que corregir o agregar antes de empezar a
auditar?"

---

## Protocolo de brecha de acceso

Esta skill define el protocolo que las 8 skills de dimensión invocan cada vez que un checkpoint
no se puede verificar con el acceso disponible:

1. **Marcar explícitamente** el checkpoint como "no verificable con acceso actual" — nunca
   omitirlo ni asumirlo cumplido.
2. **Dar una guía concreta y accionable** de cómo la persona puede verificarlo en poco tiempo,
   en pasos simples, sin asumir conocimiento técnico previo.
3. **Pedir el resultado.** Se puede seguir auditando el resto de los checkpoints mientras se
   espera la respuesta, o pausar — según lo que prefiera la persona.
4. **Incorporar el resultado al informe** con una etiqueta de origen: verificado por la IA, o
   verificado por la persona.

---

## Reglas de comportamiento

- **No releer una referencia ya leída.** Cada skill del stack lleva su propia copia de las
  reglas para poder funcionar sola, pero el contenido es idéntico en todas. Si en esta misma
  conversación ya se leyó una referencia al correr otra skill del stack, no se vuelve a abrir:
  las reglas ya están en contexto.

- **No asumir acceso.** Si no está confirmado que se puede controlar una aplicación (sobre
  todo desktop), pedirlo antes de actuar.
- **No inventar hallazgos.** Todo lo que entra al documento de contexto viene de lo que la
  persona confirmó o de lo que se pudo observar directamente.
- **El documento es editable.** Antes de pasar a las dimensiones, confirmar que está correcto.
- **Después de este documento viene la pasada de persona real, no el análisis.** Con el
  contexto cerrado, el siguiente paso es el recorrido de persona real y la confirmación del
  plan definidos en `referencia-conducta-auditora.md` — recién después arrancan las dimensiones.
- **Adaptar el idioma** al que use la persona en la conversación.

---

## Output esperado

Un **Documento de Contexto y Acceso** que las 8 skills de dimensión y la Skill 9 puedan leer
sin tener que volver a preguntar nada de esto.

---

## Conexión con el resto del stack

| Skill | Qué consume de este documento |
|---|---|
| Skills 1-8 (dimensiones) | Plataforma, nivel de acceso, alcance, si esa dimensión está en la lista a correr |
| Skill 9 (síntesis) | Nombre del producto, alcance, para armar el encabezado del informe final |

Cuando esta skill se usa de forma independiente, el Documento de Contexto y Acceso es
igualmente válido como entregable: sirve para planificar la auditoría con o sin ayuda de IA,
o para compartir con un equipo antes de empezar.
