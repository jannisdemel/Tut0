# Geometric Machine Learning in Quantum Chemistry: Tutorium 0

This repository contains the notebooks and data files for Tutorium 0. The
recommended setup is VS Code + GitHub Copilot + `uv`. Advanced users can also
use terminal-based coding agents such as GitHub Copilot CLI, Claude Code, or
OpenAI Codex CLI.

## Recommended setup

### 1. Install Visual Studio Code

Install VS Code from <https://code.visualstudio.com/>.

After installing VS Code, open the Extensions view and install:

- **Python** by Microsoft
- **Jupyter** by Microsoft
- **GitHub Copilot** by GitHub

Sign in to VS Code with your GitHub account when Copilot asks you to. You need a
GitHub account with Copilot access. Students can often get Copilot through the
GitHub Student Developer Pack, but that has to be activated on GitHub first.

Useful Copilot links:

- General GitHub Copilot docs: <https://docs.github.com/en/copilot>
- Copilot in VS Code: <https://docs.github.com/en/copilot/using-github-copilot/asking-github-copilot-questions-in-your-ide?tool=vscode>

### 2. Install uv

We use `uv` to create the Python environment and install the packages for this
repo.

Official `uv` installation instructions:
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

Open a terminal in the repository folder. In VS Code, use
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

After that, continue with:

- `task1/task1_xyz.ipynb`
- `task2/task2_molecule_match.ipynb`

If VS Code cannot find the kernel, run this once:

```bash
uv run python -m ipykernel install --user --name gmlqc-tut0 --display-name "Python (gmlqc-tut0)"
```

Then restart VS Code and select the kernel named `Python (gmlqc-tut0)`.

## Working with AI coding assistants

The expected tool for this tutorial is **GitHub Copilot in VS Code**. If you
already have a ChatGPT or Claude subscription, you may also be able to use
OpenAI Codex or Claude Code. These tools are optional; Copilot in VS Code is
enough for the tutorial.

### GitHub Copilot in VS Code

Use Copilot Chat when you want explanations, debugging help, or hints. Good
prompts for this course:

- "Explain this notebook cell and the error I got."
- "Give me a hint, but do not write the full solution."
- "Check whether my function handles the example molecule correctly."
- "Help me debug this notebook cell step by step."

### Agent mode

Agent mode is for larger tasks where Copilot should inspect files, propose
edits, and sometimes suggest terminal commands. In VS Code, open Copilot Chat
and choose **Agent** from the mode dropdown.

Use Agent mode for tasks such as:

- "Find why this notebook import fails and suggest a fix."
- "Check the task instructions against my solution and point out problems."
- "Refactor this helper function without changing the exercise result."

Be careful: an agent can edit files. Read the diff before accepting changes,
especially in exercise notebooks.

### Plan mode

Plan mode is useful before making changes. Copilot analyzes the task and creates
a plan first, but does not edit files until you review and approve the plan. Use
it when you are unsure what steps are needed or when the task has several parts.

In VS Code, open Copilot Chat and choose **Plan** from the mode dropdown. A good
prompt is:

```text
Make a plan for solving task1. Do not write the solution yet. Identify the files
I should read and the checks I should run.
```

### Instruction files

Instruction files tell Copilot how to behave in this repository. They are useful
for course rules such as "give hints before full solutions" or "prefer simple
notebook code".

GitHub's guide to repository instructions:
<https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions?tool=visualstudio>

This repo already contains instruction files:

- `.github/copilot-instructions.md` applies general repository guidance.
- `.github/instructions/task1-notebook.instructions.md` gives task-specific
  guidance for task 1 notebooks.
- `.github/instructions/task2-notebook.instructions.md` gives task-specific
  guidance for task 2 notebooks.

The general instruction style in this repo was adapted from:
<https://github.com/multica-ai/andrej-karpathy-skills/blob/main/CLAUDE.md>

When Copilot uses repository instructions, they are added automatically. In
Copilot Chat, you can often verify this by checking the response references for
`.github/copilot-instructions.md`.

## Optional tools for existing subscriptions

### If you already have ChatGPT

OpenAI Codex is OpenAI's coding agent. Depending on your ChatGPT plan, you can
use Codex in the terminal, in supported IDEs, in the Codex app, or in the cloud.

- Codex with ChatGPT plans: <https://help.openai.com/en/articles/11369540-codex-in-chatgpt>
- Codex cloud docs: <https://platform.openai.com/docs/codex/overview>
- Codex CLI repository and install notes: <https://github.com/openai/codex>

### If you already have Claude

Claude Code is Anthropic's coding agent. It can run in a terminal and can also
be used from supported editors.

- Claude Code overview: <https://docs.anthropic.com/en/docs/claude-code/overview>
- Claude Code setup: <https://docs.anthropic.com/en/docs/claude-code/getting-started>

## Advanced: command line agents

A **CLI** is a command line interface: a program you run from a terminal by
typing commands. CLI coding agents can read files, suggest or make edits, run
commands, and help debug problems without using the VS Code chat panel.

Only use these if you are comfortable with the terminal and Git. Before asking
an agent to edit files, make sure your important work is saved and check the Git
diff afterwards.

### GitHub Copilot CLI

GitHub Copilot CLI lets you use Copilot directly from the terminal.

- Product page: <https://github.com/features/copilot/cli>
- Install docs: <https://docs.github.com/en/copilot/how-tos/copilot-cli/install-copilot-cli>
- Usage docs: <https://docs.github.com/en/copilot/how-tos/use-copilot-agents/use-copilot-cli>

Install options include:

```bash
npm install -g @github/copilot
```

or, on macOS/Linux with Homebrew:

```bash
brew install copilot-cli
```

Then run:

```bash
copilot
```

### Claude Code CLI

Claude Code lets you use Claude as a coding agent from the terminal.

Install docs: <https://docs.anthropic.com/en/docs/claude-code/getting-started>

Common install command:

```bash
npm install -g @anthropic-ai/claude-code
```

Then run:

```bash
claude
```

### OpenAI Codex CLI

Codex CLI lets you use OpenAI Codex from the terminal.

Install docs and source: <https://github.com/openai/codex>

Install with npm:

```bash
npm install -g @openai/codex
```

or, on macOS with Homebrew:

```bash
brew install --cask codex
```

Then run:

```bash
codex
```

When prompted, sign in with ChatGPT if your plan supports Codex, or configure an
API key if you are using API billing.

## Common problems

### `uv` is not found

Close and reopen the terminal. If it still does not work, restart VS Code. On
Windows, make sure you are using a new PowerShell terminal after installing
`uv`.

### VS Code asks me to install Python

That is normal if VS Code has not detected the environment yet. First run:

```bash
uv sync
```

Then use **Select Kernel** in the notebook and choose the `.venv` environment.

### The notebook uses the wrong Python

Check the selected kernel in the top right of the notebook. It should be the
environment from this repository, not a global Python installation.

### Packages are missing

Run:

```bash
uv sync
```

Then restart the notebook kernel and run the cells again.

## Setup checklist

- VS Code installed
- Python and Jupyter extensions installed in VS Code
- GitHub Copilot extension installed in VS Code
- Signed in to GitHub in VS Code
- `uv --version` works in the terminal
- `uv sync` runs successfully in this repository
- `task0/test_imports.ipynb` runs with the repository kernel
