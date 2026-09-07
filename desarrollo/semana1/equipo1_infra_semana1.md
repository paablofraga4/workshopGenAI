# Equipo 1 — Infraestructura y Plataforma
## Informe semanal · Semana 1 (10/08 – 14/08)

**Redacta:** I. Barreiro
**Fecha:** viernes 14/08/2026

---

### Estado general: 🟢 VERDE

Semana de arranque sin incidencias reseñables. Se cierra la entrega D1 dentro de plazo.

### Avance

- **D1 — API de ingesta de noticias: ENTREGADA ✅**
  Servicio desplegado el jueves 13/08. Endpoint operativo, autenticación configurada y documentación publicada en el wiki interno. Se ha comunicado el acceso a Equipo 2 el viernes por la mañana.
- **D2 — Gateway de modelos:** iniciado. Se ha abierto la solicitud de alta del servicio ante el equipo de Seguridad de la Información. Trabajo técnico al 40%.
- **D3 — Almacén de resultados:** no iniciado, conforme a plan.
- **D4 — Backtesting y canal:** no iniciado, conforme a plan.

### Detalle técnico

El despliegue se ha hecho sobre el clúster compartido de servicios analíticos. Rendimiento holgado para el volumen previsto. Se ha configurado monitorización básica y alertas de disponibilidad.

El contrato con el proveedor de noticias quedó firmado el 11/08. La activación de las credenciales de producción está en curso por parte del proveedor; mientras tanto se ha habilitado el entorno de pruebas del proveedor para que Equipo 2 pueda ir familiarizándose con el formato de los datos.

### Bloqueos

Ninguno.

### Próxima semana

- Cerrar D2 en plazo (21/08). El único paso pendiente por nuestra parte es la aprobación de Seguridad, que suele resolverse en 5 días hábiles.
- Comenzar el dimensionado de D3.

### Nota

Para dimensionar correctamente el almacén de D3 necesitaremos de Equipo 2 una estimación del volumen de escritura previsto (número de análisis por día y tamaño medio del registro). Lo comentaremos en el punto de sincronización.
