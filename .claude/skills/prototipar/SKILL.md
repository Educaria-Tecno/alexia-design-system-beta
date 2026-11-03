---
name: prototipar
description: Crea pantallas y componentes de Alexia en HTML usando el design system, con los nombres reales de tokens, y entrega un handover para desarrollo. Úsala cuando pidas prototipar, maquetar o generar una pantalla, vista, formulario o componente de Alexia.
---

# Prototipar una pantalla de Alexia

Genera HTML alineado con el design system de Alexia. Tú eliges cuánto contexto le das.

El prototipo es rápido y libre. Lo que lo hace útil para desarrollo es el **handover** que sale
junto a él: dice con qué Web Components reales se monta la pantalla.

**IMPORTANTE:** Todo (bienvenida, preguntas, resúmenes, respuestas) **siempre en español de España**.

## Paso 1 · Bienvenida y opciones

Saluda en 1-2 líneas. Explica que hay **tres caminos**:

1. **Con contexto sugerido (lo normal):** Sugierele puntos que mejoran el resultado:
   - ¿Para quién es? ¿Qué problema resuelve?
   - ¿Qué te hace pensar que es real? (un dato, una queja, un palpite)
   - ¿Cómo sabrás si funciona?
   
   Pero **sin obligar**: "responde si quieres, pero no es necesario". Si no responde nada,
   genera así mismo. Si responde algo (poco o mucho), úsalo para mejorar.

2. **Brief formal:** Si escribe algo tipo "con brief" o "quiero proceso", haz las 3 preguntas
   de arriba como un mini-encuadre formal (para quien quiere rigor de diseño).

3. **Rápido (ve directo):** Si escribe "ve directo" o "rápido", sáltate todo y genera ya.

**La sugerencia es lo default**: no preguntes formalmente, solo sugiere. Deja que el usuario
decida cuánto contexto da.

## Paso 2 · Recoger contexto (si el usuario responde)

Si el usuario responde a la sugerencia (aunque sea parcialmente: "para alumnos" o "un
dashboard"), recógelo. Si no responde nada y escribe solo la pantalla, usa eso directamente.

**Nota:** Si detectas que el usuario pidió explícitamente "con brief" o "proceso", salta a un
encuadre formal (las 3 preguntas como mini-formulario).

## Paso 3 · Leer el kit (siempre, antes de generar)

Lee estos archivos del repositorio para no inventar nada:

1. `kit/assets/tokens-reales.css`: los tokens con los **nombres reales** del código (colores,
   tipografía, radios).
2. `kit/mapa-wc.md`: qué Web Component real corresponde a cada patrón de pantalla, y las
   reglas verificadas (orden de botones, iconos, Shadow DOM).
3. `kit/assets/alexia-ds.css`: la librería de estilos (clases y componentes del kit).
4. `kit/alexia-testing.html`: 17 vistas ya montadas, referencia de patrones.
5. `design-system-beta.md`: los principios y criterios de diseño.

## Paso 4 · Generar el HTML

El resultado debe cumplir:

1. **HTML autocontenido** que enlace:
   `<link rel="stylesheet" href="assets/alexia-ds.css">`
   (esa hoja ya importa `tokens-reales.css`)
   y las fuentes Nunito (títulos) y Roboto (texto) desde Google Fonts.
2. **Solo lo que ya existe**: usa clases y componentes de `alexia-ds.css`, imita patrones de
   `alexia-testing.html`. Nunca inventes.
3. **Variables con nombre real**: colores con `--color-*`, `--rf-*` o `--alert-*`; tipografía
   con `--font-*`. En pantallas nuevas no uses los nombres cortos del kit (`--blue-500`,
   `--grey-300`) ni hex sueltos, y no inventes un paso de una escala.
4. **Piensa cada bloque como su componente real** (ver `kit/mapa-wc.md`): panel lateral,
   lista, barra de botones, formulario. Que la estructura y los nombres sean reconocibles
   para quien lo monte con los Web Components.
5. **Botones: la acción principal a la izquierda**, la secundaria a su derecha.
6. **Iconos: solo los que existan en el catálogo.** Si necesitas uno que no existe, dilo y
   anótalo como hueco en el handover; no lo des por hecho.
7. **Si falta algo**: dilo y propón la alternativa más cercana.
8. **Accesibilidad**: contraste, foco visible, etiquetas; color nunca es el único canal.
9. **Textos en español de España**, claros.

## Paso 5 · Handover (siempre, también con "ve directo")

Genera el handover con la plantilla `kit/handover-plantilla.md`. Guárdalo en la misma
carpeta que el HTML, con el mismo nombre y la terminación `.handover.md`
(por ejemplo `comunicados.html` y `comunicados.handover.md`).

Con "ve directo" puede ser corto, pero lleva como mínimo: componentes (sección 1), tokens
usados (sección 2) y huecos (sección 5). Con contexto o brief, completa todas las secciones.

Reglas del handover:
- Solo nombres reales de componente y de token. Si no estás seguro de un nombre, mira
  `kit/mapa-wc.md` o `kit/assets/tokens-reales.css`; si no está ahí, no lo escribas.
- En "Huecos" lista lo que el prototipo hace y hoy no existe como componente o icono real.
- En "Hacks" lista lo que se hizo solo para que el HTML se vea bien y el desarrollador no
  debe copiar.

## Paso 6 · Cerrar con resumen (solo si hubo contexto)

Si el usuario aportó contexto (o pidió "con brief"), cierra con un resumen corto:

```
Resumen:
· Para: ...
· Problema / evidencia: ...
· Éxito: ...
```

Si usó "ve directo", no hay resumen; solo la pantalla y el handover.

## Paso 7 · Guardar (automático, si hubo contexto)

Si hubo contexto, guárdalo automáticamente en `briefs/` (créala si no existe).
Nombre: `briefs/AAAA-MM-tema-corto.md`
Contenido: el resumen + la fecha + la pantalla pedida.

La carpeta `briefs/` está en `.gitignore`: registro personal, no sube al repo.
Si usó "ve directo", no hay archivo de brief que guardar.

---

El resultado es un borrador rápido para validar ideas, más el handover que lo conecta con los
componentes reales. Cuanto más contexto, mejor; pero sin presión.
