---
name: audit-ux-8-tecnico-y-bugs
description: >
  Audita cómo se comporta un producto digital en distintos dispositivos, navegadores y
  condiciones no ideales (conexión lenta, sesión interrumpida, orientación de pantalla), con
  una mirada de impacto en la experiencia de la persona, no de QA técnico. Funciona como Skill
  8 del stack de auditoría o de forma independiente. Disparar ante frases como "audita si esto
  funciona bien en distintos dispositivos", "revisa bugs de esto", "comprueba casos límite". Al
  detectar que aplica, confirmar: "¿Empezamos auditando lo técnico? Ojo: no es QA — audito
  cómo una falla técnica afecta a la persona, no si el software está técnicamente correcto."
---

# Skill 8 — Técnico y Bugs

Audita si el producto se sostiene cuando las condiciones no son ideales: otro dispositivo, otro
navegador, conexión lenta, una sesión que se corta a mitad de camino.

**Esta dimensión no es una auditoría de QA técnico.** No se está certificando que el software
funcione — se está auditando cómo una falla técnica afecta la experiencia de la persona que usa
el producto. Un bug que un equipo de QA calificaría como "menor" puede ser grave en esta
auditoría si genera confusión, hace perder confianza, o empuja a alguien a abandonar. Por eso
cada hallazgo de esta dimensión no termina en "funciona / no funciona" — termina en qué le
pasaría a la persona cuando falla.

---

## Objetivo de esta skill

Producir un documento de hallazgos técnicos, mirados desde el impacto en la persona, que:
- Usado en stack: se combina con los de las otras 7 dimensiones en la Skill 9
- Usado sola: es un informe técnico-experiencial completo y autosuficiente

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

Después, aplicar cada uno de los checkpoints de esta dimensión (ver más abajo) sobre el producto real,
en tantas combinaciones de dispositivo/navegador/condición como el acceso disponible lo
permita — no hace falta cobertura exhaustiva, con dos o tres combinaciones reales alcanza para
encontrar la mayoría de los problemas típicos. Para el método de verificación por plataforma,
consultar `referencia-metodos-por-plataforma.md`.

### Paso 3 — Documentar cada checkpoint

Por cada uno: verificar el comportamiento, describir qué le pasaría a una persona no técnica en
ese momento (confusión, pérdida de confianza, abandono, respuesta perdida), asignar severidad
con la rúbrica de `referencia-severidad.md` (escala 0-4 con su color derivado: 0-1 azul, 2
amarillo, 3 naranja, 4 rojo — en esta dimensión la regla de reproducción es central: los
problemas técnicos intermitentes se intentan reproducir al menos 3 veces antes de puntuarse),
y registrar evidencia concreta según el protocolo de `referencia-evidencia.md` (incluyendo
registro de consola o red cuando hay acceso, y evidencia de cada intento de reproducción). Si
no se puede verificar con el acceso disponible (por ejemplo, sin acceso a un segundo
dispositivo o navegador), activar el protocolo de brecha de acceso de Skill 0.

### Paso 4 — Generar el documento de hallazgos de esta dimensión

El documento tiene dos partes (ver "Documento de hallazgos" más abajo): la **tabla de
hallazgos** — una fila por hallazgo, con ID `tecnico-NN` que coincide con la nomenclatura de
evidencia de `referencia-evidencia.md` — y el **checklist de cobertura** — una fila por
checkpoint con su estado final. Un checkpoint produce tantas filas de hallazgo como problemas
se identifiquen: **la cantidad de hallazgos no se limita nunca**.

---

## Checkpoints

1. **Comportamiento en distintos navegadores/dispositivos** — si el producto se probó en más de
   una combinación, ¿se comporta igual? Si no, ¿qué le pasaría a la persona que use la
   combinación donde falla?
2. **Recuperación al refrescar o perder la sesión a mitad de una tarea** — ¿se conserva el
   progreso, o al menos se avisa con claridad que se perdió, en vez de dejar a la persona sin
   saber si tiene que empezar de nuevo?
3. **Comportamiento con el botón de retroceso o navegación nativa** — ¿se mantiene el estado del
   producto sin duplicar acciones ni generar la sensación de que "se rompió todo"?
4. **Comportamiento con dos instancias abiertas a la vez** (dos pestañas, o la app abierta en
   dos dispositivos) — ¿genera resultados cruzados o inconsistentes que la persona no pueda
   explicarse?
5. **Comportamiento con conexión lenta o inestable** — ¿el producto sigue siendo usable, con
   señales de carga claras que eviten que la persona piense que se colgó y abandone?
6. **Comportamiento al rotar o cambiar el tamaño de pantalla** (mobile/responsive) — ¿el
   contenido se reacomoda sin perder información que la persona necesita?
7. **Comportamiento tras inactividad prolongada** — si hay un límite de tiempo de sesión, ¿se
   avisa con anticipación, o la persona pierde su progreso en silencio?

---

## Documento de hallazgos

### Tabla de hallazgos

Una fila por hallazgo. El ID (`tecnico-NN`) es el mismo que llevan sus archivos de evidencia.
Un mismo checkpoint produce tantas filas como hallazgos se identifiquen — **sin límite**: se
registra todo lo identificado, y lo cosmético se agrupa recién en el informe final, nunca se
omite acá.

| ID | Checkpoint | Hallazgo | Qué le pasaría a la persona | Severidad (0-4 / color) | Evidencia | Verificado por |
|---|---|---|---|---|---|---|

### Checklist de cobertura

Una fila por checkpoint, para que la Skill 9 — y cualquier lector — vea de un vistazo qué se
cubrió y qué no. Estado: `sin hallazgos` / `con hallazgos: [IDs]` / `no verificable — brecha
de acceso`.

| Checkpoint | Estado |
|---|---|
| Distintos navegadores/dispositivos |  |
| Refrescar o perder sesión a mitad de tarea |  |
| Botón de retroceso / navegación nativa |  |
| Dos instancias abiertas a la vez |  |
| Conexión lenta o inestable |  |
| Rotar o cambiar tamaño de pantalla |  |
| Inactividad prolongada |  |

---

## Solapamientos conocidos

**Conexión lenta o inestable**: acá se evalúa como condición degradada — el timing de respuesta en condiciones normales es de Estados del Sistema (6). **Pérdida de trabajo** al refrescar o perder la sesión roza Estados (6, "el trabajo se conserva"): acá el disparador es técnico (refresh, sesión, doble instancia) — en la 6, el error del propio sistema.

Regla común a todo el stack: **un hallazgo nunca se descarta por "pertenecer a otra dimensión"**. Si aparece durante este recorrido, se registra acá anotando la dimensión dueña en el propio hallazgo; si la otra dimensión también corre y lo encuentra, la Skill 9 fusiona los duplicados en un solo hallazgo. Cuando esta skill corre sola, todo se registra y analiza acá, completo.

---

## Reglas de comportamiento

- **No releer una referencia ya leída.** Cada skill del stack lleva su propia copia de las
  reglas para poder funcionar sola, pero el contenido es idéntico en todas. Si en esta misma
  conversación ya se leyó una referencia al correr otra skill del stack, no se vuelve a abrir:
  las reglas ya están en contexto.

- **No es QA.** Ningún hallazgo de esta dimensión se cierra con "funciona / no funciona" sin
  describir el impacto en la persona.
- **No asumir cumplimiento sin evidencia.** Cada hallazgo y cada estado de cobertura se
  completa solo con lo que se observó directamente o lo que la persona confirmó.
- **Registrar todo, sin tope.** La cantidad de hallazgos nunca se limita — ni por checkpoint,
  ni por dimensión. Todo lo identificado con evidencia entra al documento.
- **No inventar hallazgos.** Si un checkpoint no se pudo verificar por falta de acceso a otro
  dispositivo o navegador, se activa el protocolo de brecha de acceso — no se completa igual
  con una suposición.
- **Conducta durante el recorrido.** Preguntas en lote (nunca validación elemento-por-elemento),
  narrar en una línea qué se está mirando, y comunicar hallazgos al cierre de la dimensión —
  según `referencia-conducta-auditora.md`.
- **Adaptar el idioma** al que use la persona en la conversación.
- **El documento es editable.** Antes de darlo por cerrado, confirmar que no falta nada.

---

## Output esperado

Un documento de hallazgos técnicos con lente de experiencia de usuario, con la tabla de hallazgos y el
checklist de cobertura completos, listo para combinarse con las demás dimensiones en la Skill 9, o para
entregarse solo.

---

## Conexión con el resto del stack

Recibe el Documento de Contexto y Acceso de Skill 0. Su documento de hallazgos es uno de los
insumos que lee la Skill 9 al armar el informe final.
