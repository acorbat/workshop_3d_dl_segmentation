# AI Coding Agent Instructions

These instructions help AI agents work productively in this repository by documenting the current architecture, environment, and workflows.

## Project Overview
- Purpose: Workshop scaffold for 3D Deep Learning Segmentation workflows and data exploration.
- Minimal codebase: Contains environment config and data download; no Python source files yet.
- Key files: See [pixi.toml](pixi.toml) and [data/](data/).

## Environment & Dependencies
- Package manager: Pixi (Conda-based) using channel `conda-forge`.
- Platforms: Multi-OS — `win-64`, `linux-64`, `osx-64`, `osx-arm64` (see [pixi.toml](pixi.toml)).
- Python: `3.13.*`.
- Visualization: `napari >=0.6.6,<0.7`.
- Install environment: Run `pixi install` from the repo root.

## Data Workflow
- Dataset: `data/Lund.tif` (downloaded from Zenodo).
- Download task: Defined as `download-data` in [pixi.toml](pixi.toml).
- Command: `pixi run download-data` (uses `curl` and creates `data/` if missing).
- Current state: [data/](data/) contains `Lund.tif`.

## Commands & Tasks
- Run a task: `pixi run <task-name>`.
- Example: `pixi run download-data`.
- Open dataset in Napari GUI (if `napari` console script is available): `pixi run napari data/Lund.tif`.
- Notes:
  - `curl` is available on macOS/Linux by default; on Windows, use recent builds or PowerShell `Invoke-WebRequest` if `curl` is unavailable.
  - Pixi reads tasks from `[tasks]` in [pixi.toml](pixi.toml).
  - On non-Windows platforms, `pixi install` resolves only the current OS; the lock can still include multiple `platforms` for CI or cross-platform publishing.

## Conventions & Patterns
- Environment is declared in `pixi.toml`; prefer adding dependencies there rather than ad-hoc `pip`.
- Use Pixi tasks for repeatable CLI workflows (downloads, preprocessing, launches).
- Keep data under [data/](data/); reference files via relative paths.
- Target compatibility with Python 3.13 and Napari `<0.7`.

## Extending the Repo (Discoverable Patterns)
- Add new tasks under `[tasks]` in [pixi.toml](pixi.toml). Example pattern:
  
  ```toml
  [tasks]
  # existing
  download-data = "curl -L <url> --output data/<file> --create-dirs"
  # add more repeatable commands, e.g., launch scripts or preprocessing
  preprocess = "python scripts/preprocess.py data/Lund.tif data/processed/Lund.npy"
  ```
  
- When adding Python scripts or notebooks:
  - Place code under `scripts/` or `notebooks/` (choose one, be consistent).
  - Ensure imports match `pixi.toml` dependencies.
  - Add a Pixi task to run them (e.g., `pixi run preprocess`).

## Integration Points
- Napari is the primary visualization tool; use it to inspect `tif` volumes.
- Data readers: If programmatic loading is needed, add `tifffile` or `imageio` via `pixi add <package>` and document the new task.

## Common Pitfalls
- Changing Python/Napari versions: Verify plugin compatibility before bumping constraints.
- Missing CLI scripts: If `napari` command is unavailable, use a small Python script to `import napari` and `viewer.add_image(...)`, then run it via a Pixi task.
- Platform drift: Keep `platforms` in [pixi.toml](pixi.toml) aligned with the OSes you intend to support (Windows, Linux, macOS Intel/Apple Silicon).

---

Questions or gaps?
- This repo currently lacks source code and tests; if you add them, prefer repeatable Pixi tasks and update this document with concrete commands.
- Please share feedback on unclear sections or missing workflows so we can iterate.
