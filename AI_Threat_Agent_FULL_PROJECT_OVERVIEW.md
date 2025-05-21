# AI Threat Agent

**Ransomware Detection & Intelligence Dashboard powered by GPT-4, Bright Data IOC correlation, and MITRE ATT&CK simulation.**  
Submitted to the Dev.to x Bright Data AI Challenge 2025

---

## Overview

AI Threat Agent empowers SMEs to detect, understand, and respond to ransomware threats without needing a dedicated Security Operations Center (SOC).  
It uses GPT-4 to classify log files, Bright Data to cross-match IOCs, and provides a simulated MITRE ATT&CK timeline with report export.

---

## Features

- GPT-4 powered log analysis with MITRE ATT&CK phase detection
- Malware family classification (LockBit, REvil, BlackCat)
- IOC correlation with Bright Data threat feed
- Prompt Injection Firewall for secure GPT inputs
- Interactive dashboard with timeline + What-if simulation
- HTML & PDF export of incident reports
- Dockerized deployment with one-click launch

---

## Project Structure

### Main Folders

- `app/` – Streamlit UI
  - `dashboard.py` – Basic version with timeline + what-if simulation
  - `dashboard_interactive.py` – Enhanced version with attack simulation
- `modules/` – Core logic
  - `threat_phase_analyzer.py` – GPT-4 powered log classification
  - `brightdata_correlator.py` – IOC matcher using Bright Data feed
  - `prompt_firewall.py` – Detects and blocks prompt injection attempts
- `data/`
  - `sample_logs/`
    - `lockbit_log.txt` – Sample log (LockBit attack)
    - `revil_log.txt` – Sample log (Revil attack)
    - `blackcat_log.txt` – Sample log (BlackCat activity)
  - `brightdata_feed.json` – IOC feed mock from Bright Data
- `export/reports/` – Output folder for HTML/PDF reports
- `tests/`
  - `test_module_integrity.py` – Unit tests for core logic

### Root Files

- `.env.example` – API Key template for OpenAI and Bright Data
- `requirements.txt` – Python dependencies
- `run.sh` – Bash script to launch locally
- `docker-compose.yml` – Full stack deployment
- `README.md` – This file
- `use_case.md` – Real-world Coffee Bliss ransomware scenario
- `LICENSE` – MIT License (© Dream)

---

## Quick Start

```bash
git clone https://github.com/yourhandle/ai-threat-agent.git
cd ai-threat-agent
cp .env.example .env
bash run.sh
```

---

## Sample Use Case: Coffee Bliss

> The café owner uploads suspicious logs to AI Threat Agent.  
> GPT detects LockBit ransomware phases: Execution → C2 → Exfiltration  
> Bright Data flags IP `45.83.92.101` as active C2  
> Alert is raised, attack timeline simulated, PDF report exported — all without a SOC.

---

## Tech Stack

- `Python` + `Streamlit`
- `OpenAI GPT-4 API`
- `Bright Data`
- `Docker` + `MITRE ATT&CK`
- `PDF export` + `IOC Matching`

---

## License

MIT © Dream
