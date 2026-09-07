# Proyecto SIGNAL — Documento de planificación

**Cliente interno:** Mesa de Trading — Renta Variable
**Promotor:** Dirección de Tecnología
**Duración prevista:** 6 semanas (fase 1)
**Fecha de arranque:** lunes 10/08/2026
**Versión:** 1.0 — aprobada el 07/08/2026

---

## 1. Objetivo

Construir un prototipo que analice noticias de mercado en tiempo real y emita, para un universo inicial de 20 valores, una señal estructurada que indique si la noticia tiende a **subir**, **bajar** o **no afectar** al precio de la acción, con un nivel de confianza asociado.

Las señales relevantes se publicarán en un canal interno y el trader las usará como información adicional en su decisión. El sistema **no** ejecuta órdenes ni sustituye criterio humano en ningún punto.

## 2. Hipótesis de valor

El caso de uso se sostiene sobre tres supuestos. Si alguno cae, la fase 2 debe replantearse:

1. Que la noticia llegue al sistema con una latencia **inferior a 60 segundos** desde su publicación. Por encima de ese umbral el mercado ya ha incorporado la información y la señal pierde valor.
2. Que el modelo alcance una precisión direccional superior al 60% en el conjunto de validación.
3. Que el volumen de señales relevantes sea manejable por un trader (estimado entre 5 y 15 al día).

## 3. Equipos

| Equipo | Alcance | Responsable |
|---|---|---|
| **Equipo 1 — Infraestructura y Plataforma** | Despliegue de servicios, accesos, seguridad, datos y entornos | I. Barreiro |
| **Equipo 2 — Desarrollo y Modelos** | Análisis de noticias, prompting, evaluación, lógica de señal | M. Solís |

## 4. Entregas de Infraestructura (bloqueantes)

Las cuatro entregas de Equipo 1 son requisito previo para las fases de Equipo 2. Cada una habilita la siguiente.

| Id | Entrega | Fecha límite | Habilita |
|---|---|---|---|
| **D1** | API de ingesta de noticias desplegada y en producción, con acceso a **6 meses de histórico** y flujo en directo | Viernes 14/08 (fin S1) | Inicio del análisis de noticias en S2 |
| **D2** | Acceso al modelo de OpenAI a través del gateway corporativo, con supervisión, registro de llamadas y control de coste | Viernes 21/08 (fin S2) | Evaluación de respuestas y patrones en S3–S4 |
| **D3** | Almacén de resultados y serie histórica de precios intradía para los 20 valores | Viernes 28/08 (fin S3) | Medición de precisión direccional en S4 |
| **D4** | Entorno de backtesting y canal de publicación de señales | Viernes 04/09 (fin S4) | Validación con la mesa en S5–S6 |

## 5. Hitos de Desarrollo

| Semana | Hito de Equipo 2 | Depende de |
|---|---|---|
| S1 | Diseño del esquema de señal y criterios de etiquetado | — |
| **S2** | **Análisis completo de 4 lotes de noticias** (mínimo 400 noticias) sobre el histórico | D1 |
| S3 | Primera versión del prompt de clasificación con salida estructurada validada | D1 |
| **S4** | **Evaluación de respuestas del modelo e identificación de patrones** de acierto y error por tipo de noticia | D2 |
| S5 | Medición de precisión direccional contra movimiento real de precio | D3 |
| S6 | Demostración a la mesa y recomendación sobre fase 2 | D4 |

## 6. Reglas de gobierno acordadas

- **Ningún acceso a modelos de lenguaje fuera del gateway corporativo.** El uso de claves personales o de cuentas no corporativas está expresamente prohibido, incluso para pruebas, por política de tratamiento de información de mercado.
- Reporte semanal de cada equipo, cada viernes, en formato libre pero cubriendo: avance, bloqueos y desviaciones.
- Cualquier desviación superior a 3 días laborables en una entrega bloqueante se escala al promotor en las 24 horas siguientes.
- Los supuestos del apartado 2 se revisan al cierre de cada semana. Si alguno se invalida, se convoca comité extraordinario.

## 7. Presupuesto de fase 1

| Concepto | Importe |
|---|---|
| Infraestructura y licencias | 34.000 € |
| Consumo de modelos (estimado) | 6.000 € |
| Proveedor de noticias (3 meses) | 21.000 € |
| Horas de equipo interno | 78.000 € |
| **Total fase 1** | **139.000 €** |
