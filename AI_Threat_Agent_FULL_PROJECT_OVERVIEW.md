AI_Threat_Agent/
├── app/
│   ├── dashboard.py                # Streamlit dashboard หลัก (timeline + what-if analysis)
│   └── dashboard_interactive.py    # Dashboard เวอร์ชั่น interactive (MITRE timeline, threat summary)
│
├── modules/
│   ├── threat_phase_analyzer.py    # วิเคราะห์ phase ด้วย GPT-4 (MITRE ATT&CK mapping)
│   ├── brightdata_correlator.py    # ตรวจจับ IOC จาก Bright Data feed ใน logs
│   └── prompt_firewall.py          # ตรวจจับ prompt injection (regex/keyword)
│
├── data/
│   ├── sample_logs/
│   │   ├── lockbit_log.txt         # ตัวอย่าง log: LockBit
│   │   ├── revil_log.txt           # ตัวอย่าง log: REvil ransomware
│   │   └── blackcat_log.txt        # ตัวอย่าง log: BlackCat/ALPHV
│   └── brightdata_feed.json        # Mock IOC threat feed จาก Bright Data
│
├── export/
│   └── reports/                    # โฟลเดอร์สำหรับ export incident report (HTML/PDF)
│
├── tests/
│   └── test_module_integrity.py    # Unit test ตรวจสอบ module ต่างๆ
│
├── .env.example                    # ตัวอย่างไฟล์ env (set OPENAI_API_KEY, BrightData key)
├── requirements.txt                # Python dependencies (streamlit, openai, etc.)
├── run.sh                          # Bash script สำหรับรัน dashboard
├── docker-compose.yml              # Docker orchestration (API + frontend)
├── README.md                       # คู่มือโปรเจกต์, วิธีใช้งาน, quick start
├── use_case.md                     # Business use-case: ransomware (Coffee Bliss)
└── LICENSE                         # MIT License © Dream
