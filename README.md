# DIY Repair Data Generator + LLM Judge

This project generates structured DIY repair Q/A records and evaluates them with an LLM-as-judge workflow.

## Prerequisites

- `pyenv` installed
- Python `3.13.2` available in `pyenv`
- OpenAI API key

## Setup (pyenv + venv)

```bash
pyenv install 3.13.2
pyenv local 3.13.2
python -m venv .venv
```

Activate the virtual environment:

- PowerShell:
```powershell
.venv\Scripts\Activate.ps1
```

- Bash:
```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Environment Variables

Create a `.env` file in project root with:

```env
OPENAI_API_KEY=your_api_key_here
OPENAI_MODEL=gpt-4.1-mini
OPENAI_JUDGE_MODEL=o4-mini
```

## Run

Generate dataset:

```bash
python data-creation.py --count 50 --output diy_repair_data.jsonl
```

Judge dataset:

```bash
python judge.py --input diy_repair_data.jsonl --output judge_results.jsonl
```
