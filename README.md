# AI'Labs

Personal repo for all my AI-related notebooks and projects: data science, machine learning, experiments.

- Data analysis and visualization
- Classification, regression, clustering
- Reusable scripts, configs, demos

Notebooks are organized by course in `notebooks/courses/` (e.g. **data-science**, **machine-learning**).

## Installation

### Prerequisites

- Python 3.7 or higher
- pip

### Steps

1. **Navigate to the project folder:**

```bash
cd ai-labs
```

2. **Create and activate the virtual environment (Windows):**

```bash
python -m venv .venv
.venv\Scripts\activate
```

On Linux/Mac:

```bash
python -m venv .venv
source .venv/bin/activate
```

3. **Install dependencies:**

```bash
pip install -r requirements.txt
```

4. **Launch Jupyter:**

```bash
jupyter notebook
```

Or Jupyter Lab:

```bash
jupyter lab
```

Open notebooks from `notebooks/courses/<course-name>/` or `notebooks/experiments/`.

## Project Structure

```
ai-labs/
├── apps/                   # Demos (Streamlit, Gradio, etc.)
├── configs/                # Experiment configs (YAML, JSON)
├── data/                   # Datasets
├── docs/                   # Notes, cheatsheets, doc
├── models/                 # Saved models (not versioned if large)
├── notebooks/
│   ├── courses/            # By course
│   │   ├── data-science/
│   │   └── machine-learning/
│   └── experiments/        # Experiments
├── scripts/                # Reusable Python scripts
├── requirements.txt       # Python dependencies
├── .gitignore
└── README.md
```

### What's ignored by Git

- **Environment:** `.venv/`, `venv/`, `env/`, `.env`, `.env.local`
- **Python:** `__pycache__/`, `*.pyc`, `dist/`, `build/`, `*.egg-info/`
- **Jupyter:** `**/.ipynb_checkpoints`
- **Models:** contents of `models/` (large files); the folder is kept via `models/.gitkeep`
- **OS:** `.DS_Store`, `Thumbs.db`
- **Other:** `*.log`, `.cache/`

## Author

- [Tümay YILDIZ](https://github.com/YILDIZ17)
