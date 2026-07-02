# Alexia Design System (beta)

Kit para crear pantallas y prototipos alineados con Alexia, con ayuda de la IA.
Sirve a todo el equipo (producto, diseño, desarrollo) para adelantar ideas y validar flujos
rápido, sin partir de cero. Es un borrador vivo, no la versión final de producción.

## Qué hay aquí

| Archivo | Qué es |
|---|---|
| `kit/assets/alexia-ds.css` | La librería de estilos: colores, tipografía, componentes, espaciado |
| `kit/alexia-testing.html` | 17 vistas de Alexia ya montadas, la referencia de patrones |
| `design-system-beta.md` | Los principios y criterios de diseño (el porqué) |
| `instrucciones-ia.md` | El texto que le das a la IA para que trabaje en patrón Alexia |
| `.claude/skills/prototipar/` | La skill de Claude Code (ver "Forma 1") |

## Cómo se usa

Hay tres formas, según la herramienta que uses. Elige la tuya.

---

### Forma 1 · Claude Code (la más cómoda)

Sirve para cualquiera que use Claude Code, seas de producto, diseño o desarrollo.
No necesitas saber programar.

**Preparación (una vez):**

1. Instala Claude Code si aún no lo tienes.
2. Descarga este repositorio a tu ordenador. Dos opciones:
   - Botón verde "Code" en GitHub y "Download ZIP", luego descomprime.
   - O, si usas Git: `git clone <URL-del-repo>`
3. Abre la carpeta del repositorio en Claude Code.

**Uso (cada vez):**

Escribe:

```
/prototipar "una pantalla de comunicados con buscador y tabla de mensajes"
```

La skill te ofrece **tres caminos** (tú eliges):

1. **Con contexto sugerido (lo normal):** La skill sugiere puntos que mejoran la pantalla
   (¿para quién? ¿qué problema? ¿evidencia?). Respondes si quieres; si no, genera así mismo.

2. **Brief formal:** Escribe "con brief" o "quiero proceso" y la skill hace un mini-encuadre
   con las 3 preguntas (para quien quiere rigor de diseño).

3. **Ve directo:** Si tienes prisa, escribe "ve directo" y genera en el acto, sin preguntas.

Luego lee la librería y los patrones, y te devuelve un HTML en el estilo de Alexia. Lo abres
en el navegador y lo ves. Si aportaste contexto, guarda un resumen en `briefs/` de tu clon
(queda solo en tu ordenador).

No hay que configurar nada más: al abrir el repositorio, la skill `/prototipar` aparece sola.

---

### Forma 2 · Otra IA (ChatGPT, Gemini, etc.)

1. Descarga del repositorio estos tres archivos:
   - `kit/assets/alexia-ds.css`
   - `kit/alexia-testing.html`
   - `design-system-beta.md`
2. Abre la IA que uses y empieza una conversación.
3. Sube (adjunta) los tres archivos.
4. Copia y pega el texto de `instrucciones-ia.md`.
5. Pide la pantalla que quieras. Ejemplo:
   > "Crea una pantalla de calificaciones por alumno, con filtros por evaluación."

---

### Forma 3 · Claude web (claude.ai), para el equipo

Ideal si no usas Claude Code. Requiere plan Team o Enterprise para compartir con el equipo.

1. Entra en `claude.ai/projects` y crea un Proyecto (por ejemplo "Alexia · Prototipado").
2. En "Set project instructions", pega el texto de `instrucciones-ia.md`.
3. En "Knowledge" (el "+"), sube los tres archivos:
   `alexia-ds.css`, `alexia-testing.html`, `design-system-beta.md`.
4. Comparte el Proyecto con el equipo.
5. Cualquiera abre el Proyecto, pide una pantalla, y la IA ya responde en patrón Alexia,
   sin subir nada cada vez.

---

## Cómo pedir bien

Da qué pantalla, qué datos, qué acciones y qué estados. Cuanto más claro, mejor el resultado.
Ejemplos que funcionan:

> "Formulario de alta de usuario con validación inline y estados de error."

> "Dashboard de incidencias con tarjetas de resumen arriba y una lista debajo."

Para ajustar un resultado, pide cambios concretos:

> "Los estados en badges, no en texto. Añade una fila de filtros sobre la tabla."

## Límites

- Es un borrador para validar, no producción. La implementación viva vive en el código.
- La IA no inventa colores ni componentes. Si algo falta en el sistema, lo dirá y propondrá
  lo más cercano. Si necesitas algo que no existe, avisa para valorarlo y añadirlo.

## Mantenimiento

Si cambia un color o un componente, se actualiza `kit/assets/alexia-ds.css` en este
repositorio (y se re-sube al Proyecto de claude.ai si lo usas). Así todas las pantallas
nuevas reflejan el cambio. Este repositorio es la fuente compartida.
