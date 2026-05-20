# Setup Guide

This guide assumes Windows and PowerShell.

## 1. Create a Virtual Environment

```powershell
python -m venv venv
venv\Scripts\activate
```

## 2. Install Python Dependencies

```powershell
pip install -r requirements.txt
```

## 3. Install Ollama

Download Ollama for Windows from:

[https://ollama.com/download](https://ollama.com/download)

## 4. Pull the Default Model

```powershell
ollama pull llama3.1
```

## 5. Start Ollama

```powershell
ollama serve
```

If Ollama is already running in the background, this command may say the port is already in use. That is usually fine.

## 6. Run ThreatBrief AI

Open a new PowerShell tab in the project folder:

```powershell
venv\Scripts\activate
streamlit run app.py
```

Then open the local Streamlit URL in your browser.
