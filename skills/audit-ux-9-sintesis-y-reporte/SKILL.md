---
name: audit-ux-9-sintesis-y-reporte
description: >
  Ensambla los hallazgos de las dimensiones auditadas (una o varias) en un informe final con
  hallazgos priorizados, insights, y recomendaciones. Funciona como Skill 9, la última del
  stack de auditoría — requiere al menos una skill de dimensión ya corrida, no funciona sola
  desde cero. Disparar ante frases como "arma el informe final", "junta todos los hallazgos",
  "necesito presentar esto". Al detectar que aplica, confirmar: "¿Armamos el informe final con
  todo lo que auditamos hasta ahora?"
---

# Skill 9 — Síntesis y Reporte

Convierte los documentos de hallazgos de cada dimensión auditada en un informe único, legible
por alguien que no participó de la auditoría.

---

## Objetivo de esta skill

Tomar uno o más documentos de hallazgos (de cualquiera de las 8 dimensiones, no hace falta que
estén las ocho) y producir un **Informe de Auditoría** que separe lo urgente de lo secundario,
explique el patrón detrás de los hallazgos sueltos, y proponga qué hacer al respecto.

---

## Protocolo de ejecución

### Paso 1 — Reunir los documentos de hallazgos

Juntar las tablas de hallazgos y los checklists de cobertura de cada dimensión que se haya
auditado.

### Paso 2 — Verificar el respaldo de cada hallazgo

Antes de ensamblar nada, revisar que cada hallazgo referencie al menos un archivo de evidencia
según `referencia-evidencia.md`. Un hallazgo sin respaldo no entra al informe como hallazgo
firme: o se re-verifica y captura en el momento, o baja a hipótesis / brecha de acceso, con esa
etiqueta visible. Sin evidencia no hay hallazgo — hay hipótesis.

### Paso 3 — Fusionar duplicados entre dimensiones

Cuando corrieron varias dimensiones, el mismo defecto raíz puede aparecer en más de una (un
contraste pobre puede figurar en Accesibilidad y en Jerarquía Visual; un mensaje de error, en
Contenido y en Estados). Detectar esos casos y fusionarlos en **un solo hallazgo** que:
- conserva la severidad más alta asignada,
- lista todas las dimensiones que lo detectaron (columna "Dimensión/es"),
- referencia toda la evidencia acumulada.

Fusionar es unir duplicados del mismo defecto raíz, no comprimir el informe: dos problemas
distintos que comparten pantalla siguen siendo dos hallazgos. Ante la duda, no fusionar.

### Paso 4 — Distinguir hallazgo, insight y recomendación

Un hallazgo describe lo que se encontró. Un insight explica qué significa. Una recomendación
dice qué hacer al respecto. Ejemplo:
- Hallazgo: "El botón de continuar no se ve en mobile."
- Insight: "La baja visibilidad de las acciones primarias en mobile genera abandono en puntos
  de decisión clave — el problema no es el botón, es la jerarquía visual en pantallas
  pequeñas."
- Recomendación: "Aumentar el contraste y el tamaño de los botones primarios en el breakpoint
  mobile, empezando por los puntos de conversión."

No mezclar los tres niveles en una sola frase. La fórmula del insight (observación +
consecuencia, con su test rápido) y la frontera entre recomendación y rediseño están definidas
en `referencia-informe.md` — aplicarlas en los pasos 6 y 7.

### Paso 5 — Separar hallazgos del foco principal de los periféricos

Si la auditoría tuvo un foco definido (una dimensión principal) y aparecieron hallazgos de
otras dimensiones en el camino, separarlos en dos grupos. Los periféricos se registran sin
analizarlos en profundidad — quedan documentados para una futura auditoría de esa dimensión.

Esta categoría solo existe si el Documento de Contexto y Acceso declaró un foco. Si el alcance
fue integral, **todos los hallazgos son principales** y se organizan por severidad — no usar
"periférico" para acortar el informe (ver `referencia-informe.md`).

### Paso 6 — Convertir hallazgos en insights

Agrupar los hallazgos por patrón, no por orden en que se encontraron. Escribir **hasta 4
insights — solo los que los hallazgos realmente sostengan**. Si los hallazgos no forman ningún
patrón (frecuente en auditorías cortas o de una sola dimensión), el informe lo dice
explícitamente en una línea en lugar de fabricar un insight: inventar un patrón viola la misma
regla que inventar un hallazgo. Cada insight tiene que poder leerse de forma independiente y
tener sentido sin haber visto los hallazgos individuales.

### Paso 7 — Una recomendación por insight, con prioridad

Por cada insight, una recomendación concreta con una dirección clara — no hace falta que sea la
solución final. Asignar prioridad (alta / media / baja) cruzando la severidad de los hallazgos
que sostienen ese insight con qué tan accionable es la recomendación.

Una recomendación da dirección y criterio de éxito — **no entrega rediseños**, mockups ni
pantallas "como debería quedar" (ver `referencia-informe.md`). Si la persona quiere propuestas
de rediseño, se acuerda como entregable aparte.

### Paso 8 — Elegir cómo se presenta la evidencia

Toda la evidencia ya existe como archivos en la carpeta `evidencia/`. Antes de volcar el
informe, preguntar cómo se va a entregar, según quién lo va a leer (ver `referencia-informe.md`,
regla 8):

- **Referenciada** — la tabla nombra el archivo y la carpeta `evidencia/` acompaña al informe.
- **Mostrada** — además, se agrega un anexo `### Evidencia` al final, con cada captura embebida
  bajo su ID (`![formularios-01a](evidencia/formularios-01-...png)`). Recomendada para presentar
  a un cliente o exportar a PDF.

La tabla de hallazgos es igual en los dos modos; la diferencia es solo si se agrega el anexo.

### Paso 9 — Generar el Informe de Auditoría

```
## INFORME DE AUDITORÍA — [Nombre del producto]

### Alcance
- Producto: [nombre, plataforma]
- Dimensiones auditadas: [lista]
- Acceso: [nivel de acceso con el que se auditó]
- Fecha: [fecha]

### Cómo leer este informe
[una línea de introducción + mini-tabla de la escala de severidad: nivel, color, qué significa
— según referencia-severidad.md. El lector no participó de la auditoría: sin esta leyenda no
puede priorizar nada.]

### Hallazgos principales
[tabla: ID | Hallazgo | Evidencia | Severidad | Dimensión/es | Verificado por — con los
duplicados entre dimensiones ya fusionados. Entran TODOS los hallazgos con evidencia: los de
severidad baja se agrupan al final de la tabla, nunca se omiten]

### Qué funciona bien
[sección opcional — 2-3 patrones del producto que conviene no romper al corregir el resto,
cada uno con evidencia, según referencia-informe.md. Si nada alcanza esa vara, se omite la
sección]

### Hallazgos fuera de foco
[tabla: Hallazgo | Dimensión a la que pertenece]

### Insights
1. [insight 1]
2. [insight 2]
[hasta 4]

### Recomendaciones
[tabla: Insight relacionado | Recomendación | Prioridad]

### Brechas de acceso pendientes
[lista de checkpoints marcados como "no verificable con acceso actual" en cualquier dimensión,
que sigan sin resolver]

### Evidencia
[solo en modo "mostrada" (Paso 8): cada ID con su(s) captura(s) embebida(s) desde la carpeta
evidencia/. En modo "referenciada", esta sección se omite y la carpeta acompaña al informe]
```

---

## Reglas de comportamiento

- **No releer una referencia ya leída.** Cada skill del stack lleva su propia copia de las
  reglas para poder funcionar sola, pero el contenido es idéntico en todas. Si en esta misma
  conversación ya se leyó una referencia al correr otra skill del stack, no se vuelve a abrir:
  las reglas ya están en contexto.

- **El informe se escribe para alguien que no participó.** Abre con contexto y leyenda de
  severidad antes del primer hallazgo, y sigue las reglas de `referencia-informe.md`.
- **Sin evidencia no hay hallazgo.** Ningún hallazgo entra al informe sin su respaldo
  verificado en el Paso 2 — baja a hipótesis o brecha de acceso, con etiqueta visible.
- **No inflar el informe — pero nunca recortarlo.** Los hallazgos de severidad baja se agrupan,
  no se destacan uno por uno en la sección principal; omitir un hallazgo con evidencia es un
  error del informe. La cantidad de hallazgos no se limita.
- **Fusionar duplicados, no comprimir.** Mismo defecto raíz detectado por varias dimensiones =
  un hallazgo con todas sus dimensiones y evidencia. Ante la duda, no fusionar.
- **No mezclar hallazgo, insight y recomendación** en la misma frase — son tres cosas distintas
  y el informe pierde claridad si se combinan.
- **Priorizar por severidad**, no por el orden en que se encontraron los hallazgos.
- **Dejar explícitas las brechas de acceso** que sigan sin resolver — no cerrarlas en silencio.

---

## Output esperado

Un **Informe de Auditoría** completo, priorizado, listo para presentar a alguien que no
participó del proceso.

---

## Conexión con el resto del stack

Esta skill es el punto de llegada del stack. Lee lo que produjeron las skills 1-8 (o algunas de
ellas) y el nombre/alcance del producto que definió Skill 0. No alimenta a ninguna skill
posterior.
