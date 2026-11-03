# Alexia Design System (beta)

Kit para crear pantallas y prototipos alineados con Alexia, con ayuda de la IA.
Sirve a todo el equipo (producto, diseño, desarrollo) para adelantar ideas y validar flujos
rápido, sin partir de cero. Es un borrador vivo, no la versión final de producción.

## Qué hay aquí

| Archivo | Qué es |
|---|---|
| `kit/assets/alexia-ds.css` | La librería de estilos: componentes y clases del kit (importa `tokens-reales.css`) |
| `kit/assets/tokens-reales.css` | Los tokens con los nombres reales del código: colores, tipografía, radios |
| `kit/mapa-wc.md` | Qué Web Component real corresponde a cada patrón de pantalla |
| `kit/handover-plantilla.md` | Plantilla del documento de entrega para desarrollo |
| `kit/alexia-testing.html` | 17 vistas de Alexia ya montadas, la referencia de patrones |
| `design-system-beta.md` | Los principios y criterios de diseño (el porqué) |
| `instrucciones-ia.md` | El texto que le das a la IA para que trabaje en patrón Alexia |
| `.claude/skills/prototipar/` | La skill de Claude Code (ver "Forma 1") |

## Cómo se usa

Hay tres formas, según la herramienta que uses. Elige la tuya.

---

### Forma 1 · Claude Code (la más cómoda)

**Instalación:**

1. Clona el repositorio en tu ordenador. En la terminal (CMD, PowerShell, o terminal de tu IDE):

```bash
git clone https://github.com/Educaria-Tecno/alexia-design-system-beta.git
cd alexia-design-system-beta
```

2. Abre la carpeta en Claude Code.

3. Listo. La skill `/prototipar` ya está disponible.

**Uso:**

Escribe en Claude Code:

```
/prototipar "una pantalla de comunicados con tabla de mensajes"
```

La skill te ofrece **tres caminos** (tú eliges):

1. **Con contexto sugerido (lo normal):** La skill sugiere puntos que mejoran la pantalla
   (¿para quién? ¿qué problema? ¿evidencia?). Respondes si quieres; si no, genera así mismo.

2. **Brief formal:** Escribe "con brief" o "quiero proceso" y la skill hace un mini-encuadre
   con las 3 preguntas (para quien quiere rigor de diseño).

3. **Ve directo:** Si tienes prisa, escribe "ve directo" y genera en el acto, sin preguntas.

La skill genera un HTML en el estilo de Alexia, con los nombres reales de tokens, y un handover (`<nombre>.handover.md`, al lado del HTML) que dice con qué Web Components reales se monta la pantalla. Abres el HTML en el navegador y lo ves; el handover es lo que le pasas a desarrollo. Si aportaste contexto, guarda un resumen en `briefs/` de tu clon (queda solo en tu ordenador).

---

### Forma 2 · Otra IA (ChatGPT, Gemini, etc.)

1. Descarga del repositorio estos seis archivos:
   - `kit/assets/alexia-ds.css`
   - `kit/assets/tokens-reales.css`
   - `kit/alexia-testing.html`
   - `kit/mapa-wc.md`
   - `kit/handover-plantilla.md`
   - `design-system-beta.md`
2. Abre la IA que uses y empieza una conversación.
3. Sube (adjunta) los seis archivos.
4. Copia y pega el texto de `instrucciones-ia.md`.
5. Pide la pantalla que quieras. Ejemplo:
   > "Crea una pantalla de calificaciones por alumno, con filtros por evaluación."

---

### Forma 3 · Claude web (claude.ai), para el equipo

Ideal si no usas Claude Code. Requiere plan Team o Enterprise para compartir con el equipo.

1. Entra en `claude.ai/projects` y crea un Proyecto (por ejemplo "Alexia · Prototipado").
2. En "Set project instructions", pega el texto de `instrucciones-ia.md`.
3. En "Knowledge" (el "+"), sube los seis archivos:
   `alexia-ds.css`, `tokens-reales.css`, `alexia-testing.html`, `mapa-wc.md`,
   `handover-plantilla.md`, `design-system-beta.md`.
4. Comparte el Proyecto con el equipo.
5. Cualquiera abre el Proyecto, pide una pantalla, y la IA ya responde en patrón Alexia,
   sin subir nada cada vez.

---

## Cómo actualizar

El kit cambia con el tiempo (por ejemplo, cuando cambian los tokens o los componentes del
código). Cada forma de uso se actualiza distinto:

- **Forma 1 (Claude Code):** en la carpeta de tu clon, ejecuta `git pull`. La skill vive dentro
  del repositorio, así que se actualiza sola. Si no clonaste (descargaste un zip), vuelve a
  descargarlo.
- **Forma 2 (otra IA):** vuelve a descargar los seis archivos y súbelos otra vez en la
  conversación. Una conversación antigua sigue con los archivos viejos.
- **Forma 3 (Claude web):** en el Proyecto, sustituye los seis archivos de "Knowledge" por
  los nuevos y vuelve a pegar `instrucciones-ia.md` en las instrucciones del Proyecto.

Un HTML que ya generaste no se actualiza: es una copia del momento en que lo creaste.

Para que los colores se vean, `alexia-ds.css` y `tokens-reales.css` tienen que estar juntos
en la misma carpeta `assets/`, al lado de tu HTML. La primera importa la segunda.

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
