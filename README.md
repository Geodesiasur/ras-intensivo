# Sistema RAS intensivo — diagrama interactivo

Diagrama del bucle de recirculación y las fronteras de calidad de agua de un
sistema de acuicultura intensiva (RAS), generado con
[Archify](https://github.com/tt-a1i/archify) y publicado como HTML autocontenido.

**Ver:** abre `index.html` (o la URL de GitHub Pages de este repositorio).

## Qué muestra

- Tren de tratamiento: estanque → filtro de tambor → biofiltro MBBR →
  torre de stripping de CO₂ → UV + bomba de calor → cono de oxígeno.
- Bucle primario de recirculación (95–99 % del caudal) y agua de reposición
  (make-up 1–5 %).
- Purga de lodos hacia tratamiento de efluentes y venteo de CO₂.
- Lazo de control e IoT: sondas de OD, pH, temperatura y amonio → PLC/Dashboard.
- Parámetros críticos: OD > 80 % sat, CO₂ < 10–15 mg/L, TAN < 1 mg/L,
  NO₂ < 0.2 mg/L, T 12–18 °C.

Los valores son referencias típicas de RAS, no mediciones de una instalación real.

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

- `index.html` — diagrama interactivo autocontenido (no requiere instalación).
- `ras-intensivo.candidate.json` — fuente editable del diagrama.
- `.nojekyll` — evita el procesado de Jekyll en GitHub Pages.

## Regenerar el diagrama

```bash
node <ruta-a-archify>/bin/archify.mjs finalize workflow \
  ras-intensivo.candidate.json index.html --quality showcase
```
