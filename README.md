# Diagramas RAS — acuicultura de recirculación

Colección de diagramas explicativos interactivos sobre sistemas de recirculación
en acuicultura (RAS), generados con [Archify](https://github.com/tt-a1i/archify)
y publicados como HTML autocontenido (un solo archivo, sin dependencias).

**Sitio publicado:** https://geodesiasur.github.io/ras-intensivo/

## Diagramas

| # | Diagrama | Página | Fuente |
|---|---|---|---|
| 1 | Sistema RAS intensivo · bucle de recirculación y calidad de agua | [`/`](https://geodesiasur.github.io/ras-intensivo/) | `ras-intensivo.candidate.json` |
| 2 | Cálculo RAS (V2.0) · cómo la app convierte tus datos en un dictamen hidráulico | [`/ras-v2/`](https://geodesiasur.github.io/ras-intensivo/ras-v2/) | `ras-v2/calculo-ras-v2.candidate.json` |

---

## 1 · Sistema RAS intensivo

Diagrama del bucle de recirculación y las fronteras de calidad de agua de un
sistema de acuicultura intensiva.

- Tren de tratamiento: estanque → filtro de tambor → biofiltro MBBR →
  torre de stripping de CO₂ → UV + bomba de calor → cono de oxígeno.
- Bucle primario de recirculación (95–99 % del caudal) y agua de reposición
  (make-up 1–5 %).
- Purga de lodos hacia tratamiento de efluentes y venteo de CO₂.
- Lazo de control e IoT: sondas de OD, pH, temperatura y amonio → PLC/Dashboard.
- Parámetros críticos: OD > 80 % sat, CO₂ < 10–15 mg/L, TAN < 1 mg/L,
  NO₂ < 0.2 mg/L, T 12–18 °C.

Los valores son referencias típicas de RAS, no mediciones de una instalación real.

## 2 · Cálculo RAS (V2.0)

Diagrama de la aplicación de dimensionamiento
[Cálculo RAS (V2.0)](https://calculo-ras-v2-0.ai.studio/), del
Ing. en Acuicultura José Ernesto Muñoz Núñez.

- Una fila por pestaña de la app (5 pasos + Esquema & Flujo).
- Tres columnas: **tú escribes** → **la app calcula** → **la app entrega**.
- Cascada central: biomasa → TAN → biofiltro → sólidos → oxígeno → caudal
  gobernante.
- Los tres caudales que compiten: TAN 3.252 L/min, SST 2.460 L/min,
  O₂ 7.727 L/min; gana el mayor (463,6 m³/h · 2,31 rev/h).
- Entregables: agua nueva (31.637 L/d · 15,8 %/día) y reporte técnico.

Cifras del escenario guía **Salmón Engorda Estándar** incluido en la app, no
mediciones de una instalación real.

---

## Uso del visor

| Tecla | Acción |
|---|---|
| `S` | cambia el estilo visual |
| `T` | tema claro / oscuro |
| `E` | exportar (PNG, WebP, PDF) |
| `F` | modo presentación |
| `R` | trazar una ruta entre dos nodos |
| `/` | buscar y enfocar un nodo |
| `+` `-` `0` | zoom y reinicio |

## Archivos

- `index.html` — diagrama 1, autocontenido.
- `ras-intensivo.candidate.json` — fuente editable del diagrama 1.
- `ras-v2/index.html` — diagrama 2, autocontenido.
- `ras-v2/calculo-ras-v2.candidate.json` — fuente editable del diagrama 2.
- `.nojekyll` — evita el procesado de Jekyll en GitHub Pages.

## Regenerar un diagrama

```bash
node <ruta-a-archify>/bin/archify.mjs finalize workflow \
  <candidate.json> <index.html> --quality showcase
```
