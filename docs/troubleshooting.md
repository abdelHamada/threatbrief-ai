# Troubleshooting

## Ollama Is Not Running

If the app shows:

```text
Ollama is not running. Start it with: ollama serve
```

Run:

```powershell
ollama serve
```

## Model Not Found

If the app shows:

```text
Model not found. Pull it with: ollama pull llama3.1
```

Run:

```powershell
ollama pull llama3.1
```

If you typed a different model name in the sidebar, pull that model instead.

## Invalid JSON

Use a JSON validator or check for common issues:

- Missing commas
- Single quotes instead of double quotes
- Trailing commas
- Pasted log text around the JSON object

## Streamlit Command Not Found

Make sure the virtual environment is activated and dependencies are installed:

```powershell
venv\Scripts\activate
pip install -r requirements.txt
```

## The Model Response Is Too Slow

Local model speed depends on your machine. Try a smaller model:

```powershell
ollama pull phi
```

Then enter `phi` in the Streamlit sidebar.
