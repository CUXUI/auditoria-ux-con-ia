# Ejemplo: así se ve el resultado final

> **Este informe es una demostración.** "TurnoYa" es un producto inventado, para mostrar el formato de salida del stack sin exponer a ningún cliente real. Los hallazgos y sus prioridades son ilustrativos; el formato, las reglas y la estructura son exactamente los que produce la Skill 9.
>
> **Sobre la columna "Evidencia":** en una auditoría real, cada hallazgo se respalda con una captura que el stack guarda en una carpeta `evidencia/`, con un nombre ligado a su ID (por ejemplo `formularios-01a.png`). Esta demostración muestra esos nombres, no las imágenes, porque el producto no existe. Al cerrar un informe real eliges cómo se entrega la evidencia: **referenciada** (la tabla nombra los archivos y la carpeta acompaña) o **mostrada** (el informe suma un anexo con cada captura embebida, ideal para presentar a un cliente).

---

## INFORME DE AUDITORÍA: TurnoYa

### Alcance

- **Producto:** TurnoYa, aplicación web para reservar turnos médicos en clínicas privadas
- **Quiénes lo usan:** público general, de 25 a 75 años, una o dos veces por mes, con frecuencia bajo apuro
- **Áreas auditadas:** Accesibilidad · Estados del Sistema · Formularios e Interacción
- **Cómo se auditó:** la IA navegó el producto directamente; el lector de pantalla lo comprobó la persona auditora
- **Límites acordados:** entorno de prueba, con permiso para crear cuentas y reservar turnos de prueba
- **Fecha:** 14 de julio de 2026

### Cómo leer este informe

Cada hallazgo lleva una severidad del 0 al 4, asignada con una escala de referencia:

| Nivel | Color | Qué significa |
|---|---|---|
| 0-1 | 🔵 | Cosmético: se corrige si sobra tiempo |
| 2 | 🟡 | Menor: genera fricción, la tarea se completa igual |
| 3 | 🟠 | Mayor: dificulta mucho la tarea, o la hace fallar algunas veces |
| 4 | 🔴 | Catástrofe: impide terminar la tarea, o hace perder datos o dinero |

Lo que no se pudo comprobar aparece al final, en "Pendientes de comprobar".

### Hallazgos principales

| ID | Hallazgo | Evidencia | Severidad | Área | Comprobado por |
|---|---|---|---|---|---|
| formularios-01 | Al fallar la validación del paso 3 (datos de cobertura), se borran los campos ya completados del paso 2 | formularios-01a/01b (antes/después) | 4 🔴 | Formularios · Estados | IA |
| estados-02 | La confirmación de la reserva tarda entre 9 y 11 segundos sin señal de progreso; en 2 de 3 intentos se puede volver a tocar "Confirmar" y duplicar el turno | estados-02a/02b/02c (3 intentos) | 3 🟠 | Estados | IA |
| accesibilidad-01 | El botón "Reservar turno" tiene un contraste de 2.9:1, por debajo del mínimo de 4.5:1, y baja a 2.4:1 al pasar el cursor por encima | accesibilidad-01 + valores medidos | 3 🟠 | Accesibilidad | IA |
| accesibilidad-02 | La reserva no se puede completar solo con el teclado: el selector de horarios queda fuera del recorrido | accesibilidad-02 (grabación) | 3 🟠 | Accesibilidad | IA |
| formularios-03 | Los errores de validación aparecen todos juntos al final del formulario, lejos del campo que los causó | formularios-03 | 2 🟡 | Formularios | IA |
| accesibilidad-04 | El estado de cada turno (confirmado, pendiente, cancelado) se comunica solo con color, comprobado en escala de grises | accesibilidad-04 | 2 🟡 | Accesibilidad | IA |
| estados-05 | Con la agenda vacía, la pantalla inicial muestra "No hay turnos" y ninguna acción para empezar | estados-05 | 2 🟡 | Estados | IA |
| Agrupados | 4 hallazgos cosméticos: desalineaciones en pantallas secundarias, una errata, espaciado irregular en el pie de página | detalle en el anexo de cada área | 0-1 🔵 | varias | IA |

*Nota: formularios-01 lo encontraron Formularios y Estados del Sistema por separado. Se unió en un solo hallazgo, conservando la severidad más alta y toda la evidencia.*

### Qué funciona bien

- **La búsqueda de especialistas tolera erratas y sinónimos** ("cardiólogo", "cardiologia" y "corazón" devuelven lo mismo). Conviene conservar este comportamiento si se rediseña la búsqueda (evidencia: fortaleza-01).
- **El resumen previo a confirmar reúne todos los datos editables en un solo lugar**, sin obligar a volver atrás para corregir (evidencia: fortaleza-02).

### Conclusiones

1. **El producto se complica justo en el momento de mayor tensión.** Los tres hallazgos más graves (la pérdida de datos al validar, la espera sin señal al confirmar, y el contraste del botón principal) se concentran en el tramo final de la reserva, donde una persona con una urgencia médica tiene menos paciencia. El costo probable es abandono y llamadas al centro de atención, justo en el paso que el negocio necesita que sea autoservicio.
2. **Las barreras de accesibilidad se acumulan.** Contraste bajo, un elemento fuera del recorrido de teclado, y color como única señal. Para un público que llega a los 75 años, los tres se suman y afectan a mucha gente a la vez.
3. **El sistema sabe qué está pasando, pero lo comunica tarde.** Esperas sin aviso, agenda vacía sin guía, y errores agrupados lejos de su campo: en los tres casos falta información en el momento y el lugar donde la persona la necesita.

### Recomendaciones

| Conclusión | Recomendación | Prioridad |
|---|---|---|
| 1 | Conservar los datos ya ingresados ante cualquier error de validación (criterio de éxito: ningún error borra campos completados), y agregar una señal de progreso durante la confirmación, con el botón bloqueado mientras tanto | Alta |
| 2 | Llevar el contraste de las acciones principales a 4.5:1 o más en todos sus estados, e incorporar el selector de horarios al recorrido de teclado (criterio de éxito: la reserva se completa de principio a fin sin usar el ratón) | Alta |
| 3 | Mostrar los errores de validación junto a cada campo, y dar a la agenda vacía una acción clara para empezar | Media |

### Pendientes de comprobar

- **Lector de pantalla en móvil (VoiceOver):** requiere un dispositivo real. Cómo comprobarlo: activar VoiceOver (Ajustes → Accesibilidad), intentar reservar un turno, y anotar en qué paso el contenido deja de leerse. Unos 10 minutos.
- **Comportamiento con conexión inestable en la app instalada:** se comprobó en web simulando conexión lenta. Queda pendiente en un dispositivo real con datos móviles.

---

*Informe generado con el Stack de Auditoría UX de Comunidad UX/UI. 3 de las 8 áreas, según el alcance acordado al inicio.*
