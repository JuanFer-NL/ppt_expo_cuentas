# Pobreza — Enfoques y Métodos

Presentación del Grupo 13 para **Expo Cuentas 2026**, sobre los enfoques objetivo y subjetivo de medición de la pobreza.

🔗 **Ver la presentación en vivo:** https://juanfer-nl.github.io/ppt_expo_cuentas/

## Contenido

La presentación recorre:

- ¿Qué es la pobreza? Premisa del estudio.
- **Método objetivo:** Línea de Pobreza, Canasta Básica Alimentaria y sus limitaciones.
- **Método subjetivo:** origen en la Escuela de Leyden, métodos de medición y casos aplicados en Latinoamérica.
- Construcción de la línea de pobreza subjetiva: la Pregunta de Ingreso Mínimo (MIQ), el sesgo de ingresos y la regresión lineal multivariable (MCO) para hallar el umbral de pobreza subjetiva.
- Comparación de pros y contras entre ambos métodos.
- Prueba piloto: diseño de encuesta MIQ y resultados, incluyendo una visualización 3D de la distribución de respuestas (`espacio3d.html`).
- Conclusiones y bibliografía.

## Tecnología

Construida sobre [reveal.js](https://revealjs.com), el framework de presentaciones HTML de código abierto.

- `index.html` — presentación principal.
- `demo.html` — demo de referencia de reveal.js (no forma parte del contenido expuesto).
- `espacio3d.html` — visualización 3D interactiva de resultados de la encuesta.
- `plugin/`, `css/`, `js/` — código fuente del framework reveal.js.

## Uso local

```bash
npm install
npm run dev      # levanta un servidor de desarrollo
npm run build    # genera la build de producción en dist/
```

## Licencia

El contenido de la presentación pertenece al Grupo 13. El framework reveal.js está licenciado bajo MIT — ver [LICENSE](LICENSE).
