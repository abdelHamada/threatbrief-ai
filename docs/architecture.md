# Architecture

ThreatBrief AI is intentionally simple so it is easy to understand, modify, and publish as a portfolio project.

## Flow

1. The user pastes JSON or uploads a `.json` alert file in Streamlit.
2. The app validates that the input is valid JSON.
3. `detect_alert_source()` performs best-effort source identification.
4. `generate_incident_report()` inserts the alert into the SOC analyst prompt.
5. `call_ollama()` sends the prompt to the local Ollama API at `http://localhost:11434/api/generate`.
6. The model returns a structured Markdown incident report.
7. The user can download the report as a Markdown file.

## Main Files

- `app.py`: Streamlit interface and application logic
- `prompts/incident_triage_prompt.txt`: SOC analyst prompt template
- `alerts/`: Sample JSON alerts
- `reports/`: Example Markdown report
- `docs/`: Setup, architecture, troubleshooting, and screenshot notes

## Local AI Design

The app uses Ollama so alerts can be analyzed locally without a paid API key. The default model is `llama3.1`, but the sidebar supports any local Ollama model that has been pulled.
