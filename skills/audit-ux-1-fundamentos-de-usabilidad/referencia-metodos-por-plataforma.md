# Referencia — Métodos de verificación por plataforma

Documento de consulta, no es una skill invocable. Las skills 1 a 8 lo citan cuando el método de verificación de un checkpoint cambia según la plataforma del producto auditado.

| Qué hay que verificar | Web | Mobile | Desktop |
|---|---|---|---|
| Operable sin mouse/táctil | Recorrer con Tab / Shift+Tab / Enter / flechas, sin tocar el mouse | Gestos de VoiceOver (iOS) o TalkBack (Android) — **siempre brecha de acceso**, pedir a la persona que lo verifique y reporte | Recorrer con los atajos de teclado estándar del sistema operativo |
| Foco visible / orden de navegación | Observar el indicador de foco mientras se tabula | Depende del lector de pantalla activo — brecha de acceso si no hay uno corriendo | Observar el indicador de foco mientras se navega por teclado |
| Contraste de color | Leer los valores de color computados y calcular el ratio, o usar una herramienta de contraste sobre una captura | Captura de pantalla + herramienta de contraste sobre la imagen | Captura de pantalla + herramienta de contraste sobre la imagen |
| El color no es la única señal | Simular la pantalla en escala de grises (herramienta de accesibilidad del navegador) o revisar visualmente si hay una segunda señal (ícono, texto) | Igual que web, sobre la captura | Igual que web, sobre la captura |
| Tiempo de respuesta del sistema | Observación directa + inspección de la pestaña de red si hay acceso a herramientas de desarrollador | Observación directa, cronometrando con un timer externo si hace falta precisión | Observación directa, cronometrando con un timer externo si hace falta precisión |
| Compatibilidad entre navegadores/dispositivos | Repetir el recorrido en al menos dos navegadores y un dispositivo mobile real o emulado | Repetir en al menos dos combinaciones de SO + versión si hay acceso a más de un dispositivo/emulador | Repetir en al menos dos versiones del sistema operativo si hay acceso |
| Comportamiento con conexión lenta | Activar la limitación de velocidad de red en las herramientas de desarrollador del navegador | Activar modo de datos limitados del dispositivo o simulador, si el sistema lo permite | Generalmente no aplica salvo que la app dependa de red — usar un limitador de ancho de banda del sistema si existe |
| Casos límite de navegación (atrás, refrescar, doble pestaña) | Usar directamente los controles del navegador | Usar el botón de atrás nativo del sistema operativo, y abrir la app dos veces si el sistema lo permite | Usar atajos de "deshacer/rehacer" o reabrir la aplicación, según corresponda |

## Cuándo esto se convierte en brecha de acceso

Cualquier fila donde la columna de la plataforma auditada diga "brecha de acceso", o donde la IA no tenga control directo del dispositivo/simulador correspondiente, activa el protocolo de brecha de acceso definido en skill-0: se marca explícitamente, se da una guía corta de cómo verificarlo, se pide el resultado, y se documenta con la etiqueta de quién lo verificó.
