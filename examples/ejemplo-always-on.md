# Ejemplo — Modo always-on

A diferencia del [ejemplo básico](ejemplo-basico.md), aquí no hay un texto de entrada que se pide "naturalizar": el snippet de `always-on/CLAUDE-SNIPPET.md` está cargado en `CLAUDE.md`, y Claude aplica las técnicas de forma silenciosa a cualquier respuesta en español, sin producir Output B.

---

## Pregunta del usuario

> ¿Por qué le conviene a una empresa pequeña adoptar el trabajo remoto?

## Sin modo always-on (respuesta típica de un modelo sin ajustar)

> Es importante destacar que el trabajo remoto ofrece múltiples beneficios para las empresas pequeñas. En primer lugar, permite reducir costos operativos al eliminar la necesidad de un espacio físico amplio. Además, facilita el acceso a talento de otras regiones —lo cual amplía significativamente el grupo de candidatos disponibles. Por otro lado, contribuye a mejorar la satisfacción y retención de los empleados. En conclusión, es fundamental que las empresas pequeñas evalúen la implementación de esta modalidad para optimizar sus operaciones.

## Con modo always-on activado (misma pregunta, respuesta directa de Claude)

> Para una empresa pequeña, el ahorro es lo primero que salta a la vista: sin oficina que mantener, el presupuesto rinde para otras cosas. Pero hay algo igual de valioso y que se nota menos al principio, y es el acceso a talento que antes quedaba fuera del radar simplemente por vivir en otra ciudad.
>
> La retención también mejora, aunque no siempre por las razones obvias. No es solo que la gente valore la flexibilidad (la valora), sino que deja de perder horas en traslados y eso, con el tiempo, se traduce en menos rotación. Eso sí, nada de esto funciona solo: hace falta cierta disciplina en la comunicación para que el equipo no se disperse.

Nótese que no hay Output B ni comentario sobre qué técnicas se aplicaron: el modo always-on integra la naturalización directamente en la respuesta, como parte normal de cómo escribe Claude.
