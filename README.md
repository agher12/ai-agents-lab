# AI Agents Lab

Mi laboratorio de aprendizaje de agentes de IA con **LangChain / LangGraph**, LLMs en la nube (Gemini) y locales (Ollama). Aquí están los ejercicios; mis proyectos principales tienen repositorio propio:

- 🛡️ **[SmartSOC](https://github.com/agher12/SMART-SOC)**: triaje de alertas Wazuh → TheHive con un LLM local.

## Proyectos

| Carpeta | Qué practica | Stack |
|---|---|---|
| [`LLM_API`](LLM_API) | Exponer un LLM local como API REST con historial de conversación y un cliente de consola | Flask, Ollama (`gemma3:1b`), LangChain |
| [`STRUCTURED_OUTPUT`](STRUCTURED_OUTPUT) | Salidas estructuradas con Pydantic: un agente que usa herramientas (`send_email`) y un generador de recetas | LangChain `create_agent`, Gemini, Pydantic |
| [`weather-agent`](weather-agent) | Agente con herramientas (API del tiempo y geolocalización inversa), interfaz web y **memoria persistente** en Postgres | LangGraph `PostgresSaver`, Supabase, Flask, OpenWeather |

## Cómo ejecutar un proyecto

Cada carpeta es independiente y tiene sus propios `.venv` y `.env`:

```bash
cd weather-agent
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env   # rellena tus claves
python app.py
```

`LLM_API` necesita [Ollama](https://ollama.com) con el modelo descargado (`ollama pull gemma3:1b`). Arranca `main.py` y después `client.py`.

## Conceptos cubiertos

Tool calling · structured output · memoria/checkpointing con LangGraph · LLMs locales frente a cloud · servir agentes con Flask.
