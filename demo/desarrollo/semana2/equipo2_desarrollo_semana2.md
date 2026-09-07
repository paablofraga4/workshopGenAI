# Equipo 2 — Desarrollo y Modelos
## Informe semanal · Semana 2 (17/08 – 21/08)

**Redacta:** M. Solís
**Fecha:** viernes 21/08/2026

---

### Estado general: 🟡 ÁMBAR

### Hito de la semana: análisis de 4 lotes de noticias

**Resultado: 2 lotes de 4 completados (215 noticias de las 400 previstas).**

El histórico completo no estuvo disponible hasta el jueves 20/08 por la tarde, tres días y medio después del arranque de la semana. Con los dos días útiles restantes hemos podido procesar dos lotes: resultados trimestrales y noticias regulatorias. Quedan pendientes los lotes de noticias corporativas (M&A, cambios de dirección) y de macro sectorial.

No consideramos que esto comprometa la semana 3, pero arrastramos deuda: el conjunto de validación es ahora la mitad de grande de lo que debería, y eso afectará a la fiabilidad de las métricas de la semana 5.

### Avance del prompt

Primera versión del prompt de clasificación funcionando con salida estructurada. De las 215 noticias procesadas, 198 devolvieron JSON válido a la primera y 17 requirieron reintento. Estamos añadiendo validación de esquema para forzar el reintento automático.

Distribución preliminar de las 215: 34% señal alcista, 28% bajista, 38% sin efecto esperado. La proporción de "sin efecto" nos parece baja y sospechamos que el modelo tiende a encontrar dirección donde no la hay. Es algo que tendremos que corregir en el prompt.

### Sobre el acceso al modelo

El gateway corporativo no está disponible todavía. Para no perder la semana completa, hemos ejecutado los dos lotes **usando una clave de API propia del equipo, con datos de noticias públicas únicamente** (sin ninguna información de cartera ni de posiciones).

Somos conscientes de que esto se sale de lo acordado en el documento de planificación. Lo hemos hecho para no bloquear el avance y entendemos que el riesgo es acotado dado que solo se han enviado titulares y cuerpos de noticias de acceso público. Migraremos todo al gateway en cuanto esté disponible y repetiremos las ejecuciones para que quede el registro.

### Bloqueos

- Gateway de modelos (D2), pendiente.
- Dos lotes de análisis pendientes de completar.

### Próxima semana

- Completar los lotes 3 y 4.
- Iterar el prompt para corregir el sesgo direccional.
- Migrar al gateway.
