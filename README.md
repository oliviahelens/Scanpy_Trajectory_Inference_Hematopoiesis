# Scanpy Trajectory Inference Mouse Hematopoiesis
rajectory inference for mouse hematopoiesis using Scanpy's PAGA workflow. Reconstructs myeloid and erythroid differentiation paths from the [Paul et al. (2015)](https://doi.org/10.1016/j.cell.2015.11.013) bone marrow dataset, with graph denoising, diffusion pseudotime, and gene expression tracking along lineage trajectories.

## Overview

This notebook walks through:

- Preprocessing with `scanpy.pp.recipe_zheng17`
- Graph denoising via diffusion maps
- Louvain clustering and manual cell type annotation
- PAGA graph construction to visualize cluster connectivity
- Diffusion pseudotime from a stem cell root
- Gene expression dynamics along erythrocyte, neutrophil, and monocyte differentiation paths

## Getting Started

- GitHub Codespaces (4-core / 16 GB RAM recommended) or local environment

### Installation

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install 'scanpy[leiden]' pooch scikit-image ipykernel
python -m ipykernel install --user --name=venv --display-name "Python (.venv)"
```

### Running

Open `main.ipynb` in VS Code or Jupyter, select the `.venv` kernel, and run all cells.

The Paul et al. (2015) dataset is fetched automatically via `sc.datasets.paul15()`.

## Key Dependencies

| Package | Purpose |
|---------|---------|
| `scanpy` | Core scRNA-seq analysis |
| `bbknn` | Batch-balanced k-nearest neighbors |
| `louvain` | Community detection / clustering |
| `matplotlib` | Visualization |

## References

- Wolf, F.A. et al. (2019). *PAGA: graph abstraction reconciles clustering with trajectory inference through a topology preserving map of single cells.* Genome Biology.
- Paul, F. et al. (2015). *Transcriptional heterogeneity and lineage commitment in myeloid progenitors.* Cell.