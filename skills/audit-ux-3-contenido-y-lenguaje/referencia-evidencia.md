# Referencia — Protocolo de evidencia

Documento de consulta, no es una skill invocable. Las skills 1 a 8 lo citan al registrar la evidencia de cualquier hallazgo. La skill 9 lo cita al verificar que cada hallazgo del informe tenga su respaldo.

## Principio

**La evidencia se captura en el momento en que se observa, no se reconstruye al final.** Una pantalla que mostró un error puede no volver a mostrarlo; un estado intermedio desaparece al seguir navegando. Si al cerrar la auditoría hay que "volver a buscar" la evidencia de un hallazgo, el protocolo falló.

## Dónde se guarda

En una carpeta `evidencia/` junto al documento de hallazgos de la dimensión (o donde la persona indique al arrancar). Se guarda a disco a medida que se avanza — no se acumula en la conversación ni en la memoria de la sesión.

## Nomenclatura

```
[dimensión]-[NN]-[descripción-corta].[ext]
```

Ejemplos: `accesibilidad-03-contraste-boton-primario.png`, `formularios-01-validacion-borra-campos.png`, `tecnico-02-error-consola-checkout.txt`.

La numeración es secuencial dentro de la dimensión y coincide con el **ID del hallazgo** en la tabla de hallazgos de esa dimensión: el hallazgo `accesibilidad-03` referencia el archivo `accesibilidad-03-*.png`. Un hallazgo puede referenciar más de un archivo (secuencias, intentos de reproducción); en ese caso se agrega un sufijo: `formularios-01a-...`, `formularios-01b-...`.

## Qué evidencia merece cada tipo de hallazgo

| Tipo de hallazgo | Evidencia mínima |
|---|---|
| Visual (contraste, jerarquía, alineación) | Captura del estado exacto donde se observa |
| De interacción o flujo | Secuencia antes/después (2+ capturas), o grabación si el problema es de timing |
| De contenido o lenguaje | Cita textual exacta + captura de dónde aparece |
| Técnico | Captura + registro de consola o red cuando hay acceso a herramientas de desarrollador |
| Intermitente | Evidencia de **cada intento** de reproducción (incluidos los que no fallaron), para sostener la regla de reproducción de `referencia-severidad.md` |

## Regla de oro

**Sin evidencia no hay hallazgo — hay hipótesis.** Cada fila del checklist que registre un problema referencia al menos un archivo de evidencia. Si algo se observó pero no se pudo capturar, se re-verifica hasta capturarlo, o se marca con el protocolo de brecha de acceso — no entra al informe como hallazgo firme.

## En modo asistido

Cuando la evidencia la comparte la persona (capturas, grabaciones), se archiva con la misma nomenclatura y se etiqueta el origen: `verificado por la persona`. La trazabilidad del informe final no distingue calidad por origen — distingue quién lo vio.
