# Referencias — Skill: Naturalizar Texto IA en Español

Documentación de las fuentes que fundamentan las decisiones de diseño de esta skill. Organizadas por categoría y con nota de su aporte específico.

---

## Papers Científicos

| # | Título | Autores | Año | Fuente | Aporte a la skill |
|---|---|---|---|---|---|
| 1 | Classification of Human- and AI-Generated Texts for English, French, German, and Spanish | Schaaff, Schlippe, Mindner | 2023 | [arXiv 2312.04882](https://arxiv.org/pdf/2312.04882) | Métricas de detección multilingüe; variación de longitud de párrafo como señal en español |
| 2 | Explaining Generalization of AI-Generated Text Detectors Through Linguistic Analysis | Xia, Stańczak, Roth | 2026 | [arXiv 2601.07974](https://arxiv.org/pdf/2601.07974) | Correlación Pearson >0.7 entre voz pasiva/longitud oracional y detección; justifica Técnica 1 y umbrales del Output B |
| 3 | Diversity Boosts AI-Generated Text Detection (DivEye) | Basani, Chen | 2025 | [arXiv 2509.18880](https://arxiv.org/pdf/2509.18880) | Fundamenta la Técnica 2 (variación de surprisal léxico); AUC 33.2% de mejora sobre detectores zero-shot |
| 4 | MASH: Evading Black-Box AI-Generated Text Detectors via Style Humanization | Gu, Li, Hu | 2026 | [arXiv 2601.08564](https://arxiv.org/pdf/2601.08564) | Style injection y DPO como métodos de humanización; informa las técnicas de inyección de voz autoral |
| 5 | Counter Turing Test (CT²): AI-Generated Text Detection is Not as Easy as You May Think | Chakraborty et al. | 2023 | [arXiv 2310.05030](https://arxiv.org/pdf/2310.05030) | Robustez de paráfrasis múltiple; introduce el AI Detectability Index como referencia conceptual |
| 6 | VTechAGP: Academic-to-General-Audience Text Paraphrase Dataset | Cheng et al. | 2024 | [arXiv 2411.04825](https://arxiv.org/pdf/2411.04825) | Técnicas de register shifting y simplificación de vocabulario; informa la regla 70/30 |
| 7 | AI-Writing Detection Using an Ensemble of Transformers and Stylometric Features | Varios | 2023 | [CEUR Vol-3496](https://ceur-ws.org/Vol-3496/autextification-paper9.pdf) | Type-Token Ratio, Flesch, passive voice ratio como métricas; base del diagnóstico cuantitativo del Output B |
| 8 | Stylometry recognizes human and LLM-generated texts in short samples | Varios | 2025 | [arXiv 2507.00838](https://arxiv.org/abs/2507.00838) | Patrones POS bigram y palabras función como señales resistentes al parafraseo; informa Técnica 9 |

---

## Literatura Gris

| # | Título / Fuente | Tipo | Año | URL | Aporte a la skill |
|---|---|---|---|---|---|
| 9 | Frases comunes de ChatGPT que detectan sistemas AI | Blog técnico | 2024 | [Hastewire ES](https://hastewire.com/es/blog/frases-comunes-de-chatgpt-que-detectan-sistemas-ai-52-chars) | Lista negra Tier 1: las 10 frases más detectables en español |
| 10 | Cómo humanizar textos de IA: trucos, prompts y herramientas | Blog educativo | 2024 | [GrowIt School](https://growitschool.com/tips-y-herramientas-para-humanizar-texto-ia/) | Conceptos de perplejidad y explosividad aplicados al español; señales de texto robótico |
| 11 | ¿Qué es la perplejidad en la detección de IA? | Blog técnico | 2025 | [ProofreaderPro](https://proofreaderpro.ai/es/blog/what-is-perplexity-ai-detection) | Fundamenta la paradoja académica incluida en la sección de Limitaciones |
| 12 | Los marcadores discursivos, Lingüística Computacional e IA | Blog investigadora | 2024 | [Ana González Ledesma](https://www.analedesma.es/los-marcadores-discursivos-linguistica-computacional-e-inteligencia-artificial/) | Base teórica para la Técnica 3 (marcadores discursivos del español real) |
| 13 | Cómo funcionan los detectores de IA | Documentación | 2024 | [QuillBot ES](https://quillbot.com/es/blog/herramientas-de-escritura-con-ia/como-funcionan-los-detectores-de-ia/) | Mecanismos de detección PLN; características artificiales en español |
| 14 | Cómo quitar patrones plantillados de IA | Guía técnica | 2024 | [Hastewire ES](https://hastewire.com/es/blog/como-quitar-patrones-plantillados-de-ia-en-textos-e-imagenes) | Vocabulario predecible a reemplazar; lista negra Tier 2 |
| 15 | Humanizar texto IA: 5 técnicas para sonar natural | Blog agencia | 2024 | [DonWeb](https://blog.donweb.com/humanizar-texto-ia-sonar-natural/) | Transiciones genuinas vs. formulaicas; voz personal |
| 16 | Guía para humanizar textos de IA de forma natural | Guía práctica | 2024 | [Hastewire ES](https://hastewire.com/es/blog/guia-para-humanizar-textos-de-ia-de-forma-natural) | Checklist de humanización; estrategia de puntuación |
| 17 | Parafrasear con IA: herramientas y trucos | Blog especializado | 2025 | [AI Content Factory](https://theaicontentfactory.com/es/parafrasear-con-ia/) | Técnicas de paráfrasis (reestructuración, sustitución, perspectiva); ejemplos antes/después |
| 18 | Buenas prácticas para el uso de IA en la escritura | Guía editorial | 2026 | [Periodismo.com](https://www.periodismo.com/2026/05/29/una-guia-de-buenas-practicas-para-el-uso-de-ia-en-la-escritura/) | Marco ético; límites recomendados para uso de IA en escritura profesional |
| 19 | CVC Anuario 2025 — IA y lengua española | Informe institucional | 2025 | [Cervantes](https://cvc.cervantes.es/lengua/anuario/anuario_25/gonzalez/p06.htm) | Contexto del estado del arte de modelos para español (ALIA-40B) |

---

## Redes Sociales y Comunidades

| # | Título / Fuente | Plataforma | Año | URL | Aporte a la skill |
|---|---|---|---|---|---|
| 20 | Palabras y frases que delatan el uso de ChatGPT | Web/medios | 2024 | [GenBeta](https://www.genbeta.com/inteligencia-artificial/estas-palabras-frases-tus-textos-dejan-claro-has-usado-chatgpt) | Lista de palabras específicas que delatan IA; informa lista negra Tier 2 |
| 21 | Estas son las palabras que revelan que un texto fue escrito por IA | Periodismo | 2024 | [Infobae](https://www.infobae.com/educacion/2024/04/15/estas-son-las-palabras-que-revelan-que-un-texto-fue-escrito-por-la-ia/) | Vocabulario detectado por lectores hispanohablantes; perspectiva del receptor |
| 22 | Detector de ChatGPT: servicios y apps en español | Medios tecnología | 2024 | [Xataka](https://www.xataka.com/basics/detector-chatgpt-9-servicios-apps-para-saber-texto-ha-sido-generado-ia-openai) | Herramientas de detección más usadas; precisión en español (Copyleaks 92%, GPTZero 88%) |
| 23 | Soy profesor y este es el método para detectar ChatGPT | Periodismo | 2025 | [The Objective](https://theobjective.com/curiosidades/2025-02-13/truco-saber-alumnos-trabajos-chatgpt/) | Señales que detectan educadores; ausencia de voz propia y riesgo intelectual |
| 24 | IA: Cómo detectar textos producidos por chatbox | Academia | 2023 | [SciELO Blog](https://blog.scielo.org/es/2023/11/17/ia-como-detectar-textos-producidos-por-chatbox-y-sus-plagios/) | Perspectiva editorial/académica sobre detección; informa la nota de paradoja académica |
| 25 | 41% de posts largos en LinkedIn son generados por IA | Investigación | 2026 | [Whatsnew](https://wwwhatsnew.com/2026/07/14/linkedin-41-porciento-posts-generados-ia-pangram-estudio-2026/) | Contexto de prevalencia del texto IA en español; escala del problema |
| 26 | Guía para periodistas sobre detección de IA | Periodismo de datos | 2025 | [Verificado México](https://verificado.com.mx/guia-periodistas-detectar-contenido-ia/) | Checklist profesional de detección; informa los patrones del Paso 2 |

---

## Skill de referencia

| # | Recurso | URL | Aporte |
|---|---|---|---|
| 27 | humanizar-texto-es (skill de referencia) | [GitHub](https://github.com/majiayu000/claude-skill-registry/blob/main/skills/productivity/humanizar-texto-es-toniperea-humanizar-texto-es/SKILL.md) | Punto de partida; esta skill se diferencia en foco editorial vs. evasión de detectores |

---

*Última actualización: 2026-07-24*
