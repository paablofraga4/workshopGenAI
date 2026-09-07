# Equipo 2 — Desarrollo y Modelos
## Informe semanal · Semana 1 (10/08 – 14/08)

**Redacta:** M. Solís
**Fecha:** viernes 14/08/2026

---

### Estado general: 🟢 VERDE

### Avance

- Cerrado el esquema de la señal: `{ valor, direccion, confianza, horizonte, justificacion, fuente, timestamp }`. Validado con dos personas de la mesa el miércoles.
- Definidos los criterios de etiquetado para el conjunto de validación. Tres categorías de noticia (resultados, regulatoria, corporativa) con reglas distintas de horizonte temporal.
- Preparado el cuaderno de análisis y el pipeline de lectura, a la espera de datos.
- Universo inicial de 20 valores acordado con la mesa.

### Sobre el acceso a datos

Recibimos aviso de disponibilidad de la API el viernes 14 a las 11:40. Hemos podido conectar y traer datos, pero lo que hay accesible ahora mismo es el **entorno de pruebas del proveedor, con 48 horas de histórico**, no los 6 meses que figuran en la planificación.

Con 48 horas no podemos montar el conjunto de validación ni empezar los 4 lotes de análisis previstos para la semana 2. Lo hemos comentado con Equipo 1 y nos indican que las credenciales de producción están en activación por parte del proveedor.

Asumimos que se resolverá a principios de la semana que viene y que no afecta al hito de S2. Si el lunes o martes no tenemos histórico completo, el hito de las 400 noticias no será alcanzable.

### Bloqueos

- **Pendiente:** histórico de 6 meses de noticias. Sin fecha confirmada.

### Próxima semana

- Arrancar el análisis de los 4 lotes en cuanto haya histórico.
- Primera versión del prompt de clasificación.
- Enviar a Equipo 1 lo que necesiten para el dimensionado de su parte.
