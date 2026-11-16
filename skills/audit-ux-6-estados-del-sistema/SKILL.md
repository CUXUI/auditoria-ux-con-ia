---
name: audit-ux-6-estados-del-sistema
description: >
  Audita los tres momentos en que una persona se encuentra con un producto digital: el primer
  encuentro (antes de interactuar, con o sin datos en pantalla), el funcionamiento (uso normal),
  y el error. Cubre feedback, timing de respuesta, y recuperación de errores. Funciona como
  Skill 6 del stack de auditoría o de forma independiente. Disparar ante frases como "audita
  los estados de este producto", "revisa qué pasa cuando carga o falla", "comprueba el manejo de
  errores de esto". Al detectar que aplica, confirmar: "¿Empezamos auditando estados del
  sistema? Voy a revisar el primer encuentro, el uso normal, y qué pasa cuando algo sale mal."
---

# Skill 6 — Estados del Sistema

Audita si el producto comunica con claridad qué está pasando y qué sigue, en los tres momentos
en que cualquier persona se encuentra con una interfaz: antes de interactuar, durante el uso
normal, y cuando algo sale mal.

---

## Objetivo de esta skill

Producir un documento de hallazgos de estados del sistema que:
- Usado en stack: se combina con los de las otras 7 dimensiones en la Skill 9
- Usado sola: es un informe de estados completo y autosuficiente

---

## Protocolo de ejecución

### Paso 1 — Leer contexto

Si existe un Documento de Contexto y Acceso de Skill 0, leerlo: plataforma, nivel de acceso,
alcance. Si esta skill se usa de forma independiente y no existe ese documento, preguntar de
forma abreviada: qué producto es, en qué plataforma vive, y qué acceso hay disponible para
recorrerlo.

### Paso 2 — Recorrer el producto por los tres momentos

Antes de la pasada analítica, aplicar el modo de recorrido de `referencia-conducta-auditora.md`:
si la pasada de persona real de esta auditoría todavía no se hizo, hacerla primero y usar sus
notas como pistas.

A diferencia de otras dimensiones del stack, esta se organiza en tres bloques secuenciales, no
en una lista plana: primer encuentro, funcionamiento, y error. **El primer encuentro genuino de
la auditoría ya ocurrió**: fue el inicio de la pasada de persona real, y no se puede recrear
con una sesión ya usada. Por eso el bloque de primer encuentro arranca de las notas y capturas
de esa pasada (ver `referencia-conducta-auditora.md`) y después se confirma con método — si es
posible volver a un estado desde cero (sesión nueva, sin datos previos), mejor. Los bloques de
funcionamiento y error sí se recorren normalmente, en ese orden. Para checkpoints cuyo método de verificación cambia según la
plataforma, consultar `referencia-metodos-por-plataforma.md`.

### Paso 3 — Documentar cada checkpoint

Por cada uno: aplicar el método de verificación correspondiente, asignar severidad con la
rúbrica de `referencia-severidad.md` (escala 0-4 con su color derivado: 0-1 azul, 2 amarillo,
3 naranja, 4 rojo — aplicando la regla de reproducción para hallazgos intermitentes y el cruce
con el objetivo del flujo), y registrar evidencia concreta según el protocolo de
`referencia-evidencia.md` (capturar y guardar en el momento — clave en esta dimensión, donde
los estados intermedios y de error desaparecen al seguir navegando). Si no se puede verificar
con el acceso disponible (por ejemplo, un estado que solo existe con datos reales de
producción), activar el protocolo de brecha de acceso de Skill 0.

### Paso 4 — Generar el documento de hallazgos de esta dimensión

El documento tiene dos partes (ver "Documento de hallazgos" más abajo): la **tabla de
hallazgos** — una fila por hallazgo, con ID `estados-NN` que coincide con la nomenclatura de
evidencia de `referencia-evidencia.md` — y el **checklist de cobertura** — una fila por
checkpoint con su estado final. Un checkpoint produce tantas filas de hallazgo como problemas
se identifiquen: **la cantidad de hallazgos no se limita nunca**.

---

## Checkpoints

### Primer encuentro

Antes de que la persona haya interactuado con nada, exista o no exista contenido ya cargado en
pantalla.

1. **Las primeras preguntas tienen respuesta** — sin que nadie las diga en voz alta, toda
   persona se pregunta qué es esto y si parece confiable. ¿La pantalla responde sin necesidad
   de explorar?
2. **Acción clara para empezar** — ¿hay una guía visual obvia de qué hacer primero?
3. **Expectativa de cómo se ve el producto en uso** — ¿hay evidencia de cómo se va a ver esto
   una vez usado o con datos cargados?
4. **Salida si la persona se traba** — ¿hay un camino de ayuda visible desde la primera
   pantalla?

### Funcionamiento

Durante el uso normal, con contenido y controles ya en pantalla.

5. **Previsibilidad de resultados** — ¿los títulos, íconos y etiquetas anticipan correctamente
   el resultado de una acción antes de tomarla?
6. **Revelación progresiva** — ¿la pantalla muestra solo lo necesario para el paso actual, con
   lo avanzado disponible a pedido?
7. **Restricciones que previenen errores** — ¿se impide saltar pasos cuando hacerlo genera un
   problema?
8. **Tiempo de respuesta del sistema** — ¿la respuesta a una acción es inmediata (menos de 1
   segundo), intermedia (1 a 10 segundos, con señal de progreso), o disruptiva (más de 10
   segundos sin ninguna señal)?
9. **Confirmación de acciones** — ¿toda acción que modifica datos muestra éxito o fallo con
   claridad, y esa confirmación queda visible el tiempo suficiente para leerla?

### Error

Cuando algo sale mal.

10. **Tipo de error identificado** — ¿corresponde a que el sistema no entendió la entrada, no
    completó la acción esperada, o no informó qué estaba pasando?
11. **Mensaje humano y accionable** — ¿el mensaje explica qué pasó y sugiere una acción
    concreta, en lenguaje simple, sin códigos como protagonistas?
12. **El trabajo se conserva** — ¿lo que la persona ya había hecho sigue disponible después del
    error?
13. **Corrección sin recomenzar todo** — ¿se puede corregir el problema cambiando solo lo que
    falló, sin tener que repetir todo el proceso?

---

## Documento de hallazgos

### Tabla de hallazgos

Una fila por hallazgo. El ID (`estados-NN`) es el mismo que llevan sus archivos de evidencia.
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
| **Primer encuentro** | | |
| Preguntas iniciales respondidas | ¿Qué es esto? ¿Parece confiable? |  |
| Acción clara para empezar | ¿Hay una guía visual de qué hacer primero? |  |
| Expectativa de avance | ¿Se entiende cómo se verá esto una vez usado o con datos? |  |
| Salida si se traba | ¿Hay un camino de ayuda visible desde el arranque? |  |
| **Funcionamiento** | | |
| Previsibilidad | ¿Los títulos, íconos y etiquetas anticipan correctamente el resultado? |  |
| Revelación progresiva | ¿La pantalla muestra solo lo necesario para el paso actual? |  |
| Restricciones preventivas | ¿Se impide saltar pasos cuando eso genera un problema? |  |
| Tiempo de respuesta | ¿La respuesta es inmediata (<1s), intermedia (1-10s) o disruptiva (+10s)? |  |
| Confirmación de acciones | ¿Toda acción que modifica datos muestra éxito o fallo con claridad? |  |
| **Error** | | |
| Tipo de error identificado | ¿Es entrada no entendida, acción no completada, o falta de información? |  |
| Mensaje humano | ¿El mensaje usa lenguaje simple y sugiere una acción concreta? |  |
| Trabajo conservado | ¿La persona pierde lo que ya había hecho al ocurrir el error? |  |
| Corrección mínima | ¿Puede corregir cambiando solo lo que falló, sin recomenzar todo? |  |

---

## Solapamientos conocidos

**Mensajes de error**: acá se evalúan la recuperación (el trabajo se conserva, corrección sin recomenzar) y el timing — la redacción del mensaje es de Contenido y Lenguaje (3). **Tiempo de respuesta**: acá en condiciones normales — el comportamiento con conexión lenta o inestable es de Técnico y Bugs (8). El bloque de primer encuentro consume las notas de la pasada de persona real (ver Paso 2).

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
- **No inventar hallazgos.** Si un checkpoint no se pudo verificar (por ejemplo, un estado que
  solo aparece con datos reales de producción a los que no hay acceso), se activa el protocolo
  de brecha de acceso — no se completa igual con una suposición.
- **Recorrer los tres bloques en orden.** El bloque de primer encuentro se sostiene en las
  notas de la pasada de persona real — esa primera impresión no se recrea con una sesión ya
  usada.
- **Conducta durante el recorrido.** Preguntas en lote (nunca validación elemento-por-elemento),
  narrar en una línea qué se está mirando, y comunicar hallazgos al cierre de la dimensión —
  según `referencia-conducta-auditora.md`.
- **Adaptar el idioma** al que use la persona en la conversación.
- **El documento es editable.** Antes de darlo por cerrado, confirmar que no falta nada.

---

## Output esperado

Un documento de hallazgos de estados del sistema, con la tabla de hallazgos y el checklist de
cobertura completos, divididos en los tres bloques, listo para combinarse con las demás dimensiones en la Skill 9, o para
entregarse solo.

---

## Conexión con el resto del stack

Recibe el Documento de Contexto y Acceso de Skill 0. Su documento de hallazgos es uno de los
insumos que lee la Skill 9 al armar el informe final.
