---
name: naturalizacion-texto-ia
description: Naturaliza texto en español generado por IA aplicando 11 técnicas lingüísticas para mejorar la calidad editorial y naturalidad comunicativa. Produce el texto reescrito y un informe con diagnóstico cuantitativo.
triggers:
  phrases:
    - "naturalizar"
    - "humanizar"
    - "hacer más humano"
    - "quitar el estilo IA"
    - "suena a IA"
    - "suena a ChatGPT"
    - "suena a Claude"
    - "reescribir"
    - "mejorar texto"
  fileTypes:
    - ".txt"
    - ".md"
    - ".docx"
---

# Skill: Naturalizar Texto IA en Español

## Propósito

Transforma texto en español generado por IA para que suene auténtico, fluido y natural, mejorando su calidad comunicativa y editorial. **No tiene como objetivo evadir detectores de IA**, sino producir texto de mayor calidad para lectores humanos.

## Cuándo activarse

Esta skill se activa cuando el usuario:
- Proporciona texto en español generado por IA (pegado directamente o en archivo `.txt`, `.md`, `.docx`)
- Usa palabras clave como "naturalizar", "humanizar", "hacer más humano", "quitar el estilo IA", "reescribir"
- Menciona que el texto "suena a ChatGPT / Claude / IA"
- Pide mejorar la naturalidad o fluidez de un texto

---

## Lista negra de marcas IA

Estas palabras y patrones deben identificarse y tratarse en el Paso 2 y eliminarse en el Paso 3.

### Tier 1 — Conectores formulaicos (sustituir siempre)
- "En resumen", "En conclusión", "Es importante destacar que", "Por otro lado"
- "Como se puede ver", "Es evidente que", "Cabe mencionar", "Sin embargo" (al inicio de párrafo)
- "En definitiva", "Cabe destacar que", "Hoy en día", "Vale la pena señalar que"
- "Permíteme explicarte", "Del lado positivo", "Por lo tanto", "En consecuencia"
- "Además" (inicio de párrafo), "También" (inicio de párrafo)

### Tier 2 — Vocabulario predecible IA (limitar a 1 ocurrencia o sustituir)
- "Transformar", "fomentar", "explorar", "cautivar", "profundo", "vital", "fundamental", "integral"
- "Implementación", "metodología", "utilización", "aprovechar", "optimizar", "facilitar"
- "Invaluable" (no existe en español estándar), "requerimiento" (usar "requisito")
- Cadenas de adverbios en "-mente" (más de 2 consecutivos)

### Tier 3 — Patrones estructurales (romper)
- Agrupamiento sistemático en tríos: "rápido, confiable y eficiente"
- "poder + infinitivo" repetido: "podría ser", "puede ayudar", "puede resultar" (más de 3 en un párrafo)
- Estructura predecible: "definición → importancia → tipos → conclusión"
- Párrafos todos de longitud similar (±2 oraciones de diferencia)

### Tier 4 — Guiones largos (eliminar siempre)
Los guiones largos (—) son una señal tipográfica característica del texto generado por IA en español. **Deben eliminarse siempre** y reemplazarse según el contexto:
- Si introduce un inciso o aclaración → usar paréntesis: `(aclaración)`
- Si introduce una conclusión o consecuencia → usar coma: `,`
- Si separa elementos de una enumeración → reformular como oración o usar coma

---

## Proceso (un solo pase)

### Paso 1 — Leer el input

- **Archivo**: usar el tool `Read` para leer el contenido del archivo indicado
- **Texto en el chat**: tomarlo directamente del mensaje del usuario

### Paso 2 — Análisis interno de patrones IA

Antes de reescribir, identificar y anotar internamente los patrones presentes:

| Patrón | Señal |
|---|---|
| Baja burstiness | Oraciones de longitud uniforme, sin variación rítmica |
| Baja perplexity | Vocabulario predecible, siempre la palabra más obvia |
| Conectores Tier 1 | Ver lista negra arriba |
| Vocabulario Tier 2 | Ver lista negra arriba |
| Guiones largos (—) | Presencia de em-dash tipográfico |
| Agrupamiento en tríos | Ver Tier 3 |
| Ausencia de voz autoral | Sin posicionamiento, sin matices, sin perspectiva |
| Prosa enumerativa | Bullets y listas donde debería haber párrafos |
| Falta de marcadores españoles | Sin "eso sí", "la verdad es que", "dicho esto", "a fin de cuentas" |
| Ausencia de hedges | Sin imprecisiones naturales ni matices de incertidumbre |
| Sujeto siempre explícito | IA tiende a no aprovechar el pro-drop del español |

### Paso 3 — Aplicar las 11 técnicas de naturalización

Aplicar **simultáneamente** en un único pase de reescritura:

#### 1. Variación rítmica (burstiness)
Alternar deliberadamente frases cortas con largas. Romper la cadencia uniforme con cortes inesperados. Una frase corta. Después, una más extensa que desarrolle la idea con detalle y establezca conexiones que el lector puede seguir sin esfuerzo.

#### 2. Variación de surprisal léxico
Intercalar vocabulario de alta frecuencia (palabras función, términos simples) con palabras más precisas o inesperadas, creando picos y valles de densidad léxica a lo largo del texto. No mantener complejidad léxica uniforme: un párrafo puede ser más llano, el siguiente más elaborado. Evitar que cada oración tenga exactamente el mismo peso informativo.

#### 3. Marcadores discursivos del español real
Introducir expresiones propias del español escrito natural:
- "eso sí", "la verdad es que", "dicho esto"
- "claro que", "hay que decirlo", "a fin de cuentas"
- "en el fondo", "sin ir más lejos", "ahí está la clave"
- "por cierto", "en mi experiencia", "y no es un detalle menor"

#### 4. Regla 70/30 de vocabulario
- **70%** del vocabulario original se mantiene para preservar el significado
- **30%** se sustituye por sinónimos más precisos, coloquiales o inesperados según el tono

#### 5. Prosa integrada sobre listas
Convertir bullets y enumeraciones en párrafos continuos con conectores variados y no formulaicos. Evitar que la transición se note forzada.

#### 6. Hedges y matices naturales
Añadir imprecisiones propias del texto humano donde corresponda:
- "en general", "en la mayoría de los casos"
- "tiende a", "puede que", "no siempre es así"
- "al menos en principio", "salvo excepciones"

#### 7. Posicionamiento autoral
Introducir pequeñas marcas de voz que den perspectiva:
- "lo que resulta llamativo es"
- "vale la pena detenerse aquí"
- "esto es relevante porque"
- "y no es un detalle menor"

#### 8. Eliminación de conectores IA y guiones largos
- "Además" (párrafo) → integrar sin conector, o "y también", "sumado a esto"
- "Por otro lado" → "ahora bien", "dicho esto", o simplemente un punto y aparte
- "En conclusión" → "en definitiva", "a fin de cuentas", o reformular sin anunciarlo
- "Es importante destacar" → integrar la importancia directamente en la oración
- **Guiones largos (—) → siempre paréntesis o coma** (ver Tier 4 de la lista negra)

#### 9. Morfosintaxis específica del español
Aprovechar rasgos propios del español que la IA aplana:
- **Pro-drop**: omitir el sujeto cuando el contexto lo permite ("Llegué tarde" vs. "Yo llegué tarde")
- **Clíticos pronominales**: usar "me", "te", "le", "nos" naturalmente en verbos que los admiten
- **Orden flexible**: invertir ocasionalmente el orden SVO ("A ese problema le damos solución")
- **Subjuntivo**: usarlo en contextos de duda, deseo o condición donde la IA pone indicativo
- **Posición postnominal de adjetivos**: evitar el exceso de adjetivos prenominales (calco del inglés)

#### 10. Irregularidades estilísticas controladas
Introducir elementos que el texto IA raramente produce de forma espontánea:
- Preguntas retóricas puntuales
- Fragmentos breves (oraciones sin verbo cuando el contexto lo permite)
- Pequeñas digresiones o incisos explicativos
- Arranques de frase no convencionales (adverbio, participio, pregunta)
- Transiciones imperfectas: "por cierto", "volviendo al tema", "aunque esto es otro asunto"

#### 11. Coherencia tonal
Asegurar que el registro (formal, divulgativo, académico, conversacional) sea consistente de principio a fin y coherente con el tono del texto original. No mezclar registros sin justificación.

> **Nota sobre texto académico:** La escritura académica bien estructurada obtiene naturalmente baja perplexity porque usa terminología estandarizada y estructuras formulaicas propias del género. En textos académicos, la naturalización no debe introducir informalidad, sino variar conectores, puntuación y estructura de párrafos respetando el registro.

### Paso 4 — Generar los dos outputs

---

## Outputs

### Output A — Texto naturalizado

Presentar el texto reescrito directamente, sin prefacio ni comentarios editoriales inline. El texto debe:
- Mantener el mismo significado e información que el original
- Aplicar las 11 técnicas de forma integrada y no mecánica
- No contener guiones largos (—)
- Preservar la corrección ortográfica y gramatical (no introducir errores)
- Respetar el tono y registro del texto original

---

### Output B — Informe de naturalización

```
## Informe de naturalización

### Patrones IA detectados en el original
- [listar los patrones del Paso 2, incluyendo guiones largos si los había]

### Técnicas aplicadas y cambios destacados
- [2-4 ejemplos concretos formato: ANTES → DESPUÉS]

### Diagnóstico cuantitativo

| Métrica | Valor estimado | Umbral humano | Estado |
|---|---|---|---|
| Conectores Tier 1 | X% de párrafos | < 10% | ✓ / ✗ |
| Guiones largos (—) | X encontrados | 0 | ✓ / ✗ |
| Variación de longitud oracional | Alta / Media / Baja | Alta | ✓ / ✗ |
| Diversidad léxica (TTR estimado) | Alta / Media / Baja | > 0.50 | ✓ / ✗ |
| Voz pasiva | X% de oraciones | 10-20% | ✓ / ✗ |
| Marcadores discursivos del español | Presentes / Ausentes | Presentes | ✓ / ✗ |

### Puntuación de naturalidad

| Dimensión | Puntos (máx. 20) | Justificación breve |
|---|---|---|
| Variación rítmica y surprisal | X/20 | ... |
| Diversidad léxica | X/20 | ... |
| Marcadores discursivos del español | X/20 | ... |
| Eliminación de conectores IA y guiones | X/20 | ... |
| Coherencia tonal y morfosintaxis | X/20 | ... |
| **TOTAL** | **X/100** | |
```

---

## Fundamento técnico

- **Perplexity léxica** (DivEye, TMLR 2026): el texto humano varía la imprevisibilidad léxica creando picos y valles. La IA produce distribuciones uniformes.
- **Burstiness rítmica** (Xia et al., EACL 2026): la variación de longitud oracional tiene correlación de Pearson > 0.7 con la detección de texto IA.
- **Marcadores culturales**: el español tiene un repertorio de marcadores discursivos propios que los modelos omiten o reemplazan por calcos del inglés (González Ledesma, 2024).
- **Guiones largos**: patrón tipográfico estadísticamente sobrerepresentado en texto IA en español; los hablantes nativos los perciben como señal artificial.

Esta skill **no introduce errores tipográficos ni ortográficos deliberados**. La corrección se preserva; la naturalidad se logra por vía estilística, léxica y morfosintáctica.

---

## Ejemplo de activación

**Usuario:** "Este texto suena muy a IA, ¿puedes naturalizarlo?"

**Respuesta esperada:**
1. Leer el texto proporcionado
2. Analizar patrones IA presentes (incluyendo guiones largos)
3. Reescribir aplicando las 11 técnicas en un pase
4. Presentar Output A (texto naturalizado, sin guiones largos) seguido de Output B (informe con diagnóstico cuantitativo y puntuación)

---

## Limitaciones

- **Preservación de significado**: no se cambia el contenido informativo, solo la forma
- **Registro**: el tono de salida debe ser coherente con el de entrada; no se convierte texto académico en coloquial sin indicación explícita
- **Texto académico**: en géneros con estructuras formulaicas propias, la naturalización se centra en variación de conectores y puntuación, no en informalidad
- **Extensión**: textos muy largos (>2000 palabras) pueden procesarse por secciones si el usuario lo indica
