---
applyTo: "task2/**/*.xyz"
---

These files use the standard XYZ molecular geometry format.

Interpret the file structure as:
1. Line 1: integer atom count.
2. Line 2: free-text molecule label/comment.
3. Remaining lines: one atom per line in the form `Element x y z`.

Coordinate handling rules:
- Treat coordinates as Cartesian 3D positions.

Units:
- No explicit unit metadata is present in the repository XYZ files.
- Use Angstrom as the default coordinate unit, which is the standard XYZ convention.

