---
name: audit-ux-3-contenido-y-lenguaje
description: >
  Audita el lenguaje de un producto digital: etiquetas, mensajes, copy de botones, errores,
  claridad y consistencia del vocabulario. Funciona como Skill 3 del stack de auditoría o de
  forma independiente. Disparar ante frases como "audita el copy de esto", "revisa el lenguaje
  de esta app", "comprueba si esto se entiende". Al detectar que aplica, confirmar: "¿Empezamos
  auditando contenido y lenguaje? Voy a revisar si las palabras ayudan a entender, decidir y
  avanzar, o si generan fricción."
---

# Skill 3 — Contenido y Lenguaje

Audita si el lenguaje del producto ayuda a entender, decidir y avanzar, o si genera confusión,
ambigüedad, o fricción innecesaria.

---

## Objetivo de esta skill

Producir un documento de hallazgos de contenido y lenguaje que:
- Usado en stack: se combina con los de las otras 7 dimensiones en la Skill 9
- Usado sola: es un informe de contenido completo y autosuficiente

---

## Protocolo de ejecución

### Paso 1 — Leer contexto

Si existe un Documento de Contexto y Acceso de Skill 0, leerlo: plataforma, nivel de acceso,
alcance. Si esta skill se usa de forma independiente y no existe ese documento, preguntar de
forma abreviada: qué producto es, en qué plataforma vive, y qué acceso hay disponible para
recorrerlo.

### Paso 2 — Recorrer el producto

Antes de la pasada analítica, aplicar el modo de recorrido de `referencia-conducta-auditora.md`:
si la pasada de persona real de esta auditoría todavía no se hizo, hacerla primero y usar sus
notas como pistas.

Después, aplicar cada uno de los checkpoints de esta dimensión (ver más abajo) sobre el producto
real, dentro del alcance definido. Para checkpoints cuyo método de verificación cambia según la
plataforma, consultar `referencia-metodos-por-plataforma.md`.

### Paso 3 — Documentar cada checkpoint

Por cada uno: aplicar el método de verificación correspondiente, asignar severidad con la
rúbrica de `referencia-severidad.md` (escala 0-4 con su color derivado: 0-1 azul, 2 amarillo,
3 naranja, 4 rojo — aplicando la regla de reproducción para hallazgos intermitentes y el cruce
con el objetivo del flujo), y registrar evidencia concreta según el protocolo de
`referencia-evidencia.md` (capturar y guardar en el momento, no reconstruir al final). Si no se
puede verificar con el acceso disponible, activar el protocolo de brecha de acceso de Skill 0.

### Paso 4 — Generar el documento de hallazgos de esta dimensión

El documento tiene dos partes (ver "Documento de hallazgos" más abajo): la **tabla de
hallazgos** — una fila por hallazgo, con ID `contenido-NN` que coincide con la nomenclatura de
evidencia de `referencia-evidencia.md` — y el **checklist de cobertura** — una fila por
checkpoint con su estado final. Un checkpoint produce tantas filas de hallazgo como problemas
se identifiquen: **la cantidad de hallazgos no se limita nunca**.

---

## Checkpoints

1. **Lenguaje claro, sin jerga innecesaria** — ¿hay términos internos o técnicos expuestos sin
   explicación, cuando existe una alternativa simple?
2. **Universalidad** — ¿alguien sin conocimiento previo del producto entendería esta etiqueta
   igual?
3. **Vocabulario consistente** — ¿la misma acción se nombra siempre igual en todo el producto?
4. **Ir al grano** — ¿la información más importante está al principio del texto, o hay que leer
   todo para encontrarla?
5. **Enlaces y botones que describen su destino** — ¿el texto de un enlace o botón anticipa
   exactamente qué va a pasar al tocarlo?
6. **Mensajes de error en lenguaje humano** — ¿el mensaje explica qué pasó y qué hacer, sin
   jerga técnica ni códigos como protagonistas?
7. **Formato escaneable** — ¿el contenido está organizado con subtítulos o viñetas en vez de
   bloques largos de texto?
8. **Longitud coherente entre elementos similares** — ¿los elementos que cumplen la misma
   función (títulos, etiquetas de menú) tienen una extensión parecida entre sí?

---

## Documento de hallazgos

### Tabla de hallazgos

Una fila por hallazgo. El ID (`contenido-NN`) es el mismo que llevan sus archivos de evidencia.
Un mismo checkpoint produce tantas filas como hallazgos se identifiquen — **sin límite**: se
registra todo lo identificado, y lo cosmético se agrupa recién en el informe final, nunca se
omite acá.

| ID | Checkpoint | Hallazgo | Severidad (0-4 / color) | Evidencia | Verificado por |
|---|---|---|---|---|---|

### Checklist de cobertura

Una fila por checkpoint, para que la Skill 9 — y cualquier lector — vea de un vistazo qué se
cubrió y qué no. Estado: `sin hallazgos` / `con hallazgos: [IDs]` / `no verificable — brecha
de acceso`.

| Checkpoint | Pregunta clave | Estado |
|---|---|---|
| Lenguaje claro | ¿Hay jerga técnica o interna expuesta sin explicación? |  |
| Universalidad | ¿Alguien sin contexto previo del producto entendería esta etiqueta igual? |  |
| Vocabulario consistente | ¿La misma acción se llama siempre igual en todo el producto? |  |
| Ir al grano | ¿La información más importante está al principio del texto? |  |
| Enlaces y botones descriptivos | ¿El texto del enlace o botón anticipa exactamente qué va a pasar? |  |
| Mensajes de error humanos | ¿El mensaje de error usa lenguaje simple y sugiere una acción concreta? |  |
| Formato escaneable | ¿El contenido está dividido con subtítulos o viñetas en vez de bloques largos? |  |
| Longitud coherente | ¿Los elementos de un mismo grupo tienen una extensión similar entre sí? |  |

---

## Solapamientos conocidos

**Mensajes de error**: acá se evalúa la redacción (claridad, tono, acción sugerida) — qué pasa con el trabajo de la persona y cómo se recupera es de Estados del Sistema (6). **Vocabulario consistente**: acá cubre todo el copy del producto — la nomenclatura de las categorías de navegación es de Navegación y AI (5): si ambas corren, la 5 se enfoca en la estructura y esta en el lenguaje.

Regla común a todo el stack: **un hallazgo nunca se descarta por "pertenecer a otra dimensión"**. Si aparece durante este recorrido, se registra acá anotando la dimensión dueña en el propio hallazgo; si la otra dimensión también corre y lo encuentra, la Skill 9 fusiona los duplicados en un solo hallazgo. Cuando esta skill corre sola, todo se registra y analiza acá, completo.

---

## Reglas de comportamiento

- **No releer una referencia ya leída.** Cada skill del stack lleva su propia copia de las
  reglas para poder funcionar sola, pero el contenido es idéntico en todas. Si en esta misma
  conversación ya se leyó una referencia al correr otra skill del stack, no se vuelve a abrir:
  las reglas ya están en contexto.

- **No asumir cumplimiento sin evidencia.** Cada hallazgo y cada estado de cobertura se
  completa solo con lo que se observó directamente o lo que la persona confirmó.
- **Registrar todo, sin tope.** La cantidad de hallazgos nunca se limita — ni por checkpoint,
  ni por dimensión. Todo lo identificado con evidencia entra al documento.
- **No inventar hallazgos.** Si un checkpoint no se pudo verificar, se activa el protocolo de
  brecha de acceso — no se completa igual con una suposición.
- **Conducta durante el recorrido.** Preguntas en lote (nunca validación elemento-por-elemento),
  narrar en una línea qué se está mirando, y comunicar hallazgos al cierre de la dimensión —
  según `referencia-conducta-auditora.md`.
- **Adaptar el idioma** al que use la persona en la conversación.
- **El documento es editable.** Antes de darlo por cerrado, confirmar que no falta nada.

---

## Output esperado

Un documento de hallazgos de contenido y lenguaje, con la tabla de hallazgos y el checklist de cobertura completos, listo
para combinarse con las demás dimensiones en la Skill 9, o para entregarse solo.

---

## Conexión con el resto del stack

Recibe el Documento de Contexto y Acceso de Skill 0. Su documento de hallazgos es uno de los
insumos que lee la Skill 9 al armar el informe final.
