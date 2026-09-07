# Equipo 2 — Desarrollo y Modelos
## Informe semanal · Semana 3 (24/08 – 28/08)

**Redacta:** M. Solís
**Fecha:** viernes 28/08/2026

---

### Estado general: 🟡 ÁMBAR

### Avance

- Completados los lotes 3 y 4. Total acumulado: **391 noticias analizadas**.
- Prompt de clasificación en su versión 4. La distribución se ha equilibrado tras introducir una instrucción explícita para exigir evidencia antes de asignar dirección: ahora 26% alcista, 22% bajista, 52% sin efecto. Nos parece mucho más razonable.
- Migración al gateway corporativo hecha el viernes 28 por la mañana. A partir de ahora todo el consumo queda registrado.
- Identificados tres patrones preliminares de acierto y error por tipo de noticia. Las noticias de resultados se clasifican bien; las regulatorias, mal, porque el modelo no distingue entre una propuesta en consulta y una norma aprobada.

### Observación sobre la latencia de la fuente

Al pasar del histórico al flujo en directo hemos medido el retardo entre la publicación original de la noticia y su llegada a nuestra API.

**Retardo medio observado: 15 minutos y 40 segundos.** Mínimo 9 minutos, máximo 31.

Hemos revisado la documentación del proveedor y el plan contratado es el de distribución estándar, no el de baja latencia. Entendemos que el de baja latencia existe como producto aparte.

Lo dejamos anotado aquí porque es un dato de contexto relevante para interpretar los resultados. Seguimos avanzando con normalidad en la parte de clasificación, que es lo que ocupa el resto de esta semana y la siguiente.

### Bloqueos

- Almacén de resultados (D3) pendiente. Mientras tanto guardamos los resultados en ficheros locales del equipo, lo que nos impide empezar la medición de precisión direccional.

### Próxima semana

- Evaluación sistemática de respuestas del modelo y cierre del análisis de patrones.
- Preparar el conjunto de validación para la medición de precisión, aunque no podamos ejecutarla hasta tener D3.
- Revisar el prompt para el caso de noticias regulatorias.
