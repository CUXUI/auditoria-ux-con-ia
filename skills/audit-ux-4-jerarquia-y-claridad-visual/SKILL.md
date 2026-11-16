---
name: audit-ux-4-jerarquia-y-claridad-visual
description: >
  Audita la disposición visual de un producto digital: qué se agrupa, qué se destaca, y qué
  tan rápido se puede escanear, interpretar y actuar sobre una pantalla. Funciona como Skill 4
  del stack de auditoría o de forma independiente. Disparar ante frases como "audita el visual
  de esto", "revisa la jerarquía de esta pantalla", "comprueba si esto se lee bien". Al detectar
  que aplica, confirmar: "¿Empezamos auditando jerarquía y claridad visual? Voy a revisar si
  la pantalla guía la atención hacia lo importante, o si compite consigo misma."
---

# Skill 4 — Jerarquía y Claridad Visual

Audita si la disposición visual del producto guía la atención hacia lo importante, o si el
ruido visual compite con la tarea que la persona está tratando de resolver.

---

## Objetivo de esta skill

Producir un documento de hallazgos de jerarquía visual que:
- Usado en stack: se combina con los de las otras 7 dimensiones en la Skill 9
- Usado sola: es un informe visual completo y autosuficiente

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
hallazgos** — una fila por hallazgo, con ID `visual-NN` que coincide con la nomenclatura de
evidencia de `referencia-evidencia.md` — y el **checklist de cobertura** — una fila por
checkpoint con su estado final. Un checkpoint produce tantas filas de hallazgo como problemas
se identifiquen: **la cantidad de hallazgos no se limita nunca**.

---

## Checkpoints

1. **Agrupación de elementos relacionados** — ¿lo que está conectado por función se ve
   agrupado, con más espacio entre grupos distintos que dentro de un mismo grupo?
2. **Orden de importancia** — ¿la información más importante para la tarea se percibe primero,
   sin tener que buscarla?
3. **Separación entre contenido y controles** — ¿se distingue con claridad qué se lee y qué se
   toca?
4. **Elementos interactivos reconocibles** — ¿los botones y enlaces se ven claramente
   interactivos, sin obligar a "probar a ver si funciona"?
5. **Color con mesura** — ¿el color refuerza la jerarquía y el contenido, o aparece sin
   propósito funcional claro?
6. **Contraste que dirige la atención** — ¿el contraste entre elementos ayuda a distinguir lo
   importante de lo secundario?
7. **Tipografía legible y consistente** — ¿el tamaño, peso y espaciado del texto son cómodos de
   leer, y se mantienen consistentes en todo el producto?
8. **Ningún elemento destructivo por defecto** — ¿la opción resaltada o preseleccionada en una
   pantalla es siempre la no destructiva?

---

## Documento de hallazgos

### Tabla de hallazgos

Una fila por hallazgo. El ID (`visual-NN`) es el mismo que llevan sus archivos de evidencia.
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
| Agrupación de elementos | ¿Lo que está conectado por función se ve agrupado en pantalla? |  |
| Orden de importancia | ¿La información más importante se percibe primero, sin buscarla? |  |
| Separación contenido/controles | ¿Se distingue con claridad qué se lee y qué se toca? |  |
| Elementos interactivos reconocibles | ¿Los botones y enlaces se ven claramente interactivos? |  |
| Color con mesura | ¿Los colores refuerzan la jerarquía o interfieren con ella? |  |
| Contraste funcional | ¿El contraste ayuda a distinguir lo importante de lo secundario? |  |
| Tipografía legible | ¿Las fuentes son fáciles de leer y consistentes en todo el producto? |  |
| Sin default destructivo | ¿La opción resaltada por defecto es siempre la no destructiva? |  |

---

## Solapamientos conocidos

**Contraste**: acá se evalúa como herramienta de jerarquía (que lo importante se distinga de lo secundario) — el ratio numérico contra el mínimo de accesibilidad es de Accesibilidad (2). **Elementos interactivos reconocibles** roza Fundamentos (1, consistencia y estándares): acá el ángulo es visual — si *se ve* interactivo —, en la 1 es si *se comporta* como se espera.

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

Un documento de hallazgos de jerarquía y claridad visual, con la tabla de hallazgos y el checklist de cobertura completos,
listo para combinarse con las demás dimensiones en la Skill 9, o para entregarse solo.

---

## Conexión con el resto del stack

Recibe el Documento de Contexto y Acceso de Skill 0. Su documento de hallazgos es uno de los
insumos que lee la Skill 9 al armar el informe final.
