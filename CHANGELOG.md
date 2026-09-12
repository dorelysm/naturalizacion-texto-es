# Changelog

## [1.2.0] — 2026-09-12

### Marcas técnicas y tipográficas de IA (Tier 5)

- Nueva sección "Tier 5 — Marcas técnicas y tipográficas de IA" en la lista negra de `SKILL.md`: (5a) caracteres invisibles y watermarking (zero-width space, variation selectors, homoglifos, advertencia sobre watermarking estadístico tipo SynthID), (5b) tipografía sospechosa visible (comillas curvas, puntos suspensivos unicarácter, NBSP atípico, en-dash mal usado)
- Paso 2 y Paso 3 actualizados para cubrir Tier 5; la garantía del Output A se generaliza de "sin guiones largos" a "sin ninguna marca Tier 5"
- Nuevo Paso 3.5 — verificación final antes de entregar, enfocado en reducir marcas residuales en textos largos
- `SUBSTITUTIONS.md`: nuevas tablas Tier 5a y 5b con códigos Unicode y sustituciones
- `always-on/CLAUDE-SNIPPET.md`: nueva sección de prevención activa ("nunca generar") para que el modo silencioso no produzca estos caracteres
- Nuevo ejemplo [`examples/ejemplo-marcas-tecnicas.md`](examples/ejemplo-marcas-tecnicas.md)

### Output B ampliado

- Nueva fila de diagnóstico cuantitativo para marcas Tier 5
- Nueva sexta dimensión de puntuación "Ausencia de marcas técnicas y tipográficas IA (Tier 5)" (/20); el total pasa de **/100 a /120** (cambio de escala explícito; las 5 dimensiones existentes mantienen su peso sin renormalizar)
- Ejemplos existentes (`ejemplo-basico.md`, `ejemplo-academico.md`) actualizados a la nueva escala

### Registro académico

- La nota de "paradoja académica" se expande con guía operativa de qué SÍ y qué NO tocar en texto académico/formal
- `ejemplo-academico.md` actualizado mostrando la guía en aplicación

### Cobertura Tier 1/2

- Tier 1: "a la hora de" + infinitivo, "no obstante" (inicio de párrafo)
- Tier 2: "robusto" (uso genérico), "panorama" (metáfora genérica)

### Referencias

- 3 nuevas entradas en `REFERENCES.md` sobre watermarking y tipografía; dos marcadas explícitamente como "PENDIENTE: verificar cita" para no atribuir fuentes inventadas

## [1.1.0] — 2026-08-03 ([2b8cd98](https://github.com/dorelysm/naturalizacion-texto-es/commit/2b8cd98))

### Modo always-on

- Nuevo `always-on/CLAUDE-SNIPPET.md`: versión condensada de las reglas de naturalización pensada para vivir en `CLAUDE.md` (global o de proyecto), aplicándose de forma continua y silenciosa a todo el texto en español, sin frases gatillo ni informe
- README: nueva sección "Modo always-on" con instalación global y por proyecto, y tabla comparativa frente al modo explícito de la skill
- Nuevo ejemplo [`examples/ejemplo-always-on.md`](examples/ejemplo-always-on.md) mostrando la salida en modo silencioso (solo Output A)
- El modo explícito (`SKILL.md`, con Output A + Output B) no cambia

## [1.0.0] — 2026-07-24

### Lanzamiento inicial

- 11 técnicas de naturalización: variación rítmica, surprisal léxico, marcadores discursivos del español, regla 70/30, prosa integrada, hedges, posicionamiento autoral, vocabulario inesperado, morfosintaxis del español, irregularidades estilísticas, coherencia tonal
- Lista negra en 4 tiers: conectores formulaicos, vocabulario predecible IA, patrones estructurales, guiones largos (—)
- Regla de guiones largos: eliminación siempre obligatoria, reemplazando por paréntesis o coma
- Output B con diagnóstico cuantitativo (TTR, % voz pasiva, % conectores Tier 1)
- Nota sobre paradoja académica
- 27 referencias documentadas en `REFERENCES.md` (papers 2023-2026, literatura gris, comunidades hispanohablantes)
