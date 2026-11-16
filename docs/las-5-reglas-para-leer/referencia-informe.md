# Referencia — Reglas del informe final

Documento de consulta, no es una skill invocable. La skill 9 lo cita al ensamblar el Informe de Auditoría. Su lector objetivo es siempre el mismo: **alguien que no participó de la auditoría** — el informe se escribe para esa persona, no para quien auditó.

## 1. El informe abre con contexto y leyenda

Antes de mostrar un solo hallazgo, el informe responde: qué se auditó (producto, plataforma, alcance), con qué acceso, cuándo, y **cómo leer lo que sigue** — en particular, la escala de severidad explicada en una mini-tabla (0-4 con sus colores, una línea por nivel, según `referencia-severidad.md`).

Nunca arrancar con la tabla de hallazgos en seco: un lector que no sabe qué significa "3 🟠" no puede priorizar nada, y un lector que no sabe qué quedó fuera del alcance va a asumir que lo no mencionado está bien.

## 2. Fórmula del insight: observación + consecuencia

Un insight se compone de dos partes obligatorias: **qué se observó** (el patrón detrás de hallazgos sueltos) y **qué consecuencia tiene** para la persona que usa el producto o para el negocio.

**Test rápido:** si el insight no nombra ninguna consecuencia, es un hallazgo disfrazado — volver a escribirlo.

- ✘ "Varios botones primarios tienen bajo contraste en mobile." *(hallazgo agrupado, no insight)*
- ✔ "La baja visibilidad de las acciones primarias en mobile hace que los puntos de decisión clave pasen desapercibidos — el costo probable es abandono justo donde el producto necesita conversión." *(observación + consecuencia)*

## 3. Recomendación ≠ rediseño

Una recomendación da **dirección y criterio de éxito**: qué cambiar, en qué sentido, y cómo saber que quedó resuelto. No entrega pantallas rediseñadas, mockups ni especificaciones de solución — eso es otro servicio, con otro proceso y otro precio.

- ✔ "Aumentar el contraste del botón de pagar hasta cumplir al menos 4.5:1, empezando por los puntos de conversión."
- ✘ Adjuntar la pantalla rediseñada "como debería quedar".

Si la persona pide explícitamente propuestas de rediseño, se acuerda como entregable aparte — no se cuela dentro del informe de auditoría.

## 4. "Periférico" solo existe si hubo foco declarado

La categoría "hallazgos fuera de foco" aplica únicamente cuando el Documento de Contexto y Acceso declaró una dimensión o flujo principal. Si el alcance fue integral (todas las dimensiones, producto completo), **todos los hallazgos son principales** y se organizan por severidad — no inventar la categoría para esconder hallazgos incómodos ni para acortar el informe.

## 5. Los hallazgos no se limitan en cantidad

En el informe entra **todo lo que se identificó y tiene evidencia** — no hay tope de hallazgos por checkpoint, por dimensión ni por informe. "No inflar el informe" significa no destacar uno por uno los hallazgos cosméticos en la sección principal (se agrupan), nunca omitirlos: un hallazgo con evidencia que no aparece en el informe es un error del informe.

## 6. Qué funciona bien (sección opcional, misma vara)

El informe puede incluir una sección corta de fortalezas: patrones del producto que funcionan y conviene **no romper** al corregir el resto. Máximo 2-3 ítems, cada uno con la misma exigencia que un hallazgo — algo observado directamente, con evidencia, no un cumplido de cortesía. Si nada alcanza esa vara, la sección se omite; nunca se rellena.

## 7. Las brechas de acceso quedan visibles

Todo checkpoint que quedó como "no verificable con acceso actual" aparece en su propia sección al final del informe, con la guía de cómo verificarlo. Un informe que las omite implica silenciosamente que se revisó todo — y eso es falso.

## 8. Cómo se presenta la evidencia: referenciada o mostrada

Toda la evidencia existe siempre como archivos en la carpeta `evidencia/` (según `referencia-evidencia.md`). Lo que cambia es **cómo el informe la presenta**, y eso se decide al cerrar según quién va a leerlo:

- **Referenciada** — la columna "Evidencia" de la tabla nombra el archivo (`formularios-01a.png`), y la carpeta `evidencia/` acompaña al informe. Más liviano; el lector abre la carpeta para ver la prueba. Sirve para un equipo que trabaja junto a los archivos.
- **Mostrada** — además de la referencia, el informe agrega un **anexo de evidencia** al final: una sección `### Evidencia` donde cada ID muestra su captura (markdown con la imagen embebida, `![formularios-01a](evidencia/formularios-01-...png)`). La prueba se ve sin salir del documento. Es la forma recomendada cuando el informe se presenta a un cliente o se exporta a PDF.

La tabla de hallazgos es idéntica en ambos modos — la columna "Evidencia" siempre lleva el ID del archivo. La diferencia es solo si existe o no el anexo que las muestra. El modo mostrado nunca reemplaza la referencia trazable: la agrega.
