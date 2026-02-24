🤖 Descripción

Este proyecto implementa un asistente personal inteligente para Telegram utilizando n8n, OpenAI y agentes de IA con herramientas integradas de productividad.

El bot permite interactuar mediante texto o mensajes de voz, automatizando tareas como gestión de emails, resumen de correos y administración del calendario directamente desde Telegram.

⚙️ Arquitectura del workflow

El sistema está diseñado como un agente conversacional multitarea con procesamiento dinámico de entrada.

📩 Flujo principal
1️⃣ Telegram Trigger

Recibe mensajes enviados al bot desde Telegram.

2️⃣ Switch Node — Detección de tipo de mensaje

El workflow identifica automáticamente:

✅ Mensajes de texto

🎤 Mensajes de voz

📝 Procesamiento de texto

Se extrae el contenido del mensaje.

Se envía al AI Agent.

El agente interpreta la intención del usuario y decide qué herramienta utilizar.

🎙️ Procesamiento de audio

Se descarga el archivo de voz desde Telegram.

OpenAI transcribe automáticamente el audio a texto.

El texto resultante se envía al AI Agent para su análisis.

Esto permite interactuar con el asistente mediante notas de voz.

🧠 Inteligencia artificial

El AI Agent:

Mantiene conversaciones naturales

Usa memoria contextual por usuario

Selecciona herramientas automáticamente según la solicitud

La memoria utiliza el chat.id como identificador de sesión.

🧰 Herramientas disponibles
📧 Gmail Summary

Obtiene emails recientes.

Genera resúmenes automáticos.

✉️ Gmail Send

Envía correos redactados por IA.

Firma automáticamente los mensajes como Fran.

Genera emails bien estructurados.

📅 Calendar_Set

Agenda eventos en Google Calendar.

📆 Calendar_Get

Consulta próximos eventos o disponibilidad.

💬 Respuesta al usuario

Una vez procesada la solicitud:

El agente genera la respuesta.

n8n envía automáticamente el mensaje al chat de Telegram.

🧠 Tecnologías utilizadas

n8n

OpenAI (GPT-4o)

Telegram Bot API

Google Calendar API

Gmail API

LangChain Agents

Speech-to-Text (OpenAI Transcription)

✨ Características principales

Soporte para texto y audio

Transcripción automática de voz

Memoria conversacional

Gestión de correo electrónico

Automatización de calendario

Asistente personal desde Telegram

Selección automática de herramientas IA

🚀 Casos de uso

Asistente personal diario

Gestión rápida de emails

Programación de reuniones por chat

Resumen de bandeja de entrada

Organización de agenda mediante voz

🛠️ Requisitos

n8n (self-hosted o cloud)

OpenAI API Key

Telegram Bot Token

Google OAuth (Gmail + Calendar)

▶️ Instalación

Importar el workflow en n8n.

Configurar credenciales:

Telegram API

OpenAI

Gmail OAuth2

Google Calendar OAuth2

Activar el workflow.

Enviar un mensaje o nota de voz al bot.

El asistente comenzará a responder automáticamente.

📌 Notas técnicas

El workflow detecta automáticamente el tipo de input.

Las notas de voz pasan por transcripción antes del análisis.

El agente decide cuándo usar Gmail o Calendar sin lógica condicional manual.

Diseñado como asistente personal centralizado.
