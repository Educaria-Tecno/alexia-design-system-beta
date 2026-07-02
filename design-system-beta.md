# Design System Beta

Versión experimental. Template para nuevos productos.

---

## Principios (Universal)

Estos principios valen para cualquier producto:

- **Familiaridad:** preferimos patrones conocidos. No reinventamos interfaces sin necesidad.
- **Claridad:** la interfaz debe ser fácil de compreender.
- **Consistencia:** problemas similares deben tener soluciones similares.
- **Accesibilidad:** es obligatoria, no opcional.
- **Propósito:** la diseño sirve a las personas, no a la tecnología.

---

## Estructura de datos

Cada producto define su propia estructura. Cambia los valores, mantén la lógica.

### Paleta de colores

Define:
- **Primaria:** el color principal de tu marca
- **Secundaria:** acentos y énfasis
- **Estados:** suceso (verde), error (rojo), aviso (amarillo), info (azul)
- **Neutral:** grises para fondos y bordes

Ejemplo (Alexia):
- Primaria: purple-500
- Secundaria: cyan-600
- Suceso: green-700
- Error: red-600
- Aviso: yellow-500
- Info: blue-500

### Tipografía

Define:
- **Títulos:** nombre, pesos disponibles, tamaño recomendado
- **Cuerpo:** nombre, pesos disponibles, tamaño recomendado
- **Código:** nombre, tamaño

Ejemplo (Alexia):
- Títulos: Nunito (400, 700, 800, 900) → 18px–104px
- Cuerpo: Roboto (400, 500, 700) → 14px–22px
- Código: JetBrains Mono (400) → 12px–16px

### Componentes esenciales

Documenta los componentes que tu producto necesita:
- **Botones:** tipos (primario, secundario, peligro), estados (normal, hover, activo, deshabilitado)
- **Formularios:** inputs, labels, validación, ayuda de texto
- **Alertas:** suceso, error, aviso, info (color, icono, texto)
- **Cards:** estructura, espaciado, sombras
- **Navegación:** menús, tabs, breadcrumbs
- [Añade los que falten]

Ejemplo (Alexia):
- 4 tipos de botones (primario, secundario, terciario, peligro)
- 4 estados de alerta (suceso, error, aviso, info)
- Formularios con validación inline
- Cards con sombra baja

### Espaciado

Define:
- **Unidad base:** 4px o 8px (elige una)
- **Escala:** xxs (4px), xs (8px), sm (12px), md (16px), lg (24px), xl (32px), xxl (48px)

Ejemplo (Alexia):
- Unidad base: 4px
- Escala: 4, 8, 12, 16, 24, 32, 48, 64 px

---

## Cómo adaptar para tu producto

1. **Copia este archivo** a la carpeta raíz de tu proyecto
2. **Reemplaza Paleta de colores** con los colores de tu marca
3. **Reemplaza Tipografía** con las fuentes que usas
4. **Reemplaza Componentes esenciales** con lo que tu producto necesita
5. **Define Espaciado** basado en tu unidad base

Listo. Ahora tienes tu Design System.

---

## Ejemplos reales

### Alexia (nuevo)

**Paleta:** purple-500 (primaria), cyan-600 (secundaria), green-700 (suceso), red-600 (error), yellow-500 (aviso), blue-500 (info)

**Tipografía:** Nunito (títulos), Roboto (cuerpo), JetBrains Mono (código)

**Componentes:** 4 tipos de botón, 4 estados de alerta, formularios con validación, cards

**Espaciado:** base 4px, escala 4, 8, 12, 16, 24, 32, 48, 64

### App de Familias (Maria)

**Paleta:** [tu color primario], [tu color secundario], [tus estados]

**Tipografía:** [las fuentes que uses]

**Componentes:** [lo que tu app necesite]

**Espaciado:** [tu unidad base]

### Alexia (legado, Pablo)

**Paleta:** [colores actuales]

**Tipografía:** [tipografía actual]

**Componentes:** [componentes existentes]

**Espaciado:** [escala actual]

---

## Cómo prototipar con IA (caso Alexia)

Este documento (los criterios) es una de tres piezas que trabajan juntas. Con las tres en
el contexto de una IA, se generan pantallas alineadas con Alexia en minutos:

| Pieza | Qué aporta |
|---|---|
| `alexia-ds.css` | los componentes reales (colores, tipografía, clases) |
| `alexia-testing.html` | 17 vistas montadas, referencia de patrones |
| `design-system-beta.md` (este archivo) | los principios y criterios, el porqué |

**Mecanismo (importante):** documentar los criterios aquí no basta por sí solo. Una IA solo
usa el CSS y el HTML cuando los tiene **en su contexto**. Por eso las tres piezas se suben al
conocimiento de un Proyecto compartido en Claude, y las instrucciones del proyecto le dicen a
la IA cómo usarlas. A partir de ahí, pedir una pantalla es directo y el resultado ya sale en
patrón Alexia, sin repetir contexto en cada conversación.

Cómo usar el kit (en Claude Code, en otra IA o en Claude web) está explicado en el
`README.md`. El texto que se le da a la IA está en `instrucciones-ia.md`.

## Próximos pasos

- [ ] Define tu paleta de colores
- [ ] Define tu tipografía
- [ ] Lista tus componentes esenciales
- [ ] Documenta tu espaciado
- [ ] Comparte con tu equipo
- [ ] Itera basado en feedback

---

## Preguntas frecuentes

**¿Por qué tan simple?**  
Porque simple = reutilizable. Si es claro, otros productos pueden copiar y adaptar en minutos.

**¿Debo tener todos los componentes?**  
No. Empieza con los esenciales. Añade más conforme tu producto lo necesite.

**¿Puedo cambiar los principios?**  
Los principios (familiaridad, claridad, etc) son universales. Los datos (colores, tipografía) son tuyos.

**¿Quién mantiene esto?**  
Tu equipo de diseño. Actualiza cuando cambies decisiones o añadas componentes.
