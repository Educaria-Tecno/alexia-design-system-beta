# Handover: <nombre de la pantalla>

Fecha: <AAAA-MM-DD>
Prototipo: `index.html` (al lado de este archivo)

El prototipo muestra el resultado. Este documento dice cómo montarlo con los Web Components
reales. Si algo del HTML contradice este documento, manda este documento.

## 1. Componentes

| Zona de la pantalla | Componente real | Configuración |
|---|---|---|
| <zona> | `<componente>` | <propiedades que importan: variant, columns, searchable...> |

## 2. Tokens usados

Solo nombres reales. Ninguno inventado.

| Para qué | Token |
|---|---|
| <ej. fondo del aviso de éxito> | `--alert-bg-success` |

## 3. Comportamiento

- <qué pasa al tocar cada cosa>
- <estados: vacío, con datos, error>
- <qué se abre, qué se cierra, qué se guarda>

## 4. Decisiones de diseño aplicadas

- <decisión y por qué, en una línea>

## 5. Huecos

Lo que el prototipo hace y hoy NO existe como componente o icono real. Cada línea es trabajo
para desarrollo.

| Qué falta | Cómo se resolvió en el prototipo | Qué haría falta |
|---|---|---|
| <ej. icono de "Retraso"> | <SVG embebido en el HTML> | <darlo de alta en `icon-catalog.css`> |

## 6. Hacks del prototipo

Cosas que se hicieron en el HTML para que se viera bien y que el desarrollador **no** debe
copiar. Si no hay ninguna, escribe "ninguno".

- <ej. CSS inyectado en el Shadow DOM de un `button-bar`>
