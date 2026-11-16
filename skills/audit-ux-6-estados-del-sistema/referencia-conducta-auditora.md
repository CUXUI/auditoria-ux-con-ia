# Referencia — Conducta auditora

Documento de consulta, no es una skill invocable. Aplica a todo el stack (skills 0 a 9) durante toda la auditoría: define cómo se recorre, cuándo se pregunta, y cómo se comunica el avance. Las skills de dimensión lo citan antes de empezar su recorrido.

## 1. Pasada de persona real primero

Antes de cualquier pasada analítica, recorrer el flujo completo **como lo haría una persona real**: sin frenar a analizar, sin abrir herramientas, sin puntuar nada. Anotar solo las fricciones que saltan solas — lo que confunde, lo que hace dudar, lo que obliga a releer.

- Esta pasada ocurre **una sola vez por auditoría**, no una vez por dimensión. Si ya se hizo (en skill-0 o al arrancar la primera dimensión), no se repite: las dimensiones siguientes leen esas notas.
- Sus anotaciones no son hallazgos todavía — son pistas que las pasadas analíticas van a confirmar con método y evidencia.
- **Esta pasada es también el único primer encuentro genuino de toda la auditoría.** Antes de interactuar con nada, anotar (y capturar en pantalla, según `referencia-evidencia.md`) qué transmite el producto en frío: qué es, si parece confiable, qué invita a hacer primero. Ese momento no se puede repetir — cualquier dimensión que lo necesite después (en particular Estados del Sistema, bloque "primer encuentro") consume estas notas en lugar de intentar recrearlo con una sesión ya usada.

**Por qué:** analizar elemento por elemento desde el primer segundo produce una auditoría que ninguna persona real experimentó. La fricción real aparece usando el producto, no inspeccionándolo.

## 2. Plan confirmado antes de analizar

Con el contexto definido y la pasada de persona real hecha, presentar el plan en pocas líneas — qué dimensiones corren, en qué orden, qué flujos se van a mirar — y **confirmar antes de arrancar el análisis**. La persona tiene que poder redirigir el foco antes de que se gaste tiempo en él.

## 3. Preguntas en lote, nunca validación elemento-por-elemento

- **Nunca** validar con la persona campo por campo, pantalla por pantalla, o hallazgo por hallazgo mientras se audita. Eso convierte la auditoría en un interrogatorio y rompe el flujo de las dos partes.
- Las dudas que aparecen durante el recorrido se **anotan y se agrupan**. Se hacen en lote en pausas naturales: al cerrar una dimensión, al terminar un flujo, o cuando algo bloquea seguir.
- Única excepción para interrumpir en el momento: un bloqueo real (no se puede seguir sin ese dato) o un hallazgo de severidad 4 que cambia cómo conviene continuar.

## 4. Narrar el trabajo

Al cambiar de dimensión, de herramienta o de flujo, decirlo en una línea: qué skill está corriendo, qué se está por mirar, con qué método. La persona tiene que poder seguir el hilo del trabajo sin preguntarlo — pero la narración es una línea, no un discurso: no reemplaza al avance real.

## 5. Hallazgos al cierre, no en goteo

Los hallazgos se comunican como resumen al **cerrar cada dimensión** — no uno por uno en tiempo real. El goteo constante de "encontré esto" fragmenta la atención de la persona y le impide ver el patrón. La excepción es la misma del punto 3: bloqueos y severidad 4.

## 6. Ninguna acción con efecto real sin confirmación

Auditar es observar, no operar en serio. Durante todo el recorrido — pasada de persona real incluida — no se ejecuta ninguna acción con consecuencias reales sin confirmación explícita de la persona: pagos o cualquier paso final de un checkout, publicaciones visibles para terceros, envíos de mensajes o correos, borrado de datos, contratación o cancelación de servicios. El límite exacto de hasta dónde se puede operar lo define el Documento de Contexto y Acceso (skill-0, límites de operación); ante la duda, frenar justo antes del efecto y preguntar. Un flujo se puede auditar hasta su último paso reversible — el paso irreversible se documenta como brecha de acceso o se ejecuta solo si la persona lo autoriza en el momento.
