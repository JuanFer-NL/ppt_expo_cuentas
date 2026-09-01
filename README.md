# Pobreza — Enfoques y Métodos

[![Tests](https://github.com/JuanFer-NL/ppt_expo_cuentas/actions/workflows/test.yml/badge.svg)](https://github.com/JuanFer-NL/ppt_expo_cuentas/actions/workflows/test.yml)
[![Spellcheck](https://github.com/JuanFer-NL/ppt_expo_cuentas/actions/workflows/spellcheck.yml/badge.svg)](https://github.com/JuanFer-NL/ppt_expo_cuentas/actions/workflows/spellcheck.yml)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-live-2ea44f?logo=githubpages&logoColor=white)](https://juanfer-nl.github.io/ppt_expo_cuentas/)
[![License: MIT](https://img.shields.io/badge/framework-MIT-blue.svg)](LICENSE)
[![License: CC BY 4.0](https://img.shields.io/badge/contenido-CC%20BY%204.0-lightgrey.svg)](LICENSE-CONTENT)

Presentación del **Grupo 13** para **Expo Cuentas 2026**, sobre los enfoques objetivo y subjetivo de medición de la pobreza.

🔗 **Ver la presentación en vivo:** https://juanfer-nl.github.io/ppt_expo_cuentas/

---

## ⚠️ Nota sobre este repositorio

Este repo contiene el **código fuente completo del framework [reveal.js](https://revealjs.com)** (vendorizado, no como dependencia npm) más el contenido propio de la presentación. Es decir: la gran mayoría de los archivos (`js/`, `css/`, `plugin/`, `react/`, `test/`, `examples/`, `.github/workflows/`, `scripts/`) **no fueron escritos por el grupo** — son el framework en sí. El contenido propio del proyecto se reduce a:

| Archivo | Rol |
|---|---|
| `index.html` | La presentación en sí (968 líneas, todas las diapositivas) |
| `espacio3d.html` | Visualización 3D embebida como `<iframe>` dentro de una diapositiva |
| `barrascuenta.png`, `graficogeneral1.png`, `Figure_1.png` | Gráficos usados en las diapositivas |

Si vas a modificar la presentación, editá **solo esos archivos**. El resto es infraestructura de reveal.js que se mantiene para poder compilar/servir localmente.

---

## Contenido de la presentación

`index.html` recorre, diapositiva por diapositiva:

1. **Estructura de la presentación** — índice.
2. **¿Qué es la pobreza?** — premisa del estudio.
3. **Método objetivo**
   - Línea de Pobreza (LP) y Canasta Básica Alimentaria (CBA).
   - Limitaciones del método objetivo.
4. **Pobreza subjetiva**
   - Origen: Escuela de Leyden.
   - Métodos de medición subjetiva.
   - Casos aplicados en Latinoamérica.
5. **Construcción de la línea de pobreza subjetiva**
   - La Pregunta de Ingreso Mínimo (MIQ, *Minimum Income Question*) y el sesgo de ingresos.
   - Regresión lineal multivariable (MCO) para estimar la función de Leyden.
   - Cálculo del umbral de pobreza subjetiva.
6. **Pros y contras** de ambos métodos (objetivo vs. subjetivo), en formato comparativo de dos columnas.
7. **Prueba piloto**
   - Diseño de la encuesta MIQ aplicada por el grupo.
   - Resultados — estimación general (`graficogeneral1.png`).
   - **Espacio 3D** — distribución de respuestas, embebido vía `<iframe src="espacio3d.html">` (sección 7.3, línea 813).
   - Gráfico de barras de cuenta (`barrascuenta.png`).
8. **Conclusiones** — qué significa el resultado obtenido.
9. **Bibliografía** — 8 referencias académicas (Van Praag & Kapteyn, Goedhart et al., Kapteyn, Aguado & Osorio, Lucchetti, Giarrizzo, Scalese), todas sobre la Escuela de Leyden y pobreza subjetiva en Latinoamérica.
10. Diapositiva final de agradecimiento.

No se usan plugins de reveal.js en esta presentación (`plugins: []` en la configuración de `Reveal.initialize`, línea 950): no hay Markdown, math, highlight ni notas de orador activados.

## `espacio3d.html`

Visualización 3D independiente y autocontenida (1900 líneas) que se carga como `<iframe>` dentro de `index.html`. Muestra la distribución de las respuestas de la prueba piloto en un espacio de tres dimensiones. Al ser un archivo aparte, también se puede abrir directamente en el navegador para explorarlo fuera de la presentación.

## Tecnología

- **Framework:** [reveal.js](https://revealjs.com) v6, framework de presentaciones HTML de código abierto.
- **Build:** Vite + TypeScript (`vite.config.ts`, `tsconfig.json`) para compilar `js/`, `css/` (SCSS) y los plugins a `dist/`.
- **CI:** `.github/workflows/test.yml` (tests de reveal.js) y `spellcheck.yml` (corrector ortográfico vía `.codespellrc`) — heredados del framework, corren sobre todo el repo.

## Uso local

```bash
npm install
npm run dev      # servidor de desarrollo (vite), sirve index.html en modo watch
npm run build    # build de producción → dist/
```

Para editar la presentación, alcanza con abrir `index.html` en un navegador (no requiere build), aunque `npm run dev` da recarga en caliente.

## Estructura completa del repositorio

```
index.html              ← la presentación (contenido del grupo)
espacio3d.html           ← visualización 3D embebida (contenido del grupo)
barrascuenta.png, graficogeneral1.png, Figure_1.png  ← imágenes usadas (contenido del grupo)
demo.html                ← demo de referencia de reveal.js, no forma parte del contenido expuesto
js/, css/, plugin/       ← código fuente del framework reveal.js
react/                   ← wrapper de React para reveal.js (no usado por esta presentación)
test/, examples/         ← suite de tests y ejemplos del framework
scripts/                 ← scripts de build del framework (zip, banner, es5, etc.)
.github/workflows/       ← CI heredado del framework (tests, spellcheck)
dist/, build/            ← artefactos de build (generados, no versionar cambios manuales)
```

## Licencia

Licenciamiento dual:

- El **contenido propio del grupo** (`index.html`, `espacio3d.html`, `barrascuenta.png`, `graficogeneral1.png`, `Figure_1.png`) está licenciado bajo **CC BY 4.0** — ver [LICENSE-CONTENT](LICENSE-CONTENT).
- El **framework reveal.js** (todo lo demás: `js/`, `css/`, `plugin/`, `react/`, etc.) está licenciado bajo **MIT** — ver [LICENSE](LICENSE).
