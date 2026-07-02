---
name: prototipar
description: Crea pantallas y componentes de Alexia en HTML usando el design system. Úsala cuando pidas prototipar, maquetar o generar una pantalla, vista, formulario o componente de Alexia.
---

# Prototipar una pantalla de Alexia

Genera HTML alineado con el design system de Alexia. Tú eliges cuánto contexto le das.

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

1. `kit/assets/alexia-ds.css` — la librería de estilos (colores, tipografía, componentes,
   espaciado).
2. `kit/alexia-testing.html` — 17 vistas ya montadas, referencia de patrones.
3. `design-system-beta.md` — los principios y criterios de diseño.

## Paso 4 · Generar el HTML

El resultado debe cumplir:

1. **HTML autocontenido** que enlace:
   `<link rel="stylesheet" href="assets/alexia-ds.css">`
   y las fuentes Nunito (títulos) y Roboto (texto) desde Google Fonts.
2. **Solo lo que ya existe**: usa clases y componentes de `alexia-ds.css`, imita patrones de
   `alexia-testing.html`. Nunca inventes. No uses hex sueltos.
3. **Si falta algo**: dilo y propón la alternativa más cercana.
4. **Accesibilidad**: contraste, foco visible, etiquetas; color nunca es el único canal.
5. **Textos en español de España**, claros.

## Paso 5 · Cerrar con resumen (solo si hubo contexto)

Si el usuario aportó contexto (o pidió "con brief"), cierra con un resumen corto:

```
Resumen:
· Para: ...
· Problema / evidencia: ...
· Éxito: ...
```

Si usó "ve directo", no hay resumen; solo la pantalla.

## Paso 6 · Guardar (automático, si hubo contexto)

Si hubo contexto, guárdalo automáticamente en `briefs/` (créala si no existe).
Nombre: `briefs/AAAA-MM-tema-corto.md`
Contenido: el resumen + la fecha + la pantalla pedida.

La carpeta `briefs/` está en `.gitignore`: registro personal, no sube al repo.
Si usó "ve directo", no hay archivo que guardar.

---

El resultado es un borrador rápido para validar ideas. Cuanto más contexto, mejor; pero sin
presión.
