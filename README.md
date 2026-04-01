# Transcriptional networks underlying tumor plasticity in small-cell lung cancer

This repository contains the code used to reproduce the analyses and figures from our study on transcriptional and epigenetic networks underlying tumour plasticity in small-cell lung cancer (SCLC). The project integrates single-cell RNA-seq, single-cell ATAC-seq, spatial proteomics, bulk RNA-seq, and downstream computational analyses to characterize cell-state diversity, lineage plasticity, and regulatory programs in the RPR2 mouse model and related SCLC datasets. The study identifies a previously unrecognized Intermediate state, explores its relationship to NE-to-nonNE transitions, and highlights transcription factor regulators such as RORB that shape SCLC cell fate.

## Contents
- `archetype_analysis/`
  - `1a-all-preprocessing.ipynb`
    - Data preprocessing and integration for archetype analysis.
  - `2-all_scPCHA.ipynb`
    - Single-cell archetype analysis using scPCHA / Pareto-based archetype inference.
  - `2c-all-Harmony-PCHA-Network_Prep.ipynb`
    - Harmony-corrected archetype analysis, diffusion-based labeling of cells, and network preparation.

- `network_analysis/`
  - `main_make_network.py`
    - Build directed gene regulatory networks from DIRECT-NET input, filter by motif score, and save network CSV outputs.
  - `main_all_data_remove_selfloops_6667.py`
    - Configure and run Boolean network inference, validation, attractor finding, and perturbation analysis on directed regulatory networks.
  - `feature_selection_network.py`
    - Perform Lasso-based feature selection per target gene to refine network edges and save filtered network subsets with plots.
  - `bb_utils.py`
    - Boolean network utility library for walk parsing, attractor similarity, stability metrics, and visualization.
  - `DIRECT-NET FILES/`
    - Input files used for network construction.
  - `networks/`
    - Output network files and selected network variants.

- `scMultiomics analysis/`
  - `01.scMultiomics_archetype_characterization_Fig1.Rmd`
    - R Markdown analysis for archetype characterization and Figure 1 / Extended Data Figure 2.
  - `02.RPM-RPMA_dataset_reanalysis_Fig2.rmd`
    - R Markdown analysis of the RPM-RPMA dataset for Figure 2 and Extended Data Figure 5.



## Dependencies

This repository does not include an explicit dependency specification file. Some of the packages used in the notebooks and scripts include:

- Python: `pandas`, `numpy`, `networkx`, `matplotlib`, `seaborn`, `bobaT`, `graph_tool`, `scikit-learn`, `arboreto`, `json`, `glob`
- R: `Seurat`, `Signac`, `ggplot2`, `dplyr`, `readxl`, `reshape2`, `tidyverse`, `MuDataSeurat`, `pheatmap`, `effsize`, `EnhancedVolcano`, `msigdbr`, `homologene`, `viridis`, `Hmisc`, `patchwork`, `corrplot`

## Reproducing the analyses

1. Open the Jupyter notebooks in `archetype_analysis/` to run preprocessing and archetype workflows.
2. Open the R Markdown files in `scMultiomics analysis/` to generate figures and run multi-omics scoring.
3. Run the Python scripts in `network_analysis/` to rebuild networks and perform Boolean network analysis.


## Notes

- The repository contains only analysis code and manuscript material; raw data are not included.
- The attached PDF manuscript documents the biological context and results for this work.
-  The scripts are configured with local paths and analysis parameters; these should be reviewed before rerunning. 



---

For questions about usage or reproducibility, inspect the notebook headers and script comments for dataset locations and pipeline settings.
