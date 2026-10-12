# HDB DE Technical Test

## Project Overview

This repository contains the solution for the Data Engineering Technical Test. The project is structured to keep code, data, and answers organized and reproducible using **uv** as the Python package manager.

## Folder Structure

```
.
├── answers/          # Contains the two answer files addressing different parts of the assessment
├── data/             # Input and output datasets used during the analysis
├── diagrams/         # Architecture diagrams in Mermaid markdown (.mmd) format for Part 2
├── .venv/            # Virtual environment (ignored by git)
├── Data Engineering Technical Test.pdf # Original assessment document (ignored by git)
├── pyproject.toml    # Project dependencies and metadata
├── uv.lock           # Locked dependency versions for reproducibility
└── .gitignore        # Specifies intentionally untracked files to ignore
```

### Folder Descriptions

- **answers/**
  Contains the two answer files for the assessment:

  - `Submission_Part_1.ipynb`: Jupyter notebook with analysis for Part 1.
  - `Submission_Part_2.pdf`: Presentation deck for Part 2.
- **data/**
  Stores raw data downloaded or generated, as well as any intermediate or processed data files.
  *(Add subfolders like `raw/` and `processed/` as needed.)*
- **diagrams/**
  Contains the Mermaid markdown (`.mmd`) files for the architecture diagrams required in Part 2 of the assessment.

## Where the Answers Are

The answer files are located in the `answers/` directory:

- `answers/Submission_Part_1.ipynb`
- `answers/Submission_Part_2.pdf`

## Re‑creating the Environment with **uv**

This project uses **uv** to manage Python dependencies and ensure reproducible environments.

### Prerequisites

1. Install **uv** (if not already installed):

   ```bash
   # Using the official installer
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

   Or follow the installation guide at https://github.com/astral-sh/uv.

### Setup Steps

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd HDB_DE_TT   # or your repo name
   ```
2. Synchronize the project to install the exact dependencies:

   ```bash
   uv sync
   ```

   This reads `pyproject.toml` and `uv.lock` to create a virtual environment (`.venv/`) and install all packages.
3. Activate the environment (optional, as uv can run commands directly):

   ```bash
   source .venv/bin/activate   # on Unix/macOS
   .\.venv\Scripts\activate    # on Windows
   ```

   Or run scripts via `uv run <command>` without activation.

### Running Notebooks using **uv**

After setting up the environment with `uv sync`, activate the virtual environment:

```bash
source .venv/bin/activate   # on Unix/macOS
.\.venv\Scripts\activate    # on Windows
```

Then launch Jupyter Notebook (or JupyterLab) and open the notebook(s) in the `answers/` directory.

> **Important:** When opening a notebook, you must select the correct kernel to ensure it uses the project's dependencies:
> 1. In the notebook toolbar, click on **Kernel** → **Change kernel** → **Python Environments**
> 2. Look for the environment named `hdb-tt-env` (or the name of your project's virtual environment) and select it.
> 
> This ensures that the notebook runs with the exact dependencies installed by `uv`.

Alternatively, you can run notebooks directly from the command line using `uv run`:

```bash
uv run jupyter notebook
```

Then follow the same kernel selection steps above.

## Dependency Files

- **pyproject.toml** – defines project metadata and dependency specifications.
- **uv.lock** – records the exact versions of dependencies resolved at lock‑time; commit this to guarantee reproducibility.

> **Important:** Both `pyproject.toml` and `uv.lock` are **tracked** by Git (not ignored) so that anyone cloning the repo can recreate the exact same environment.

## Final .gitignore Check

The current `.gitignore` ensures that:

- The virtual environment (`.venv/`) is excluded.
- Build artifacts, caches, and distribution folders are excluded.
- The original assessment PDF (`Data Engineering Technical Test.pdf`) is excluded.
- **Crucially**, `pyproject.toml` and `uv.lock` are **not** ignored, allowing a fresh clone to recover the dependency information needed for `uv sync`.

You can verify with:

```bash
git status --ignored
```

The ignored list should show `.venv/` and the PDF, but **not** `pyproject.toml` or `uv.lock`.

---

* [ ] Feel free to reach out if you have any questions!
