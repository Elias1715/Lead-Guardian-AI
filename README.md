# 🛡️ Lead-Guardian-AI: Sistema Inteligente de Triaje y Monitoreo

Este es un workflow avanzado de **n8n** diseñado para la gestión automatizada de leads y soporte técnico. El sistema actúa como un "guardián" que analiza, clasifica y deriva cada consulta entrante al canal correspondiente, asegurando que ninguna oportunidad de venta se pierda y que las urgencias se atiendan de inmediato.

## 🧠 Arquitectura del Sistema

1.  **Ingesta y Normalización:** Recepción de datos vía Webhook/Formulario y limpieza de strings mediante expresiones JavaScript para asegurar un análisis preciso.
2.  **Cerebro de Clasificación (Regex Switch):** Un nodo Switch configurado con **Expresiones Regulares (Regex)** que segmenta el tráfico en 4 rutas:
    * **Ventas:** Detección de intención de compra y registro en Base de Datos (Google Sheets).
    * **Soporte Crítico:** Identificación de palabras de alerta y envío de notificación inmediata vía Gmail.
    * **Filtro de Spam:** Aislamiento de mensajes sospechosos con una pausa de seguridad (Wait) y log de auditoría.
    * **Fallback (Extra Output):** Captura de consultas no categorizadas para revisión manual, garantizando 0% de pérdida de datos.
3.  **Trazabilidad:** Sistema de logs (NoOp/Sheets) para monitorear el rendimiento de los filtros.

## 🛠️ Especificaciones Técnicas

* **Lógica:** Regex Match avanzado (`.*(palabra).*`).
* **Integraciones:** Google Sheets API, Gmail API, n8n Core Nodes.
* **Seguridad:** Manejo de datos nulos y normalización a minúsculas (`toLowerCase`).

## 🚀 Impacto en el Negocio
Este bot reduce el tiempo de respuesta en casos críticos de horas a **segundos** y automatiza la carga administrativa de los equipos de ventas.

<img width="1121" height="468" alt="image" src="https://github.com/user-attachments/assets/d8d0f5c9-da90-4612-94d3-d1b0732065c4" />
