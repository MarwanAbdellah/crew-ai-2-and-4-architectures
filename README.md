# 🤖 Multi-Agent Architectures with CrewAI (2-Bot & 4-Agent)

End-to-end **CrewAI** setups tracked with **AgentOps**:
- **Session Rebuild Crew** – rebuilds a codebase from a recorded session and writes docs.
- **Content Creation Crew (4 Agents)** – Writer, Summarizer, Fact-Checker, Metadata.

---

> Note: Open the notebooks and run cells top-to-bottom to execute the crews and write outputs.

**URL** = https://github.com/MarwanAbdellah/crew-ai-2-and-4-architectures

---

## 🧠 Overview

This project demonstrates two multi-agent workflows. The first reconstructs a project from a recorded session and produces a step-by-step guide + summary. The second turns that project into high-quality content (article, TL;DR, fact report, and SEO metadata). Runs are optionally tracked with AgentOps.

---

## 📁 Project Structure

```
crew-ai-2-and-4-architectures/
├── 2-bots_architecture/
│   └── 2_agents_architecture.ipynb
├── 4-bots_architecture/
│   └── 4_agents_architecture.ipynb
├── content/                 # article, tldr, facts, metadata (outputs)
├── docs/                    # step-by-step rebuild guides (outputs)
├── reports/                 # rebuild summaries (outputs)
├── .env.example
├── README.md
├── .gitignore
└── LICENSE
```

---

## 👥 Crews & Outputs

### Crew 1 — Session Rebuild Crew
**Role:** Rebuild the codebase from a recorded session and document it.  
**Outputs:**  
- Reconstructed code (e.g., in a `rebuild/` folder)  
- `docs/rebuild_guide.md` (step-by-step)  
- `reports/rebuild_summary.md`

### Crew 2 — Content Creation Crew (4 Agents)
- **Writer Agent:** long, structured article  
- **Summarizer Agent:** bullets + TL;DR  
- **Fact-Checker Agent:** technical accuracy report  
- **Metadata Agent:** SEO title, description, tags, and JSON metadata

**Outputs:**  
- `content/article.md`  
- `content/tldr.md`  
- `content/facts_report.md`  
- `content/metadata.json`

---

## 🛠 Requirements

- Python **3.10+**  
- **CrewAI**  
- (Optional) **AgentOps** for run tracking  
- An LLM provider key (e.g., `OPENAI_API_KEY`)

**Install:**
```bash
pip install crewai "crewai[tools]"
```

---

## 🔐 Environment

Create a `.env` or export variables in your shell:

```bash
OPENAI_API_KEY=your_openai_key
# or GROQ_API_KEY / ANTHROPIC_API_KEY / GEMINI_API_KEY if configured
AGENTOPS_API_KEY=your_agentops_key   # optional
PROJECT_ROOT=/absolute/path/to/repo
```

---

## ▶️ How to Run (Notebooks)

1) Open the notebook you want (e.g., `4-bots_architecture/4_agents_architecture.ipynb`).  
2) Run all cells.  
3) Check the generated files under `content/`, `docs/`, and `reports/`.

**Export to script (optional):**
```bash
jupyter nbconvert --to script 4-bots_architecture/4_agents_architecture.ipynb
python 4-bots_architecture/4_agents_architecture.py
```

---

## 🧩 Customization

- **Models/Providers:** switch using env vars or config cells.  
- **Prompts/Tasks:** edit agent roles and task prompts directly in the notebook.  
- **IO Paths:** change output folders (e.g., `content/`, `docs/`, `reports/`).

---

## 🐙 AgentOps (Optional)

1) Add `AGENTOPS_API_KEY` to `.env`.  
2) Initialize AgentOps in the first cells of the notebook.  
3) Review traces/runs in your AgentOps dashboard.

---

## 📦 Suggested .gitignore

```
__pycache__/
.venv/
.env
rebuild/
data/
*.log
.ipynb_checkpoints/
```

---

## 📬 Contact

**Marwan Abdellah**  
📧 marawan.abdellah0@gmail.com  
🔗 GitHub: https://github.com/MarwanAbdellah
