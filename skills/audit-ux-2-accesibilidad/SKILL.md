---
name: audit-ux-2-accesibilidad
description: >
  Audita un producto digital contra los cuatro principios de accesibilidad: perceptible,
  operable, comprensible y robusto. No reemplaza una auditoría de accesibilidad formal contra
  un nivel de conformancia específico — es el primer filtro para detectar barreras reales de
  uso. Funciona como Skill 2 del stack de auditoría o de forma independiente. Disparar ante
  frases como "audita la accesibilidad de esto", "revisa si esto es usable sin mouse", "comprueba
  el contraste de esta interfaz". Al detectar que aplica, confirmar: "¿Empezamos auditando
  accesibilidad? Voy a revisar contraste, navegación sin mouse, y qué tan bien se entiende sin
  depender de un solo sentido."
---

# Skill 2 — Accesibilidad

Audita si el producto se puede usar con distintas capacidades: sin mouse, sin depender del
color, con lectores de pantalla, con distintos niveles de visión.

---

## Objetivo de esta skill

Producir un documento de hallazgos de accesibilidad que:
- Usado en stack: se combina con los de las otras 7 dimensiones en la Skill 9
- Usado sola: es un informe de accesibilidad completo y autosuficiente

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
hallazgos** — una fila por hallazgo, con ID `accesibilidad-NN` que coincide con la nomenclatura de
evidencia de `referencia-evidencia.md` — y el **checklist de cobertura** — una fila por
checkpoint con su estado final. Un checkpoint produce tantas filas de hallazgo como problemas
se identifiquen: **la cantidad de hallazgos no se limita nunca**.

---

## Checkpoints

1. **Contraste de color** — ¿el contraste entre texto y fondo cumple el mínimo esperado (4.5:1
   para texto normal), y se sostiene en estados hover, disabled y sobre imágenes?
2. **El color no es el único portador de significado** — si un estado o categoría se comunica
   con color, ¿hay también un ícono o texto que diga lo mismo?
3. **Texto alternativo y multimedia accesible** — ¿las imágenes que comunican información
   tienen descripción para lectores de pantalla? ¿el video o audio tiene subtítulos o
   transcripción?
4. **Navegable sin mouse o táctil** — ¿se puede completar una tarea entera usando solo teclado
   (web/desktop) o los gestos del lector de pantalla (mobile)?
5. **Foco visible y orden lógico** — ¿el indicador de foco es visible, y el orden de navegación
   sigue la lógica visual de la pantalla?
6. **Lenguaje claro y errores explicados** — ¿el contenido evita jerga innecesaria, y los
   mensajes de error dicen con precisión qué falló y cómo corregirlo?
7. **Comportamiento consistente y predecible** — ¿los mismos elementos se comportan igual en
   todo el producto, sin acciones inesperadas al recibir foco?
8. **Compatible con tecnologías de asistencia** — ¿el contenido puede ser interpretado
   correctamente por un lector de pantalla, con un orden de lectura que coincide con el
   visual?

---

## Verificación por código (web con acceso autónomo)

Cuando el producto es web y hay acceso al DOM, no quedarse en la inspección visual — esta
dimensión es la que más gana verificando por código:

- **Contraste exacto, no estimado**: leer los colores computados (CSS) de texto y fondo y
  calcular el ratio real — incluidos los estados hover, focus, disabled y el texto sobre
  imágenes. Un contraste "que se ve bien" a ojo puede estar en 3.8:1.
- **Texto alternativo y semántica**: revisar en el DOM la presencia y calidad de `alt` en
  imágenes informativas (un `alt=""` en una imagen que comunica información es un hallazgo,
  igual que un `alt` genérico tipo "imagen"), etiquetas accesibles (`aria-label`,
  `aria-labelledby`) en controles sin texto visible, y roles/landmarks que estructuran la
  página para un lector de pantalla.
- **Orden de tabulación desde el DOM**: detectar `tabindex` positivos, elementos interactivos
  no enfocables (divs clickeables sin rol ni tabindex), y divergencias entre el orden del DOM
  y el orden visual — además del recorrido manual con Tab.

Lo verificado por código pesa igual que lo observado en pantalla: es evidencia directa. Se
registra según `referencia-evidencia.md`, guardando el valor extraído junto a la captura.

---

## Documento de hallazgos

### Tabla de hallazgos

Una fila por hallazgo. El ID (`accesibilidad-NN`) es el mismo que llevan sus archivos de evidencia.
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
| Contraste de color | ¿El contraste texto/fondo se sostiene en todos los estados (hover, disabled, sobre imagen)? |  |
| Color no exclusivo | ¿Hay una segunda señal (ícono, texto) además del color para comunicar estado o error? |  |
| Texto alternativo y multimedia | ¿Las imágenes con información tienen descripción? ¿El video/audio tiene subtítulos o transcripción? |  |
| Navegable sin mouse/táctil | ¿Se puede completar la tarea entera solo con teclado o gestos de accesibilidad? |  |
| Foco visible y orden lógico | ¿El foco es visible y sigue el orden visual esperado? |  |
| Lenguaje claro y errores explicados | ¿El mensaje de error señala con precisión qué falló y cómo corregirlo? |  |
| Comportamiento consistente | ¿Ningún elemento dispara una acción inesperada solo al recibir foco? |  |
| Compatible con tecnologías de asistencia | ¿El orden de lectura coincide con el visual para un lector de pantalla? |  |

---

## Solapamientos conocidos

**Contraste**: acá se verifica el ratio numérico contra el mínimo (4.5:1) — su uso como herramienta de jerarquía es de Jerarquía y Claridad Visual (4). **Lenguaje claro y errores explicados**: acá se evalúa como barrera de acceso cognitiva — la redacción fina del copy es de Contenido y Lenguaje (3). **Comportamiento consistente**: el ángulo de accesibilidad es que nada inesperado ocurra al recibir foco — la consistencia general de conceptos es de Fundamentos (1).

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
- **No inventar hallazgos.** Si un checkpoint no se pudo verificar (frecuente en esta
  dimensión, sobre todo con lectores de pantalla en mobile), se activa el protocolo de brecha
  de acceso — no se completa igual con una suposición.
- **Verificar por código cuando el acceso lo permite.** En web con acceso autónomo, el
  contraste, el texto alternativo y el orden de tabulación se verifican en el DOM y los estilos
  computados, no a ojo (ver sección "Verificación por código").
- **Conducta durante el recorrido.** Preguntas en lote (nunca validación elemento-por-elemento),
  narrar en una línea qué se está mirando, y comunicar hallazgos al cierre de la dimensión —
  según `referencia-conducta-auditora.md`.
- **Adaptar el idioma** al que use la persona en la conversación.
- **El documento es editable.** Antes de darlo por cerrado, confirmar que no falta nada.

---

## Output esperado

Un documento de hallazgos de accesibilidad, con la tabla de hallazgos y el checklist de cobertura completos, listo para
combinarse con las demás dimensiones en la Skill 9, o para entregarse solo.

---

## Conexión con el resto del stack

Recibe el Documento de Contexto y Acceso de Skill 0. Su documento de hallazgos es uno de los
insumos que lee la Skill 9 al armar el informe final.
