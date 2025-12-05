# au-adatom-bayesopt

  Bayesian optimization of an Au adatom on vicinal Au(433) using EMT (ASE/asap3) and Gaussian-process surrogates. Includes dense PES mapping, local L-BFGS-B
  search, Bayesian optimization sweeps over β, and exploratory GP modeling of diffusion barriers.

  ## Layout
  - assignments/project-2b/project2b_bayesopt_solution.ipynb — executed notebook with code, figures, and summary outputs.
  - assignments/project-2b/report.tex — report ready for LaTeX compilation.
  - assignments/project-2b/artifacts/ — cached PES grid, figures, and summary metrics.
  - assignments/project-2b/.venv312/ — Python 3.12 virtual environment with dependencies.

  ## Quick start
  1) Activate the venv: `source assignments/project-2b/.venv312/bin/activate`
  2) Re-run notebook (from repo root):

  JUPYTER_CONFIG_DIR=assignments/project-2b/artifacts/jupyter_config \
  JUPYTER_DATA_DIR=assignments/project-2b/artifacts/jupyter_data \
  JUPYTER_RUNTIME_DIR=assignments/project-2b/artifacts/jupyter_runtime \
  assignments/project-2b/.venv312/bin/jupyter nbconvert --to notebook --execute --inplace \
  assignments/project-2b/project2b_bayesopt_solution.ipynb --ExecutePreprocessor.kernel_name=python3 --ExecutePreprocessor.timeout=7200

  3) Build the report: `pdflatex assignments/project-2b/report.tex` (or `latexmk`).

  ## Results (executed)
  - Global min: x=3.42 Å, y=0.75 Å, E=0.228 eV.
  - Local search: 2/250 hits (0.8%).
  - BO: β=2.0 best robustness (100% hits ~21 iterations); large β over-explores.
  - Exploratory GP: RMSE ≈0.035 eV vs EMT grid; path barrier 0.88 eV (matches EMT).

  ## Reproducibility
  - Data/figures in `assignments/project-2b/artifacts/`.
  - Metrics in `assignments/project-2b/artifacts/summary.json`.
  - Code and text explanations live in the notebook; the LaTeX report summarizes methods and findings.
