# ThreatBrief AI

ThreatBrief AI is a beginner-friendly Python Streamlit app for defensive cybersecurity alert triage. Paste or upload JSON alerts from Wazuh, AWS CloudTrail, GuardDuty, or Prowler, then generate a SOC analyst-style incident brief using a local Ollama model.

No paid API key is required. The app runs locally on your Windows machine.

## Tools Used

- Python
- Streamlit
- Ollama
- requests
- python-dotenv

## Features

- Clean Streamlit dashboard
- Paste JSON alerts into a text box
- Upload `.json` alert files
- Detects likely alert source: Wazuh, AWS CloudTrail, AWS GuardDuty, Prowler, or Unknown
- Sends alerts to a local Ollama model
- Generates:
  - Incident summary
  - Severity
  - Key evidence
  - Possible MITRE ATT&CK mapping
  - False-positive explanation
  - Recommended response steps
  - Resume-friendly explanation
- Exports the final report as Markdown
- Includes sample alerts and documentation

## Windows Setup

Open PowerShell in the project folder and run:

```powershell
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

## Install Ollama

1. Download Ollama for Windows from [https://ollama.com/download](https://ollama.com/download).
2. Install and start Ollama.
3. Pull the default model:

```powershell
ollama pull llama3.1
```

If Ollama is not already running, start it with:

```powershell
ollama serve
```

## Run the App

```powershell
streamlit run app.py
```

Streamlit will print a local URL, usually:

```text
http://localhost:8501
```

## Change the Model

The default model is `llama3.1`. You can change it in the Streamlit sidebar, or copy `.env.example` to `.env` and edit:

```text
OLLAMA_MODEL=llama3.1
```

Other local model options include:

```powershell
ollama pull mistral
ollama pull phi
```

## Sample Alerts

The `alerts/` folder includes:

- Failed Windows login
- Suspicious PowerShell execution
- AWS IAM user created
- AWS root account activity
- GuardDuty finding
- Prowler S3 public access finding

## Example Screenshots

Screenshots can be added to `docs/screenshots.md` after you run the app locally.

## Resume Bullets

See `resume-bullets.md` for ready-to-adapt resume bullets.

## GitHub Project Description

Local AI-powered cybersecurity alert triage app using Python, Streamlit, Ollama, and sample Wazuh, AWS CloudTrail, GuardDuty, and Prowler alerts.

## Defensive Use Only

ThreatBrief AI is built for defensive security alert review, learning, and portfolio demonstration. It does not perform exploitation, scanning, credential collection, or offensive actions.
