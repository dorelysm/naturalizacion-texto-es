# Ejemplo — Detección de marcas técnicas y tipográficas (Tier 5)

Demostración enfocada en la Tier 5 de la lista negra: caracteres invisibles/watermarking y tipografía sospechosa visible. El texto de entrada contiene, de forma deliberada, marcas que no son errores de vocabulario sino señales técnicas.

---

## Texto original (input)

> La adopción de la inteligencia artificial en el sector educativo “plantea preguntas urgentes” sobre la evaluación del aprendizaje​… Los docentes reportan dificultades para distinguir el trabajo propio del estudiante de aquel producido con asistencia de modelos generativos.
>
> Esto es especialmente cierto en tareas de escritura – donde la frontera entre apoyo legítimo y sustitución total del esfuerzo del estudiante resulta difícil de trazar.

> **Nota editorial (no visible al copiar el texto):** entre "aprendizaje" y el punto suspensivo hay un carácter zero-width space (U+200B) insertado deliberadamente para este ejemplo. Además, la palabra "difícil" en el segundo párrafo usa una "і" cirílica (U+0456) en vez de la "i" latina (U+0069): visualmente son casi indistinguibles, pero un corrector ortográfico las marcaría como distintas.

---

## Output A — Texto naturalizado

La inteligencia artificial ha entrado al aula sin pedir permiso, y con ella llegó una pregunta que los docentes no terminan de resolver: cómo distinguir el trabajo propio del estudiante de aquel escrito con ayuda de un modelo generativo.

El problema se agudiza en tareas de escritura, donde la línea entre apoyo legítimo y sustitución del esfuerzo se vuelve, en la práctica, casi imposible de trazar.

---

## Informe de naturalización

### Patrones IA detectados en el original

- **Comillas curvas** (Tier 5b) en `"plantea preguntas urgentes"` (U+201C/U+201D)
- **Punto suspensivo unicarácter "…"** (Tier 5b, U+2026) tras "aprendizaje"
- **Zero-width space** (Tier 5a, U+200B) detectado entre "aprendizaje" y el punto suspensivo, párrafo 1 — invisible en el render normal del chat, identificado al inspeccionar el texto literal
- **Homoglifo cirílico** (Tier 5a) en "dif**і**cil" (U+0456 en vez de U+0069 latina), párrafo 2
- **En-dash mal usado** (Tier 5b, U+2013) en "escritura – donde la frontera", debía ser guion largo o coma
- **Conector Tier 1**: ninguno significativo en este caso puntual (el ejemplo se centra en Tier 5)

### Técnicas aplicadas y cambios destacados

| Antes | Después | Técnica |
|---|---|---|
| `"plantea preguntas urgentes"` (comillas curvas) | plantea preguntas urgentes (integrado en prosa, sin comillas) | Tier 5b → reformulación sin necesidad de comillas |
| "aprendizaje[ZWS]…" | "aprendizaje." | Tier 5a: zero-width space eliminado; punto suspensivo unicarácter → punto simple al reformular |
| "dif**і**cil" (homoglifo) | "difícil" (i latina) | Tier 5a: homoglifo sustituido por su equivalente latino |
| "escritura – donde la frontera" | "escritura, donde la línea" | Tier 5b: en-dash → coma |

### Diagnóstico cuantitativo

| Métrica | Original | Naturalizado | Umbral humano |
|---|---|---|---|
| Conectores Tier 1 | 0 | 0 | < 10% ✓ |
| Guiones largos (—) | 0 | 0 | 0 ✓ |
| Marcas técnicas/tipográficas Tier 5 | 4 (comillas curvas, ZWS, homoglifo, en-dash) | 0 | 0 ✓ |
| Variación longitud oracional | Media | Alta | Alta ✓ |
| Diversidad léxica (TTR est.) | ~0.55 | ~0.60 | > 0.50 ✓ |
| Marcadores discursivos del español | Ausentes | 1 presente ("y con ella llegó") | Presentes ✓ |

### Puntuación de naturalidad

| Dimensión | Puntos (máx. 20) | Justificación |
|---|---|---|
| Variación rítmica y surprisal | 16/20 | Texto corto; margen limitado de variación |
| Diversidad léxica | 15/20 | TTR ya era razonable en el original |
| Marcadores discursivos del español | 14/20 | Un solo marcador introducido, texto breve |
| Eliminación de conectores IA y guiones | 20/20 | Sin conectores Tier 1 ni guiones largos en el output |
| Coherencia tonal y morfosintaxis | 17/20 | Registro divulgativo-formal preservado |
| Ausencia de marcas técnicas y tipográficas IA (Tier 5) | 20/20 | Las 4 marcas detectadas (comillas curvas, zero-width space, homoglifo, en-dash) fueron eliminadas o normalizadas; el output no contiene ninguna |
| **TOTAL** | **102/120** | |

---

## Nota metodológica

Este ejemplo ilustra por qué el Paso 1 de la skill recomienda usar el tool `Read` cuando el input es un archivo: caracteres como el zero-width space o los homoglifos no siempre se distinguen visualmente al leer el texto pegado en el chat, pero sí se pueden identificar si se conocen los patrones Unicode a buscar (ver Tier 5 de `SKILL.md` y las tablas de `SUBSTITUTIONS.md`). El watermarking estadístico de tokens (tipo SynthID), en cambio, no deja ninguna huella de este tipo — no se puede "detectar" leyendo caracteres, y la skill lo señala como limitación explícita en vez de fingir una detección que no es técnicamente posible.
