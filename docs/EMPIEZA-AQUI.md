# Empieza aquí

Primero eliges **dónde** instalarlo (tres opciones), y después arrancas con uno de los **tres ejemplos** listos para copiar.

*Versión 2.0 del stack.*

---

## Primero: ¿dónde lo vas a usar?

### Opción A: Instalarlas en claude.ai (recomendado)

En claude.ai las skills se instalan **de a una, en formato zip**. Por eso cada skill tiene su zip en [Releases](https://github.com/ComunidadUXUI/auditoria-ux-con-ia/releases/latest).

1. Entra a **Personalizar → Skills**, toca **+** y elige **Subir una skill**. Paso a paso con capturas: [guía en Notion](NOTION_LINK).
2. Sube **un zip de Releases**, el de la skill que quieras.
3. Repite con las demás. No hace falta subir las 10: cada una funciona sola.

⚠️ **Un zip = una skill.** Si comprimes la carpeta entera te va a rechazar el archivo, porque contiene 10 `SKILL.md` y la subida espera exactamente uno. Los zips de Releases ya vienen armados así, con su `SKILL.md` y sus reglas adentro.

💡 ¿Cuáles subir primero? `audit-ux-0-contexto-y-acceso` (arranca cualquier auditoría) y `audit-ux-9-sintesis-y-reporte` (arma el informe). Entre medio, las áreas que te interesen.

### Opción B: Instalarlas en Claude Code

Dos comandos dentro de Claude Code (el primero solo la primera vez):

```
/plugin marketplace add ComunidadUXUI/auditoria-ux-con-ia
/plugin install auditoria-ux@auditoria-ux-con-ia
```

Cuando termine, **abre una conversación nueva** y escribe `/skills` para confirmar que aparecen en la lista. Desde ahí se activan solas cuando pides una auditoría, o puedes invocar una con `/audit-ux-2-accesibilidad`, por ejemplo.

Aquí el stack rinde al máximo, porque la IA puede navegar la web directamente, guardar las capturas y medir el contraste sobre el código.

### Opción C: Adjuntarlas en una conversación suelta

Si prefieres no instalar nada: abre una conversación nueva, adjunta el `SKILL.md` de la skill **y los `referencia-*.md` que están en su misma carpeta**, y debajo escribe qué quieres auditar.

💡 **Para usarlo seguido**: crea un Proyecto en claude.ai y sube la carpeta `skills/` de este repositorio a su base de conocimiento. Así cualquier conversación del proyecto tiene el stack disponible sin adjuntar nada.

---

## Escenario 1: Un diagnóstico puntual (15-30 min)

Un área, un producto, directo al grano. Este ejemplo usa accesibilidad:

> *[adjunta `audit-ux-2-accesibilidad/SKILL.md` y sus reglas]*
>
> Audita la accesibilidad de https://mi-sitio.com. Concéntrate en el registro de usuarios. Tengo 30 minutos.

La skill hace dos o tres preguntas de contexto, recorre el producto como lo haría una persona común, y te entrega la lista de problemas con sus capturas y su prioridad.

Funciona igual con cualquier área: formularios (`audit-ux-7`), contenido (`audit-ux-3`), navegación (`audit-ux-5`)…

---

## Escenario 2: La auditoría completa (2-4 horas, según el alcance)

El stack entero, en orden, en una misma conversación:

> Quiero auditar mi producto con el stack completo. Es https://mi-producto.com, una aplicación web de [descripción en una línea]. Empecemos por el contexto.

El recorrido:

1. **Skill 0** te pregunta: qué producto es, quién lo usa, cómo va a trabajar la IA, hasta dónde puede operar (¿hay entorno de prueba? ¿puede crear cuentas?), cuánto tiempo tienes y qué áreas quieres revisar.
2. **Recorrido inicial**: la IA usa el producto como lo haría cualquier persona, sin analizar todavía, y anota la primera impresión.
3. **Las áreas que elegiste**, una por una, cada una con su lista de problemas.
4. **Skill 9**: comprueba que cada problema tenga su captura, une los repetidos, y arma el informe final.

💡 Si tienes poco tiempo, la skill 0 te va a recomendar concentrarte en el flujo más importante en lugar de revisar todo por encima. Hazle caso.

---

## Escenario 3: Cuando la IA no puede entrar al producto

Habitual con apps móviles y sistemas internos:

> Quiero auditar mi app de [descripción]. Yo navego y te comparto capturas de cada pantalla.

La IA te va a pedir las capturas o grabaciones de cada flujo, hace la auditoría sobre ese material, y cada problema queda etiquetado según quién lo comprobó. Lo que no se pueda verificar se anota como pendiente, con instrucciones para que lo revises tú.

---

## Preguntas frecuentes

**¿Necesito las 10 skills siempre?**
No. Cada una funciona sola. El stack completo es para auditorías formales; una skill suelta resuelve un diagnóstico puntual.

**¿Sirve para auditar el producto de un cliente?**
Sí, es su mejor uso. Acuerda los límites con tu cliente antes de empezar (la skill 0 te guía), y el informe final sale listo para presentar.

**¿La IA puede romper algo en mi producto?**
El stack lleva la regla incorporada: cualquier acción con consecuencias reales (pagos, publicaciones, envíos, borrados) espera tu confirmación explícita. Aun así, si tienes un entorno de prueba, úsalo: la skill 0 te lo va a preguntar.

**¿Qué hago con el informe?**
Es un archivo de texto con formato markdown: pégalo en Notion, expórtalo a PDF, o pídele a la IA que lo convierta en presentación. Ya incluye una sección que explica cómo leerlo, así que tu cliente no necesita contexto adicional.

**¿Puedo modificar las skills?**
Claro. Son archivos de texto: ajusta los puntos de revisión, agrega áreas, cambia la escala. Si mejoras algo, compártelo en [Comunidad UX/UI](https://www.skool.com/comunidaduxui/about) 💜
