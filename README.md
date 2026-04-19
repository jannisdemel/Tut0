# GMLQC Tutorial Environment

This project uses `uv` to create and manage the Python virtual environment.

## Install uv

If `uv` is not installed yet, install it with:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Then restart your terminal, or make sure the `uv` command is available:

```bash
uv --version
```

## Create the virtual environment

From this project folder, run:

```bash
uv sync
```

This creates a `.venv` folder and installs the packages listed in `pyproject.toml`.

## Activate the environment

On macOS or Linux:

```bash
source .venv/bin/activate
```

On Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

## Run the test notebook

After activating the environment, open Jupyter:

```bash
jupyter notebook
```

Then open `test_imports.ipynb` and run the cell. It should import NumPy, pandas, and Matplotlib, then print:

```text
hello world
```

You can also run commands without manually activating the environment by prefixing them with `uv run`, for example:

```bash
uv run jupyter notebook
```
