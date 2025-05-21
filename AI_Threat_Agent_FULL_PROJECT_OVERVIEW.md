
# AI Threat Agent – Full Project Breakdown (Production-Ready)

AI Threat Agent is a cybersecurity tool built for SMEs to detect, analyze, and respond to ransomware threats using GPT-4, Bright Data IOC correlation, and a streamlit-based UI. The system includes simulated MITRE ATT&CK phase detection, prompt injection defense, timeline simulation, and exportable incident reports.

---

## Project Directory Structure

AI_Threat_Agent/
├── app/
│   ├── dashboard.py                  # Main Streamlit dashboard (basic timeline + what-if analysis)
│   └── dashboard_interactive.py     # Enhanced dashboard with simulated MITRE timeline and threat summaries
│
├── modules/
│   ├── threat_phase_analyzer.py     # GPT-based analyzer for MITRE phase and malware family detection
│   ├── brightdata_correlator.py     # Match IOC (IP, domain, file) against Bright Data threat feed
│   └── prompt_firewall.py           # Detect prompt injection via regex/keyword
│
├── data/
│   ├── sample_logs/
│   │   ├── lockbit_log.txt          # Sample log showing LockBit activity
│   │   ├── revil_log.txt            # Sample log showing Revil ransomware
│   │   └── blackcat_log.txt         # Sample log simulating BlackCat/ALPHV
│   └── brightdata_feed.json         # Mock IOC threat intelligence feed from Bright Data
│
├── export/
│   └── reports/                     # HTML/PDF export directory for incident reports
│
├── tests/
│   └── test_module_integrity.py     # Unit tests for modules (basic integrity check)
│
├── .env.example                     # Template for setting OPENAI_API_KEY and BrightData key
├── requirements.txt                 # Python dependencies (streamlit, openai, etc.)
├── run.sh                           # Run script to launch the dashboard
├── docker-compose.yml               # Container orchestration for API + frontend
├── README.md                        # Project overview, usage guide, quick start
├── use_case.md                      # Business use-case: ransomware incident (Coffee Bliss)
└── LICENSE                          # MIT License © Dream

---

## Core Modules

### `threat_phase_analyzer.py`
Uses GPT-4 to analyze logs and classify them into MITRE ATT&CK phases.
- Output includes: threat name, severity level, phases list
- Example malware matched: LockBit, REvil, BlackCat

### `brightdata_correlator.py`
Loads a JSON IOC feed and checks if known IPs/files/domains appear in logs.
- Returns match dictionary keyed by IOC

### `prompt_firewall.py`
Performs basic string matching to detect prompt injection attempts.
- Searches for phrases like "ignore previous", "pretend", etc.

---

## Data + Threat Feed

- Sample logs simulate real-world ransomware behavior
- Bright Data feed includes IOC metadata:
```json
{
  "192.168.1.100": {
    "Malware": "LockBit",
    "Confidence": "High",
    "LastSeen": "2025-05-21"
  },
  ...
}
```

---

## Dashboard UI (`dashboard_interactive.py`)

- Upload log file → GPT analyzes → timeline appears
- Shows MITRE ATT&CK-style event simulation
- What-if panel lets users explore defense options
- Can export results into PDF/HTML

---

## Use Case Summary

Coffee Bliss uploads a log file → GPT flags LockBit → IP matches in BrightData → Alert triggered → Report exported  
No SOC needed. Just smart automation.

---

## Ready for:

- GitHub Deployment
- Hugging Face Demo
- Poster Submission
- Final Pitch

---

## License

MIT © Dream
