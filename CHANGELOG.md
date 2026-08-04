# Changelog

## [1.1.0] — 2026-08-03

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
