# naturalizacion-texto-es

![Idioma](https://img.shields.io/badge/idioma-Español-blue)
![Claude Code](https://img.shields.io/badge/Claude_Code-skill-orange)
![Licencia](https://img.shields.io/badge/licencia-MIT-green)

Skill para [Claude Code](https://claude.ai/code) que transforma texto en español generado por IA en texto natural, fluido y auténtico. A diferencia de las herramientas de "humanización", **el objetivo no es evadir detectores de IA**, sino mejorar la calidad editorial real del texto para lectores humanos.

---

## Instalación

**1.** Clona o descarga este repositorio:

```bash
git clone https://github.com/dorelysm/naturalizacion-texto-es.git
```

**2.** Copia la carpeta de la skill a tu directorio global de Claude Code:

```
# La estructura debe quedar así:
~/.claude/skills/naturalizacion-texto-ia/
├── .claude-plugin/
│   └── plugin.json
└── skills/
    └── naturalizacion-texto-ia/
        ├── SKILL.md
        └── REFERENCES.md
```

Copia el contenido de `.claude/skills/naturalizacion-texto-ia/` al directorio anterior y añade el archivo `.claude-plugin/plugin.json` con este contenido:

```json
{
  "name": "naturalizacion-texto-ia",
  "description": "Naturaliza texto en español generado por IA para mejorar su calidad editorial.",
  "version": "1.0.0",
  "author": { "name": "Dorelys Martinez" }
}
```

**3.** Reinicia Claude Code. La skill aparecerá disponible en la lista de skills.

---

## Uso

Invoca la skill desde cualquier proyecto con:

```
/naturalizacion-texto-ia
```

Luego pega el texto directamente en el chat o indica la ruta de un archivo `.txt`, `.md` o `.docx`. La skill también se activa automáticamente cuando escribes palabras como *naturalizar*, *humanizar*, *quitar el estilo IA* o *suena a ChatGPT*.

### Ejemplo rápido

**Entrada (texto IA):**
> Es importante destacar que el trabajo remoto ofrece múltiples beneficios. Además, permite una mayor flexibilidad en los horarios —lo que contribuye al bienestar. En conclusión, es fundamental optimizar los procesos de comunicación.

**Salida (texto naturalizado):**
> El trabajo remoto tiene ventajas que ya no sorprenden a nadie. Y tiene sentido: la flexibilidad de horarios incide directamente en el bienestar de quien trabaja. A fin de cuentas, lo que marca la diferencia no es la tecnología, sino cómo se comunican los equipos.

Ver el [ejemplo completo con informe](examples/ejemplo-basico.md).

---

## Modo always-on

El modo explícito de arriba requiere que pidas "naturalizar" un texto puntual y siempre entrega un informe (Output A + Output B). El **modo always-on** es distinto: hace que Claude naturalice automáticamente *todo* el texto en español que escribe (respuestas, documentos, emails), sin que tengas que pedirlo y sin mostrar ningún informe — de forma silenciosa, como escribiría una persona.

No es una skill que Claude decida invocar: es un bloque de instrucciones que vive en tu `CLAUDE.md`, así que se carga siempre, en cada turno. La skill completa con diagnóstico sigue disponible en paralelo para cuando pidas naturalizar un texto específico.

El snippet listo para copiar está en [`always-on/CLAUDE-SNIPPET.md`](always-on/CLAUDE-SNIPPET.md).

### Instalación global (todos tus proyectos)

Añade el contenido del snippet al final de tu `CLAUDE.md` global:

```bash
cat always-on/CLAUDE-SNIPPET.md >> ~/.claude/CLAUDE.md
```

En Windows (PowerShell):

```powershell
Get-Content always-on/CLAUDE-SNIPPET.md | Add-Content $HOME\.claude\CLAUDE.md
```

### Instalación en un proyecto puntual

Si solo quieres que aplique dentro de un proyecto concreto, añádelo al `CLAUDE.md` de ese proyecto en vez del global:

```bash
cat always-on/CLAUDE-SNIPPET.md >> /ruta/a/tu-proyecto/CLAUDE.md
```

### Diferencias entre los dos modos

| | Modo explícito (skill) | Modo always-on (CLAUDE.md) |
|---|---|---|
| Cómo se activa | Frases gatillo o `/naturalizacion-texto-ia` | Siempre, sin pedirlo |
| Alcance | Un texto puntual que pegas o indicas | Todo el texto en español que Claude escribe |
| Output | Texto naturalizado + informe de diagnóstico | Solo el texto naturalizado, sin informe |
| Uso típico | Revisar/mejorar un texto ya escrito (propio o de otra IA) | Que las respuestas y documentos de Claude no suenen a IA desde el principio |

---

## Qué hace la skill

Aplica **11 técnicas lingüísticas** en un único pase de reescritura y genera dos outputs:

- **Output A** — El texto naturalizado, listo para usar
- **Output B** — Informe con patrones detectados, cambios aplicados y puntuación de naturalidad 0-100

### Las 11 técnicas

| # | Técnica | Qué corrige |
|---|---|---|
| 1 | Variación rítmica (burstiness) | Oraciones de longitud uniforme |
| 2 | Variación de surprisal léxico | Densidad léxica constante |
| 3 | Marcadores discursivos del español | Ausencia de "claro que", "a fin de cuentas", "eso sí" |
| 4 | Regla 70/30 de vocabulario | Vocabulario demasiado predecible |
| 5 | Prosa integrada sobre listas | Bullets y enumeraciones mecánicas |
| 6 | Hedges y matices naturales | Afirmaciones absolutas sin matices |
| 7 | Posicionamiento autoral | Ausencia de voz y perspectiva |
| 8 | Vocabulario inesperado | Texto plano sin picos de surprisal |
| 9 | Eliminación de conectores IA y guiones | "Además", "Por otro lado", "En conclusión", guiones largos (—) |
| 10 | Morfosintaxis específica del español | Pro-drop, clíticos, orden SVO flexible, subjuntivo |
| 11 | Coherencia tonal | Mezcla de registros |

### Lista negra (patrones que detecta y elimina)

**Conectores formulaicos:**
"En resumen", "En conclusión", "Es importante destacar que", "Por otro lado", "Además" (inicio de párrafo), "Sin embargo" (inicio de párrafo), "Es fundamental", "Cabe mencionar"

**Vocabulario predecible IA:**
"transformar", "fomentar", "implementación", "metodología", "optimizar", "facilitar", "aprovechar", "fundamental", "integral", "invaluable"

**Tipografía:**
Guiones largos (—) → siempre reemplazados por paréntesis o coma

Ver la tabla completa de sustituciones con alternativas concretas en [SUBSTITUTIONS.md](SUBSTITUTIONS.md).

---

## Fundamento técnico

La skill está fundamentada en investigación académica 2023-2026:

- **Perplexity léxica** — el texto humano varía la imprevisibilidad léxica; la IA elige siempre la palabra más probable ([DivEye, TMLR 2026](https://arxiv.org/pdf/2509.18880))
- **Burstiness rítmica** — la variación de longitud oracional tiene correlación de Pearson >0.7 con la detección de texto IA ([Xia et al., EACL 2026](https://arxiv.org/pdf/2601.07974))
- **Marcadores culturales** — el español tiene marcadores discursivos propios que los modelos omiten ([González Ledesma, 2024](https://www.analedesma.es/los-marcadores-discursivos-linguistica-computacional-e-inteligencia-artificial/))

Ver todas las referencias en [REFERENCES.md](.claude/skills/naturalizacion-texto-ia/REFERENCES.md) (27 fuentes).

---

## Diferencia con "humanizar texto IA"

| | [humanizar-texto-es](https://github.com/majiayu000/claude-skill-registry/blob/main/skills/productivity/humanizar-texto-es-toniperea-humanizar-texto-es/SKILL.md) | naturalizacion-texto-es |
|---|---|---|
| Objetivo | Evadir detectores | Calidad editorial real |
| Errores tipográficos | Sí (deliberados) | No |
| Guiones largos | No trata | Eliminación obligatoria |
| Morfosintaxis del español | No | Sí (pro-drop, clíticos, subjuntivo) |
| Diagnóstico cuantitativo | No | Sí (TTR, voz pasiva, conectores) |

---

## Contribuir

Los PRs son bienvenidos. Puedes proponer nuevas técnicas, añadir palabras a la lista negra o aportar ejemplos. Lee la [guía de contribución](.github/CONTRIBUTING.md).

---

## Licencia

[MIT](LICENSE) — Dorelys Martinez, 2026
