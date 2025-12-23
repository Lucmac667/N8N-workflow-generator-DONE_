# 🤖 n8n AI Workflow Generator — Agent Planning Phase

This repository is the **planning and setup phase** for building an **AI-powered n8n JSON generator agent**.

> The agent will take natural language descriptions of automation tasks and convert them into fully valid, importable **n8n workflow JSON** — including nodes, connections, placeholders, and error handling.

This project uses **GitHub Codespaces** and is designed for **GitHub Copilot** (Pro plan) or similar GitHub Agents — no OpenAI key required.

---

## ✅ Project Goals

- [x] Set up a clean development environment in Codespaces or locally with VS Code
- [x] Prepare reusable components (modular code primitives)
- [x] Embed the full system prompt spec for AI behavior
- [x] Scaffold file/folder structure — **no business logic yet**
- [x] Plan for smooth transition into coding phase

---

## 🧰 Development Environment

This project is prepped for **full-stack agent building** with:

### 🐍 Python

- Python 3.11+
- `black`, `ruff` for linting/formatting
- `pytest` for testing
- `pydantic` or `dataclasses` for schema modeling
- Optional: `langchain`, `litellm`, or `instructor` for structured LLM output

### 🟢 Node.js & JavaScript

- Node.js LTS (latest)
- `npm` (latest)
- `typescript` (optional)
- `eslint`, `prettier` for JS/TS linting

### 🧪 Tools & Dev Support

| Tool       | Purpose                         |
|------------|---------------------------------|
| Copilot    | GitHub Pro Copilot integration  |
| Codespaces | Zero-config dev environment     |
| Python     | LLM agent and orchestration     |
| Node/npm   | Optional integrations if needed |
| Markdown   | Spec + planning documentation   |

---

## 📁 Project Structure (Initial Scaffolding)

```bash
n8n-generator/
├── src/
│   ├── parser/                # NLP → steps
│   ├── nodes/                 # Node builders
│   ├── connections/           # Graph logic
│   ├── renderer/              # Final JSON builder
│   └── tests/
├── docs/
│   └── n8n_generator_spec.md  # Full agent behavior spec
├── examples/
│   └── sample_tasks.txt       # Test input prompts
├── .devcontainer/
│   └── devcontainer.json      # Codespace setup
├── .github/
│   └── workflows/
│       └── lint-test.yml      # CI checks (optional)
├── main.py                    # CLI entrypoint
├── requirements.txt           # Python deps
├── package.json               # Node deps (optional)
└── README.md
```

---

## 🔌 Modular Code Primitives (MCPs)

These are reusable building blocks the agent will use:

| Module             | Purpose                                             |
|-------------------|-----------------------------------------------------|
| `TaskParser`       | Parse natural language into steps                  |
| `NodeFactory`      | Create nodes with placeholder configs              |
| `ConnectionGraph`  | Wire nodes into valid n8n graph                    |
| `PlaceholderHelper`| Inject `{{PLACEHOLDER}}` values                   |
| `ErrorHandler`     | Add IF + Set nodes for error branches              |
| `WorkflowBuilder`  | Assemble final JSON object                         |
| `JSONValidator`    | Confirm valid n8n structure                        |

---

## 🧠 Agent Behavior (Planned, Not Implemented Yet)

> The agent will receive a plain-English automation description like:
> 
> `When a new Google Sheet row is added, send data to CRM and notify on Slack if error.`

It will then:

- Identify steps
- Select correct n8n node types
- Create parameterized node objects
- Wire them using `connections`
- Add placeholder values
- Add error handling logic
- Output a clean `JSON` object like this:

```json
{
  "name": "Google Sheet to CRM",
  "nodes": [...],
  "connections": {...},
  "settings": {},
  "version": 2
}
```

📄 The full behavior spec is in: `docs/n8n_generator_spec.md`

---

## 🚀 Planning Tasks

Use this checklist to guide initial work:

- [ ] Initialize Python environment (see below)
- [ ] Scaffold all `src/` MCPs as empty files with docstrings
- [ ] Add placeholder `main.py` CLI:
  ```bash
  python main.py --task "When a form is submitted..."
  ```
- [ ] Create sample inputs in `examples/sample_tasks.txt`
- [ ] Copy full system prompt into `docs/n8n_generator_spec.md`
- [ ] (Optional) Add Codespace devcontainer for consistent setup

---

## 🧪 Sample Dev Setup Commands

### Python

```bash
python -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

Example `requirements.txt`:

```txt
openai
pydantic
typer
black
ruff
pytest
```

### Node.js (Optional)

```bash
npm install --save-dev eslint prettier typescript
npx eslint --init
```

---

## ✅ Success Criteria for Planning Phase

- Environment runs in Codespaces or local VS Code
- All core files exist, with placeholder logic and docstrings
- System prompt is embedded in project
- Copilot/Agent can now start helping write core logic

---

## 🔐 Auth

This project is designed for **GitHub Pro** users using:

- GitHub Copilot Chat or Agents
- GitHub token-based authentication
- No OpenAI API keys are required unless you later add them

---

## 📌 Next Steps (After Planning)

Once setup is complete, you will:

1. Implement `TaskParser` and test with simple tasks
2. Generate node templates using `NodeFactory`
3. Combine nodes and connections in `WorkflowBuilder`
4. Validate and output final JSON

> ✅ All logic should follow the system prompt spec in `docs/n8n_generator_spec.md`

---


