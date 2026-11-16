---
name: audit-ux-7-formularios-e-interaccion
description: >
  Audita formularios y los controles de interacción que los rodean: campos, validación,
  botones, pasos. Es donde más fricción real se pierde en cualquier producto digital. Funciona
  como Skill 7 del stack de auditoría o de forma independiente. Disparar ante frases como
  "audita este formulario", "revisa cómo se cargan datos en esto", "comprueba el checkout de
  esto". Al detectar que aplica, confirmar: "¿Empezamos auditando formularios e interacción?
  Voy a revisar campos, validación, y qué tan fácil es completar y corregir."
---

# Skill 7 — Formularios e Interacción

Audita los formularios de un producto y los controles que los rodean: qué tan fácil es
completarlos, corregir un error, y llegar al final sin abandonar en el camino.

---

## Objetivo de esta skill

Producir un documento de hallazgos de formularios e interacción que:
- Usado en stack: se combina con los de las otras 7 dimensiones en la Skill 9
- Usado sola: es un informe de formularios completo y autosuficiente

---

## Protocolo de ejecución

### Paso 1 — Leer contexto

Si existe un Documento de Contexto y Acceso de Skill 0, leerlo: plataforma, nivel de acceso,
alcance. Si esta skill se usa de forma independiente y no existe ese documento, preguntar de
forma abreviada: qué producto es, en qué plataforma vive, y qué acceso hay disponible para
recorrerlo.

### Paso 2 — Recorrer el producto

Antes de la pasada analítica, aplicar el modo de recorrido de `referencia-conducta-auditora.md`:
si la pasada de persona real de esta auditoría todavía no se hizo, hacerla primero — completar
el formulario como lo haría una persona real, de punta a punta — y usar sus notas como pistas.

Después, aplicar cada uno de los checkpoints de esta dimensión (ver más abajo) sobre cada
formulario dentro del alcance definido. Para checkpoints cuyo método de verificación cambia según la
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
hallazgos** — una fila por hallazgo, con ID `formularios-NN` que coincide con la nomenclatura de
evidencia de `referencia-evidencia.md` — y el **checklist de cobertura** — una fila por
checkpoint con su estado final. Un checkpoint produce tantas filas de hallazgo como problemas
se identifiquen: **la cantidad de hallazgos no se limita nunca**.

---

## Checkpoints

1. **Una sola columna en formularios de uso infrecuente** — en formularios de consumo (los que
   se llenan una vez o pocas veces), ¿sigue un único recorrido visual, sin secciones sin
   relación puestas una al lado de la otra? Agrupar en una línea campos que son una sola unidad
   lógica (fecha, ciudad/código postal) no cuenta como excepción a esto. En herramientas
   administrativas de uso experto y repetido, esta regla no aplica igual — ahí priorizar lo que
   reduzca el esfuerzo de quien lo usa todos los días, aunque implique más de una columna.
2. **Mínimo de campos necesarios** — ¿todos los campos son imprescindibles para completar esta
   tarea puntual?
3. **Etiquetas visibles, no solo placeholder** — ¿cada campo tiene una etiqueta persistente, no
   solo un texto de ejemplo que desaparece al escribir?
4. **Obligatorio y opcional marcados con claridad** — ¿queda claro qué campos se pueden
   saltear?
5. **El tipo de campo correcto para cada dato** — ¿se usan controles apropiados (radio buttons
   para opciones excluyentes, steppers para números acotados, teclado numérico en mobile para
   números)?
6. **Validación en el momento y el lugar correctos** — ¿el error se señala en línea, en el
   campo exacto, apenas ocurre, en vez de todo junto al final?
7. **Formularios largos divididos en pasos** — si es extenso, ¿hay un indicador de progreso que
   muestre en qué paso está la persona y cuánto falta?
8. **Un botón primario, fricción en lo destructivo** — ¿hay un único botón primario por
   pantalla, y las acciones destructivas piden confirmación adicional?

---

## Documento de hallazgos

### Tabla de hallazgos

Una fila por hallazgo. El ID (`formularios-NN`) es el mismo que llevan sus archivos de evidencia.
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
| Una sola columna (uso infrecuente) | Si es de uso infrecuente, ¿sigue un único recorrido visual sin secciones sin relación puestas una al lado de la otra? |  |
| Mínimo de campos | ¿Todos los campos son imprescindibles para esta tarea puntual? |  |
| Etiquetas visibles | ¿Cada campo tiene una etiqueta persistente, no solo un placeholder? |  |
| Obligatorio/opcional claro | ¿Queda claro qué campos se pueden saltear? |  |
| Tipo de campo correcto | ¿El control (radio, stepper, dropdown, teclado) corresponde al tipo de dato? |  |
| Validación en momento y lugar | ¿El error se señala en línea, en el campo exacto, apenas ocurre? |  |
| Pasos con progreso | ¿Un formulario largo muestra en qué paso está la persona y cuánto falta? |  |
| Botón primario y fricción destructiva | ¿Hay un solo botón primario por pantalla? ¿Las acciones destructivas piden confirmación? |  |

---

## Solapamientos conocidos

**Validación y errores en formularios**: acá el ángulo es el formulario (momento y lugar de la validación) — la redacción del mensaje es de Contenido y Lenguaje (3) y la conservación del trabajo tras el error es de Estados del Sistema (6). **Etiquetas de campos**: acá se evalúa que existan y persistan — la claridad de su lenguaje es de Contenido (3).

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
- **Distinguir contexto de uso antes de aplicar el checkpoint 1.** Un formulario de checkout no
  se evalúa con el mismo criterio de columnas que un panel administrativo de carga masiva de
  datos.
- **Conducta durante el recorrido.** Preguntas en lote (nunca validación campo-por-campo con la
  persona), narrar en una línea qué se está mirando, y comunicar hallazgos al cierre de la
  dimensión — según `referencia-conducta-auditora.md`.
- **Adaptar el idioma** al que use la persona en la conversación.
- **El documento es editable.** Antes de darlo por cerrado, confirmar que no falta nada.

---

## Output esperado

Un documento de hallazgos de formularios e interacción, con la tabla de hallazgos y el checklist de cobertura completos,
listo para combinarse con las demás dimensiones en la Skill 9, o para entregarse solo.

---

## Conexión con el resto del stack

Recibe el Documento de Contexto y Acceso de Skill 0. Su documento de hallazgos es uno de los
insumos que lee la Skill 9 al armar el informe final.
