# Live-Cell-CaTrigger-Imaging-Analysis

End-to-end workflow for quantitative subcellular calcium imaging analysis. This repository combines **CellProfiler** pipelines for segmentation and feature extraction with **Python** post-processing for photobleaching correction, F/F₀ normalization, per-cell time-series extraction, and aggregation across experiments and cell lines.

## Contents
- `cellprofiler/` – CellProfiler pipelines (`.cppipe`) and (optionally) example project files
- `python/` – Post-processing scripts (F/F₀ export, plotting, aggregation)
- `examples/` – Optional example inputs/outputs (small, anonymized)
- `figures/` – Generated plots for QC and analysis
- `docs/` – Notes on experimental setup, channel naming conventions, etc.

> Adjust folder names to match your repo structure.

## Workflow overview
1. **Run CellProfiler** to segment cells/regions and export per-object intensity measurements per frame.
2. **Run Python post-processing** to:
   - merge tracking information (TrackID)
   - filter cells by positivity criteria (per channel)
   - optionally correct photobleaching
   - compute **F/F₀** per cell and frame
   - export per-experiment per-cell tables and summary plots

## Requirements
- CellProfiler (recommended: 4.x or later)
- Python 3.9+ (tested with standard scientific stack)

Python dependencies:
- numpy
- pandas
- matplotlib

Install (example):
```bash
pip install numpy pandas matplotlib
