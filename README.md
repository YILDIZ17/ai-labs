# AI Labs

Personal repository for AI-related work : data science, machine learning, and experiments.

- **Courses:** `notebooks/courses/` : Python, data science, machine learning (NumPy, pandas, visualization, regression, etc.)
- **Projects:** `notebooks/projects/` : End-to-end experiments (e.g. [Weather WW2](notebooks/projects/WeatherWW2) : daily temperature prediction with linear regression)

## Installation

**Prerequisites:** Python 3.7+, pip

1. Clone or go to the project folder, then create and activate a virtual environment:

   **Windows:**

   ```bash
   python -m venv .venv
   .venv\Scripts\activate
   ```

   **Linux / Mac:**

   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```

2. Install dependencies and run Jupyter:

   ```bash
   pip install -r requirements.txt
   jupyter notebook
   ```

   Or use `jupyter lab` instead of `jupyter notebook`.

Open notebooks from `notebooks/courses/<course>/` or `notebooks/projects/<project>/`.

## Project structure

```
ai-labs/
├── apps/ # Demos (Streamlit, Gradio, etc.)
├── configs/ # Experiment configs (YAML, JSON)
├── data/ # Datasets
├── docs/ # Notes, cheatsheets
├── models/ # Saved models (folder kept, contents not versioned)
├── notebooks/
│   ├── courses/
│   │   ├── python/
│   │   ├── data-science/
│   │   └── machine-learning/
│   └── projects/
│       └── WeatherWW2/ # Daily temperature prediction (EDA → linear regression)
├── scripts/ # Reusable Python scripts
├── requirements.txt
├── .gitignore
└── README.md
```

**Git ignores:** `.venv/`, `__pycache__/`, `.ipynb_checkpoints`, `models/*` (except `.gitkeep`), `.DS_Store`, `*.log`, etc.

## Author

[Tümay YILDIZ](https://github.com/YILDIZ17)
