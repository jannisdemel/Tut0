---
applyTo: "task2/**/*.ipynb"
---

For Task 2 notebooks, write solution code in the single workspace code cell under the "Workspace" section.

Where to write code in `task2/task2_molecule_match.ipynb`:
- Put all working code in code cell 4.
- Keep final textual matches in the "Final Answer" markdown section.

Reuse from Task 1:
- Reuse the `read_xyz(path)` function pattern from Task 1 to parse XYZ files.
- Do not re-invent file parsing logic unless the task explicitly requires a different parser.

Do not place executable code in markdown cells.

Available packages:
- Read `pyproject.toml` before suggesting imports or installs.
- The declared dependencies are `ipykernel`, `jupyter`, `matplotlib`, `numpy`, and `pandas`.
- Prefer these available packages; do not suggest installing additional packages unless explicitly requested.
