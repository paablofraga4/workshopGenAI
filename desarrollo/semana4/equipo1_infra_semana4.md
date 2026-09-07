# Equipo 1 — Infraestructura y Plataforma
## Informe semanal · Semana 4 (31/08 – 04/09)

**Redacta:** I. Barreiro
**Fecha:** viernes 04/09/2026

---

### Estado general: 🟢 VERDE

Semana buena. Cerramos D3 en la fecha reestimada y el gateway lleva ya una semana completa en producción sin incidencias.

### Avance

- **D1:** cerrada.
- **D2:** cerrada. Estable, sin caídas en 6 días de operación.
- **D3 — Almacén de resultados y serie de precios: ENTREGADA ✅** el jueves 03/09, un día antes de la fecha reestimada.
- **D4 — Backtesting y canal de publicación:** 45%. Nueva estimación: **15/09**.

### Detalle de D3

Almacén aprovisionado y probado con carga sintética. Rendimiento correcto con el supuesto de dimensionado que asumimos (2.000 análisis diarios, 4 KB por registro).

Serie histórica de precios cargada para los 20 valores del universo, con 5 años de profundidad. Fuente: el repositorio corporativo de datos de mercado, que es el que teníamos disponible sin coste adicional. Los datos son de **cierre diario**.

Damos la entrega por completa. Si Equipo 2 necesitase otro tipo de granularidad, habría que abrir una petición aparte al proveedor de datos de mercado, con su coste y sus plazos.

### Nuevo retraso de D4

D4 pasa del 10/09 al 15/09. El motivo es que dos de nuestras tres personas han estado dedicadas a cerrar D3 y a resolver la configuración del proxy que arrastrábamos de la semana pasada. El canal de publicación está diseñado pero no implementado.

Con la ventana de 6 semanas del proyecto cerrando el 18/09, esto deja tres días para la validación con la mesa. Es ajustado pero lo vemos alcanzable si Equipo 2 llega con su parte lista.

### Consumo de modelo

Primer dato del gateway desde su puesta en marcha. Consumo acumulado del proyecto: **4.100 €** sobre un presupuesto de 6.000 € para las 6 semanas. Llevamos 4 semanas, de las cuales solo una con registro completo.

No sabemos qué consumo hubo antes del 27/08 porque las ejecuciones anteriores no pasaron por el gateway y no hay registro. A ritmo actual el presupuesto de consumo se agota antes del cierre de la fase 1.

### Bloqueos

Ninguno por nuestra parte.

### Próxima semana

- Implementar y probar D4 para el 15/09.
- Configurar alertas de coste en el gateway.
