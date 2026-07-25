# Contribuir a naturalizacion-texto-es

Gracias por querer mejorar esta skill. Aquí tienes las formas principales de aportar.

## Proponer una nueva técnica

1. Abre un issue con el título `[técnica] Nombre de la técnica`
2. Describe: qué patrón IA corrige, cómo se aplica, y si tienes un ejemplo antes/después
3. Si tienes respaldo en literatura académica o gris, mejor. Puedes añadirla a `REFERENCES.md`
4. Haz un PR modificando `SKILL.md` en la sección "Paso 3" y añadiendo la referencia

## Añadir palabras a la lista negra

Si detectas palabras o frases que delatan texto IA en español y no están en la lista negra:

1. Abre un issue con `[lista negra] palabra o frase`
2. Indica en qué tier encajaría (Tier 1-4) y por qué
3. PR directo a `SKILL.md` sección "Lista negra"

## Aportar ejemplos

Los ejemplos ayudan a entender cómo funciona la skill en la práctica:

1. Crea un archivo en `examples/` con el nombre `ejemplo-[tema].md`
2. Sigue el formato de `examples/ejemplo-basico.md`
3. Haz el PR

## Reportar un caso donde la skill no funciona bien

Abre un issue describiendo:
- El texto de entrada
- Qué salió mal en el output
- Qué esperabas que pasara

## Código de conducta

Este proyecto es para la comunidad hispanohablante. Los issues y PRs deben estar en español.
