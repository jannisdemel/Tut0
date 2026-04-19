---
applyTo: "task2/**/*.ipynb"
---

For Task 2 notebooks, write solution code under the "Your solution" section. You can split
it into multiple cells if needed, but make sure to keep the code organized and well-commented.


Reuse from Task 1:
- Reuse the `read_xyz(path)` function pattern from Task 1 to parse XYZ files.
- Do not re-invent file parsing logic unless the task explicitly requires a different parser.

Do not place executable code in markdown cells.

Available packages:
- Read `pyproject.toml` before suggesting imports or installs.
- The declared dependencies are `ipykernel`, `jupyter`, `matplotlib`and `numpy`.
- Prefer these available packages; do not suggest installing additional packages unless explicitly requested.

Plan mode:
- If we need are in plan mode to plan the solution, ask questions to clarify the task and get user input.

The final solution (so the four found molecules) should be placed in the markdown cell under the "Final answer" section.

Ignore the section "Extra task" for now as it is only if there is time left. Only work on it if specifically propmpted. If working on it though, you do not need to use only the declared dependencies.
