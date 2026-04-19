# Geometric Machine Learning in Quantum Chemistry: Tutorium 0

This repository contains the notebooks and data files for Tutorium 0. 

## What you need to install

### 1. Visual Studio Code

Install VS Code from <https://code.visualstudio.com/>.

After installing VS Code, open the Extensions view and install:

- **Python** by Microsoft
- **Jupyter** by Microsoft
- **GitHub Copilot** by GitHub

Sign in to VS Code with your GitHub account when Copilot asks you to. You need a
GitHub account with Copilot access. Students can get Copilot through the
GitHub Student Developer Pack, but that has to be activated on GitHub first.

### 2. uv

We use `uv` to create the Python environment and install the packages for this
repo.

Install `uv` from the official instructions:
<https://docs.astral.sh/uv/getting-started/installation/>

Quick install commands:

macOS / Linux:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```


Windows PowerShell:

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

After installing, close and reopen your terminal, then check:

```bash
uv --version
```

### 3. Python

This repo needs Python 3.11 or newer.

You do **not** need to install Python separately if you use `uv`. `uv` can
download and manage Python for you. To make sure a suitable Python is available,
run:

```bash
uv python install 3.11
```

If you already have Python 3.11 or newer installed, that is also fine. `uv` will
usually find and use it automatically.

## Set up this repository

Open a terminal in the repository folder. In VS Code, you can use
**Terminal > New Terminal**.

Run:

```bash
uv sync
```

This creates a local `.venv` folder and installs the packages listed in
`pyproject.toml`.

Then test the setup:

```bash
uv run python -c "import numpy, matplotlib, jupyter, ipykernel; print('setup ok')"
```

If you see `setup ok`, the Python environment works.

## Run the notebooks in VS Code

1. Open this folder in VS Code.
2. Open `task0/test_imports.ipynb`.
3. Click **Select Kernel** in the top right of the notebook.
4. Choose the environment from this repository. It will usually be called
   `.venv`, `gmlqc-tut0`, or something similar.
5. Click **Run All**.


## Setup checklist

- VS Code installed
- Python and Jupyter extensions installed in VS Code
- GitHub Copilot extension installed in VS Code
- Signed in to GitHub in VS Code
- `uv --version` works in the terminal
- `uv sync` runs successfully in this repository
- `task0/test_imports.ipynb` runs with the repository kernel
