# Multi-Agent AI System for Document Classification and Routing

## Project Overview

This project implements a multi-agent AI system that:
- Accepts documents in PDF, JSON, or email (text) format
- Classifies the format and intent (e.g., Invoice, RFQ, Complaint)
- Routes the input to the appropriate agent (JSON Agent, Email Agent)
- Maintains shared context for traceability using a memory store

## Table of Contents
- [Tech Stack](#-tech-stack)
- [Folder Structure](#-folder-structure)
- [How to Run](#-how-to-run)
- [Agents](#-agents)
- [Sample Inputs](#-sample-inputs)
- [Contributing](#-contributing)

## Tech Stack
- Language: Python 3
- Platform: Google Colab (Jupyter Notebook)
- Memory Store: Simulated Redis (in-memory using Python dictionary)
- Classifier: Rule-based format and intent detection

## How to Run
1. [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Keerthana-Uppanda/Multi_Agent_Ai_System/blob/main/MultiagentAISystem.ipynb)
2. Run each cell in order:
   - Set up format and intent classifiers
   - Define memory storage
   - Create and route documents
   - Test with sample inputs

## Agents
- Classifier Agent: 
  - Detects document format (PDF, JSON, Email)
  - Classifies intent (Invoice, RFQ, Complaint, Regulation)
  - Routes to the appropriate agent
- JSON Agent: 
  - Processes structured JSON payloads
  - Extracts and reformats data
  - Flags anomalies or missing fields
- Email Agent: 
  - Extracts sender, subject, and urgency
  - Formats for CRM-style usage

## Folder Structure
multi-agent-ai-system/
│
├── data/                   # Sample input documents (PDFs, JSONs, Emails)
│   ├── samples/
│   │   ├── sample_invoice.json
│   │   ├── sample_rfq_email.txt
│   │   └── sample_document.pdf
│
├── notebooks/              # Jupyter notebooks
│   └── MultiagentAISystem.ipynb
│
├── agents/                 # Agent implementations
│   ├── classifier_agent.py
│   ├── json_agent.py
│   └── email_agent.py
│
├── memory/                 # Memory store implementation (in-memory Redis simulation)
│   └── memory_store.py
│
├── utils/                  # Utility functions (parsing, format detection)
│   └── helpers.py
│
├── tests/                  # Unit tests for agents and utilities
│   ├── test_classifier_agent.py
│   ├── test_json_agent.py
│   └── test_email_agent.py
│
├── requirements.txt        # Project dependencies
├── README.md               # Project documentation (this file)
└── LICENSE                 # (Optional) License file


## Sample Inputs
- Email RFQ Example:
  - ID: 202245
  - Amount: 5000
  - Email: uppandakeerthana@gmail.com
  - Intent: RFQ

- Invoice JSON Example:
  ```json
  {
    "id": "INV-456",
    "amount": 1500,
    "customer": "Acme Corp",
    "due_date": "2025-06-01"
  }

## 🤝 Contributing

Contributions are welcome! If you'd like to improve this project, please:

1. *Fork the repository*

2. *Create a feature branch*  
   ```bash
   git checkout -b feature-name
3.*Commit the changes*
  ```bash
   git commit -m 'Add some feature'
4.*Push to the branch*
```bash
git push origin feature-name
