# Mapa: patrón de pantalla → Web Component real

Para qué sirve: cuando prototipas rápido con este kit, el desarrollador no va a copiar tu
HTML. Va a montar la pantalla con los Web Components reales. Este mapa dice qué componente
usaría para cada patrón, para que el prototipo y el handover hablen de lo mismo.

Cada fila se verificó leyendo el código de los componentes (carpeta
`Desarrollo/javascript/common/web-component/`). El detalle de propiedades de cada uno está en
las skills del TFS: `Desarrollo/.agents/skills/web-components/` (`base/` y `widgets/`).

Si un patrón no está en esta tabla: mira esas skills. Si tampoco existe allí, no lo inventes,
anótalo como **hueco** en el handover.

## Patrones

| Patrón en el prototipo | Web Component real | Lo que hay que decir en el handover |
|---|---|---|
| Panel lateral con cabecera, acciones, cuerpo y pie | `right-sidebar` | Título y subtítulo del header, botones de `actions`, contenido del cuerpo, botones del `footer`. |
| Lista de filas (alumnos, mensajes) con foto, título y subtítulo | `tree-list` | Campos de cada nodo (`id`, `title`, `subtitle`, `image`, `buttons`, `content`), si lleva `searchable` y `multiselect`. |
| Fila que se despliega con detalle | `tree-list` con `content` en el nodo y `accordion` si solo se abre una a la vez | Qué muestra el desplegable. |
| Grupo de botones con menú "..." cuando no caben | `button-bar` | Lista de botones, `align`, y que el "..." lo decide el propio componente por ancho. |
| Botón | `wc-button` | `variant`, `size`, `shape`, y si es `text-out` (icono arriba, label abajo). |
| Aviso (éxito, error, info, aviso) | `wc-banner` | `type` (`info`, `warning`, `error`, `success`, `news`) y el `message`. |
| Formulario | `dynamic-form` | Esquema: secciones, campos, `columns` de cada uno (rejilla de 12). |
| Sección con título y línea | `content-section` | Si lleva `headerDivider`, `collapsable`, `borderless`. |
| Campo de texto, número, área, casilla, fecha | `wc-input`, `wc-textarea`, `wc-checkbox`, `wc-datepicker` | Etiqueta, valor por defecto, validaciones. |
| Insignia de estado | `wc-status` | Texto y estado. |
| Icono | `wc-icon` | Nombre del icono **del catálogo** (`icon-catalog.css`). |

Lo que NO tiene componente: la barra superior y el menú de navegación de la app (el "shell"
del kit). Eso se entrega como referencia visual, no como especificación de componente.

## Reglas que salen de la práctica (verificadas)

- **El orden de un grupo de botones es el orden del array.** La acción principal va primero
  (a la izquierda), la secundaria después.
- **Iconos: solo los del catálogo.** Un botón toma su icono de una clase de `icon-catalog.css`.
  Si el icono que necesitas no está en el catálogo, no lo dibujes en el prototipo como si
  existiera: apúntalo como hueco (hace falta darlo de alta).
- **Los botones de `button-bar` viven en su propio Shadow DOM.** Un CSS de la página no les
  llega. En un prototipo, si necesitas retocarlos, es un hack: márcalo en el handover.
- **`wc-button` con `text-out` mide 74px de ancho fijo.** Un label largo se corta con
  puntos suspensivos.
- **`tree-list`: cambiar un nodo con `updateNode` rehace la fila entera.** Si el prototipo
  depende de un estado dentro de la fila, el desarrollador tiene que tenerlo en cuenta.
- **`right-sidebar`: cada `refreshHeader()` borra los botones extra que se hubieran añadido a
  mano al header.**

## Colores y tipografía

Usa siempre los nombres reales de `assets/tokens-reales.css`: `--color-blue-500`,
`--rf-color-primary`, `--alert-bg-success`, `--font-size-label`, `--font-family-ui`...
No pongas hex sueltos ni inventes un paso de la escala. Los nombres cortos del kit
(`--blue-500`, `--grey-300`...) existen solo para las vistas ya montadas.
