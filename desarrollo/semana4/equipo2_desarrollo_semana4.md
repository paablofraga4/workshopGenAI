# Equipo 2 — Desarrollo y Modelos
## Informe semanal · Semana 4 (31/08 – 04/09)

**Redacta:** M. Solís
**Fecha:** viernes 04/09/2026

---

### Estado general: 🟡 ÁMBAR

### Hito de la semana: evaluación de respuestas y patrones

**Completado.** Evaluación cerrada sobre las 391 noticias analizadas, con un subconjunto de 120 etiquetadas manualmente por dos personas del equipo como referencia.

#### Precisión direccional preliminar

| Tipo de noticia | Aciertos | Muestra | Precisión |
|---|---|---|---|
| Resultados trimestrales | 41 | 58 | 71% |
| Corporativa (M&A, dirección) | 14 | 27 | 52% |
| Regulatoria | 10 | 35 | 29% |
| **Total** | **65** | **120** | **54%** |

El objetivo del documento de planificación es superar el 60%. Estamos en 54%. El resultado está muy condicionado por las noticias regulatorias, donde el modelo sigue sin distinguir entre una propuesta en consulta y una norma en vigor, pese a dos iteraciones del prompt.

Consideramos el dato preliminar: la muestra es pequeña (consecuencia del conjunto de validación reducido que arrastramos desde la semana 2) y creemos que hay margen de mejora si tratamos las regulatorias como categoría aparte con su propio prompt. Lo proponemos para la semana 5.

#### Patrones identificados

1. El modelo acierta cuando la noticia contiene una cifra comparable con una expectativa previa, y falla cuando la valoración depende de contexto no presente en el texto.
2. Sobrerreacciona a titulares con lenguaje intenso aunque el cuerpo de la noticia sea neutro.
3. En noticias que afectan a un sector completo, asigna la misma dirección a todos los valores del sector sin discriminar posición competitiva.

### Volumen de señales

Extrapolando el flujo en directo de esta semana al universo de 20 valores, saldrían **unas 42 señales relevantes al día**. La planificación estimaba entre 5 y 15. Habrá que subir el umbral de confianza para publicar, pero eso reducirá también los aciertos. Es una decisión de producto que no nos corresponde a nosotros.

### Bloqueo con D3

Hemos recibido el almacén el jueves y hemos empezado a cargar resultados sin problema.

El punto es la serie de precios: son datos de **cierre diario**. Para medir precisión direccional en el horizonte que definimos con la mesa (movimiento en las 2 horas posteriores a la noticia) necesitamos **precios intradía**. Con cierre diario no podemos ejecutar la medición del hito de la semana 5 tal y como está definida.

Lo hemos hablado con Equipo 1 y nos indican que hay que abrir una petición al proveedor de datos de mercado, con coste y plazo por determinar. No tenemos visibilidad de cuánto tardaría.

### Latencia de la fuente

Consultamos al proveedor de noticias sobre el plan de baja latencia. Nos confirman que existe, que dejaría el retardo por debajo de 30 segundos, y que el sobrecoste es de **18.000 € anuales** sobre el contrato actual. Queda a decisión de dirección del proyecto.

### Bloqueos

- Precios intradía para poder medir precisión (S5).
- Decisión sobre el plan de baja latencia.
- Decisión sobre el umbral de publicación de señales.

### Próxima semana

- Prompt específico para noticias regulatorias.
- Preparar el pipeline de medición para poder ejecutarlo el mismo día que tengamos datos intradía.
- Preparar los materiales de la demostración a la mesa.
