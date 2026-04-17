# 🎓 Academic Research Agent Team

[![Python](https://img.shields.io/badge/Python-3.11+-blue)](https://www.python.org/)
[![Google ADK](https://img.shields.io/badge/Framework-Google%20ADK-orange)](https://google.github.io/adk-docs/)
[![Gemini](https://img.shields.io/badge/LLM-Gemini%202.5%20Flash%20Lite-green)](https://deepmind.google/technologies/gemini/)
[![Google x Kaggle](https://img.shields.io/badge/Google%20x%20Kaggle-AI%20Agents%20Intensive-20BEFF)](https://www.kaggle.com/learn-guide/5-day-agents)

A Sequential Multi-Agent System that automates comprehensive academic research workflows. Given a broad topic, the pipeline autonomously breaks it into specific research questions, browses the web for current information, and synthesizes everything into a structured, professional report — complete with real citations.

---
## 📸 Demo

> *Add a screenshot or GIF of your terminal output here.*

**Example prompt:** `"How are AI Agents transforming Data Science workflows in 2025?"`

**Actual output from the pipeline:**




---

## 🚀 Project Overview

Instead of relying on a single LLM prompt — which often produces shallow or hallucinated answers — this system orchestrates a "company" of specialized AI agents. Each agent has one job and hands its output to the next, enforcing a strict **Plan → Research → Edit** pipeline that produces grounded, well-structured results.

---

## 🤖 Agent Architecture

This project uses a **Sequential Workflow** with three agents and two tools:

| Agent | Role | Tools |
|---|---|---|
| 🧠 **Planner** | Decomposes a vague topic into 3 specific, executable research questions | None (reasoning only) |
| 🕵️ **Researcher** | Executes each question using live web search, gathering technical details and sources | `google_search` |
| ✍️ **Editor** | Synthesizes raw notes into a clean, structured blog post with citations | None (writing only) |

The `SequentialAgent` orchestrates strict execution order — the Researcher never runs before the Planner finishes, and the Editor only sees the Researcher's verified output.

---

## 🛠️ Tech Stack

| Component | Choice |
|---|---|
| Framework | Google Agent Development Kit (ADK) |
| LLM | Gemini 2.5 Flash Lite |
| Web Search | Google Search (via ADK built-in tool) |
| Language | Python 3.11 |
| Architecture | Sequential Multi-Agent Workflow |
| Environment | Kaggle Notebooks |

---

## ⚡ Quickstart

**1. Clone the repository**
```bash
git clone https://github.com/your-username/academic-research-agent.git
cd academic-research-agent
```

**2. Set up a virtual environment**
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Configure your API key**
```bash
cp .env.example .env
# Open .env and add your Google API key
```

**5. Run the notebook**

Open `notebooks/demo.ipynb` in Jupyter or upload it directly to Kaggle. Make sure to add your `GOOGLE_API_KEY` in **Add-ons → Secrets** before running.

---

## 📁 Repository Structure

```
academic-research-agent/
├── README.md
├── LICENSE
├── .gitignore
├── .env.example              # Template for environment variables
├── requirements.txt          # Pinned dependencies
├── research_agent/
│   ├── __init__.py
│   ├── agent.py              # SequentialAgent pipeline definition
│   ├── planner.py            # Planner agent
│   ├── researcher.py         # Researcher agent + tool definitions
│   └── editor.py             # Editor agent
├── notebooks/
│   └── demo.ipynb            # Full Kaggle notebook (runnable)
├── outputs/
│   └── .gitkeep              # Sample report outputs (git-ignored)
└── assets/
    └── architecture.png      # Pipeline diagram for README
```

---

## 🔑 Environment Variables

Create a `.env` file from the template:

```bash
cp .env.example .env
```

| Variable | Description |
|---|---|
| `GOOGLE_API_KEY` | Your Google Gemini API key from [Google AI Studio](https://aistudio.google.com/) |

> ⚠️ Never commit your `.env` file. It is already listed in `.gitignore`.

---

## 📦 Dependencies

```
google-adk
```

> Run `pip freeze > requirements.txt` in your environment to pin exact versions before publishing.

---

## 🏆 Acknowledgements

This project was built as the Capstone for the **[Google × Kaggle AI Agents Intensive (2025)](https://www.kaggle.com/learn/ai-agents-intensive)** — a 5-day intensive course on designing, building, and deploying AI agent systems.
