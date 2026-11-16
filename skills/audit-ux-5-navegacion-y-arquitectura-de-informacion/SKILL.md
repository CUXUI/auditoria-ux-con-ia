---
name: audit-ux-5-navegacion-y-arquitectura-de-informacion
description: >
  Audita cómo está organizada la información de un producto digital y cómo se llega de un
  lugar a otro: nomenclatura, profundidad, búsqueda, y si la estructura coincide con cómo
  piensa la persona que la usa. Funciona como Skill 5 del stack de auditoría o de forma
  independiente. Disparar ante frases como "audita la navegación de esto", "revisa cómo está
  organizada la información", "comprueba si esto es fácil de encontrar". Al detectar que aplica,
  confirmar: "¿Empezamos auditando navegación y arquitectura de información? Voy a revisar si
  la estructura ayuda a encontrar las cosas, o si obliga a adivinar."
---

# Skill 5 — Navegación y Arquitectura de Información

Audita la estructura completa del producto: cómo está organizada la información, cómo se llega
de un lugar a otro, y si esa organización coincide con cómo piensa la persona que la usa — no
con cómo está organizada la base de datos por dentro.

---

## Objetivo de esta skill

Producir un documento de hallazgos de navegación que:
- Usado en stack: se combina con los de las otras 7 dimensiones en la Skill 9
- Usado sola: es un informe de arquitectura de información completo y autosuficiente

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
hallazgos** — una fila por hallazgo, con ID `navegacion-NN` que coincide con la nomenclatura de
evidencia de `referencia-evidencia.md` — y el **checklist de cobertura** — una fila por
checkpoint con su estado final. Un checkpoint produce tantas filas de hallazgo como problemas
se identifiquen: **la cantidad de hallazgos no se limita nunca**.

---

## Checkpoints

1. **Nomenclatura basada en el lenguaje de quien usa el producto** — ¿las categorías se llaman
   como las nombraría la persona, no como las nombró el equipo que las construyó?
2. **Profundidad razonable** — ¿cuántos niveles hay que atravesar para llegar a las tareas más
   frecuentes, y es proporcional a qué tan seguido se usan?
3. **Coincidencia con el flujo de trabajo real** — ¿el orden de la navegación coincide con el
   orden en que la persona realmente hace las cosas?
4. **Sentido de ubicación** — ¿la persona puede saber en todo momento dónde está, dónde estuvo,
   y a dónde puede ir?
5. **La búsqueda como red de contención** — si el producto tiene búsqueda, ¿entrega resultados
   relevantes con errores de tipeo o sinónimos razonables?
6. **Múltiples caminos cuando corresponde** — ¿hay más de una forma de llegar a contenido
   importante, para personas que piensan de formas distintas?
7. **Consistencia de la navegación** — ¿la estructura de navegación se comporta igual en todas
   las secciones del producto?

---

## Documento de hallazgos

### Tabla de hallazgos

Una fila por hallazgo. El ID (`navegacion-NN`) es el mismo que llevan sus archivos de evidencia.
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
| Nomenclatura | ¿Los nombres de categorías usan el lenguaje de quien usa el producto? |  |
| Profundidad razonable | ¿Cuántos niveles hay que atravesar para llegar a las tareas más frecuentes? |  |
| Coincidencia con el flujo real | ¿El orden de la navegación coincide con el orden real en que se hacen las cosas? |  |
| Sentido de ubicación | ¿La persona puede saber en todo momento dónde está y a dónde puede ir? |  |
| Búsqueda como red de contención | ¿La búsqueda entrega resultados relevantes con errores de tipeo o sinónimos? |  |
| Múltiples caminos | ¿Hay más de una forma de llegar al contenido importante? |  |
| Consistencia de navegación | ¿La estructura de navegación se comporta igual en todas las secciones? |  |

---

## Solapamientos conocidos

**Nomenclatura**: acá se evalúan las categorías y rótulos de la estructura — el vocabulario del resto del copy es de Contenido y Lenguaje (3). **Consistencia de la navegación**: acá es estructural (la navegación se comporta igual en todas las secciones) — la consistencia general de conceptos y comportamiento es de Fundamentos (1).

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

Un documento de hallazgos de navegación y arquitectura de información, con la tabla de hallazgos y el
checklist de cobertura completos, listo para combinarse con las demás dimensiones en la Skill 9, o para
entregarse solo.

---

## Conexión con el resto del stack

Recibe el Documento de Contexto y Acceso de Skill 0. Su documento de hallazgos es uno de los
insumos que lee la Skill 9 al armar el informe final.
