---
name: audit-ux-1-fundamentos-de-usabilidad
description: >
  Audita un producto digital contra los principios fundamentales de usabilidad: visibilidad
  del estado del sistema, coincidencia con el mundo real, control del usuario, consistencia,
  prevención de errores, reconocer antes que recordar, flexibilidad, diseño minimalista, y
  ayuda para recuperarse de errores. Funciona como Skill 1 del stack de auditoría o de forma
  independiente. Disparar ante frases como "audita la usabilidad de esto", "revisa si esto es
  fácil de usar", "haz un heurístico de este producto". Al detectar que aplica, confirmar:
  "¿Empezamos auditando fundamentos de usabilidad? Voy a recorrer el producto buscando
  fricciones en cómo se usa, no en cómo se ve."
---

# Skill 1 — Fundamentos de Usabilidad

Audita si el producto es fácil de operar: si comunica lo que está pasando, si se comporta como
la persona espera, y si perdona los errores en vez de castigarlos.

---

## Objetivo de esta skill

Producir un documento de hallazgos de usabilidad que:
- Usado en stack: se combina con los de las otras 7 dimensiones en la Skill 9
- Usado sola: es un informe de usabilidad completo y autosuficiente

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
hallazgos** — una fila por hallazgo, con ID `usabilidad-NN` que coincide con la nomenclatura de
evidencia de `referencia-evidencia.md` — y el **checklist de cobertura** — una fila por
checkpoint con su estado final. Un checkpoint produce tantas filas de hallazgo como problemas
se identifiquen: **la cantidad de hallazgos no se limita nunca**.

---

## Checkpoints

1. **Visibilidad del estado del sistema** — ¿toda acción tiene una confirmación visible en
   menos de un segundo? ¿los procesos largos muestran progreso real, no solo una animación sin
   información?
2. **Coincidencia con el mundo real** — ¿el lenguaje, los íconos y el orden de la información
   son los que usaría la persona que lo usa, no los del sistema por dentro?
3. **Control y libertad** — ¿existe una salida clara de cualquier acción por error (deshacer,
   cancelar, volver atrás) sin tener que pasar por un proceso largo?
4. **Consistencia y estándares** — ¿un mismo concepto se nombra siempre igual en todo el
   producto? ¿se respetan las convenciones de la plataforma en vez de reinventarlas?
5. **Prevención de errores** — ¿hay confirmaciones antes de acciones destructivas? ¿el sistema
   restringe entradas inválidas antes de que se envíen?
6. **Reconocer antes que recordar** — ¿la información necesaria para el siguiente paso está
   visible, o la persona tiene que recordarla de una pantalla anterior?
7. **Flexibilidad y eficiencia de uso** — ¿el mismo camino sirve tanto para alguien que lo usa
   por primera vez como para alguien que lo usa todos los días?
8. **Diseño minimalista** — ¿hay elementos en pantalla que no aportan a la tarea actual y
   podrían sacarse sin perder claridad?
9. **Ayudar a reconocer y recuperarse de errores** — ¿el mensaje de error explica en lenguaje
   simple qué pasó y qué hacer, sin mostrar códigos como protagonistas?
10. **Ayuda y documentación** — si hace falta ayuda, ¿está disponible en el contexto donde se
    necesita, con pasos concretos en vez de explicaciones abstractas?

---

## Documento de hallazgos

### Tabla de hallazgos

Una fila por hallazgo. El ID (`usabilidad-NN`) es el mismo que llevan sus archivos de evidencia.
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
| Visibilidad del estado del sistema | ¿Toda acción tiene confirmación en menos de 1 seg? ¿Los procesos largos muestran progreso real? |  |
| Coincidencia con el mundo real | ¿El lenguaje y los íconos son los que usaría la persona, no los del sistema? |  |
| Control y libertad | ¿Hay una salida clara ante una acción por error? |  |
| Consistencia y estándares | ¿Un mismo concepto se nombra siempre igual en todo el producto? |  |
| Prevención de errores | ¿Hay confirmación antes de una acción destructiva? |  |
| Reconocer antes que recordar | ¿La información necesaria está visible, o hay que recordarla? |  |
| Flexibilidad y eficiencia | ¿Sirve igual para alguien nuevo que para alguien experto? |  |
| Diseño minimalista | ¿Hay elementos que no aportan a la tarea actual? |  |
| Reconocer y recuperarse de errores | ¿El mensaje de error explica qué pasó y cómo resolverlo en lenguaje simple? |  |
| Ayuda y documentación | Si hace falta ayuda, ¿está en el contexto donde se necesita? |  |

---

## Solapamientos conocidos

Esta es la dimensión más general del stack y roza varias otras. En stack completo, el ángulo propio de cada una: la **redacción** de los mensajes de error es de Contenido y Lenguaje (3) y su **recuperación** es de Estados del Sistema (6) — acá se evalúa el principio general (que el error se reconozca y se pueda superar); la consistencia de **nomenclatura** es de Contenido (3) y de Navegación (5) — acá se evalúa la consistencia de **comportamiento**; la prevención de errores **en formularios** es de Formularios e Interacción (7).

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

Un documento de hallazgos de usabilidad, con la tabla de hallazgos y el checklist de cobertura completos, listo para
combinarse con las demás dimensiones en la Skill 9, o para entregarse solo.

---

## Conexión con el resto del stack

Recibe el Documento de Contexto y Acceso de Skill 0. Su documento de hallazgos es uno de los
insumos que lee la Skill 9 al armar el informe final.
