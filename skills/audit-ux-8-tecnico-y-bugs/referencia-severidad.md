# Referencia — Rúbrica de severidad

Documento de consulta, no es una skill invocable. Las skills 1 a 8 lo citan cada vez que asignan severidad a un hallazgo; la skill 9 lo cita al priorizar el informe. La escala no se aplica de memoria ni por intuición: se aplica esta rúbrica.

## La escala

Escala de 5 niveles adaptada de Nielsen, con capa de color para lectura rápida. Todo hallazgo lleva ambos: el número y el color derivado.

| Nivel | Color | Definición | Ejemplo calibrado |
|---|---|---|---|
| 0 | 🔵 | No es un problema de usabilidad | Preferencia estética sin evidencia de fricción para nadie |
| 1 | 🔵 | Cosmético — se corrige solo si sobra tiempo | Desalineación visual leve en una página secundaria; typo que no cambia el sentido |
| 2 | 🟡 | Menor — genera fricción, la persona igual completa la tarea | Etiqueta ambigua que obliga a "probar a ver qué pasa"; placeholder como única etiqueta en un formulario corto |
| 3 | 🟠 | Mayor — dificulta seriamente la tarea o la hace fallar a veces | Validación que borra lo ya cargado; contraste insuficiente en la acción primaria; demora larga sin señal de progreso en el flujo principal, reproducida |
| 4 | 🔴 | Catástrofe — impide completar la tarea, o causa pérdida de datos/dinero/confianza | No se puede finalizar el flujo principal en un navegador soportado; el trabajo se pierde sin aviso; no se puede pagar |

## Cómo se calcula

La severidad cruza cuatro factores — ninguno alcanza solo:

1. **Frecuencia** — ¿cuántas personas se lo cruzan, y qué tan seguido?
2. **Impacto** — cuando ocurre, ¿qué tan grave es para la tarea?
3. **Persistencia** — ¿se lo cruza una vez y aprende a esquivarlo, o molesta cada vez?
4. **Impacto de mercado** — cuando aplica: ¿daña la confianza, la marca, o empuja a la competencia?

## Regla de reproducción (hallazgos intermitentes)

Antes de asignar severidad a un problema que no ocurre siempre:

1. **Intentar reproducirlo al menos 3 veces**, en las mismas condiciones.
2. **2 o más ocurrencias** → el hallazgo cuenta como reproducible; la severidad se asigna con la rúbrica normal.
3. **1 sola ocurrencia en 3+ intentos** → se documenta como **observación única**: severidad provisoria (máximo 2), etiqueta explícita de "no reproducido", y pedido de re-verificación. No se infla ni se descarta.

**Contraejemplo calibrado** (error real a no repetir): una búsqueda que tarda 8 segundos 1 de 2 veces **no es severidad 4**. No impide la tarea ni pierde datos. Reproducida y en el flujo principal es un 3; en una sección secundaria, un 2.

## Cuándo la baja frecuencia NO baja la severidad

La frecuencia baja descuenta severidad en molestias, no en bloqueos. Si el problema **impide por completo la tarea o pierde datos/dinero**, sigue siendo 3-4 aunque afecte a poca gente: para la persona que lo sufre, ocurre el 100% de las veces que le importa. Un checkout roto solo en un navegador minoritario no es "raro" — es catastrófico para todo el segmento que usa ese navegador.

## Cruce con el objetivo del flujo

El mismo defecto pesa distinto según dónde vive. Antes de puntuar, preguntarse: ¿este problema está en el flujo que el producto necesita que funcione (conversión, tarea principal declarada en el Documento de Contexto y Acceso), o en una zona periférica? Un contraste pobre en el botón de pagar y el mismo contraste en el footer no comparten severidad.

## Señal de recalibrado

Si al cerrar una dimensión más de 1 de cada 5 hallazgos quedó en severidad 4, la escala está inflada: releer esta rúbrica y re-puntuar. Las catástrofes reales son raras — cuando todo es urgente, nada lo es, y el informe pierde credibilidad.
