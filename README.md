# Do Criminologists Read Each Other's Work?

**A Longitudinal Analysis of Cross-Citation Patterns, 1960–2025**

Zarina I. Vakhitova, Monash University

---

## Overview

This repository contains the interactive companion tool and replication materials for:

> Vakhitova, Z. I. (2026). Do criminologists read each other's work? A longitudinal analysis of cross-citation patterns, 1960–2025.

The paper tests three claims embedded in the fragmentation thesis: that (1) criminology is a fragmented discipline; (2) fragmentation is accelerating; and (3) the pattern of disengagement is symmetric. Using article-level citation data from the Web of Science for twenty-three criminology journals spanning four intellectual traditions (quantitative/empirical, applied/practice, international/comparative, and critical/theoretical), it constructs a longitudinal record of cross-citation patterns covering the 1960s through 2025.

The findings suggest that fragmentation rose through the 1980s and 1990s, peaked around 2000–2003, and has since declined substantially. The fragmentation is also asymmetric: the critical/theoretical tradition allocates a far larger proportion of its references to the quantitative mainstream than the reverse.

## Interactive Explorer

**[Launch the interactive tool →](https://zarina-vakhitova.github.io/criminology-fragmentation/)**

The interactive cluster specification explorer allows readers to reassign any of the 23 journals to a different intellectual tradition and watch the fragmentation ratio recompute in real time across the full 1973–2025 time series. This makes the paper's robustness checks transparent and testable: readers can verify for themselves that the arc-shaped trajectory is not an artefact of how individual journals were classified.

### How to use it

1. **Select a journal** by clicking on it in any of the four cluster columns.
2. **Move it** by clicking on a different cluster column.
3. The chart updates instantly, showing your custom specification (blue) against the paper's baseline (grey dashed).
4. The stats bar shows the 2025 ratio, the peak year, and the change from baseline.
5. Click **Reset** to return to the paper's baseline specification.

The tool runs entirely in your browser. No data is sent to any server.

## Repository Contents

| File | Description |
|------|-------------|
| `index.html` | Interactive cluster specification explorer (self-contained, no build step required) |
| `replication_23.R` | Complete R replication script for all numerical analyses |
| `annual_matrices.json` | Annual 23×23 journal-to-journal citation matrices, 1960–2025 |
| `cumulative_flows.csv` | Cumulative citation flows between all journal pairs |
| `annual_metrics.csv` | Annual fragmentation ratio, modularity, density, and related metrics |
| `changepoint_results.csv` | Piecewise linear regression (breakpoint) results |
| `asymmetry_longitudinal.csv` | Longitudinal pairwise asymmetry ratios |
| `table1_descriptive_stats.csv` | Descriptive statistics for the 23-journal panel (Table 1) |
| `robustness_*.csv` | Ratio series under alternative cluster specifications |

## Data

The analysis draws on article-level data from the Web of Science (WoS) Core Collection, extracted in March 2026. The raw WoS data cannot be redistributed due to licensing restrictions. The processed citation matrices and all derived outputs needed to reproduce the figures and tables are included in this repository.

## Replication

The R replication script (`replication_23.R`) reproduces all numerical analyses reported in the paper. It requires only the `data.table` package:

```r
install.packages("data.table")
source("replication_23.R")
```

The script reads the raw WoS data files (not included due to licensing) and produces all CSV outputs. The pre-computed CSV files in this repository can be used to verify the results without access to the raw data.

The primary analyses were originally implemented in Python 3 using NumPy, pandas, SciPy, and Matplotlib. The R script is an independent replication that produces identical numerical outputs.

## Citation

If you use the data, code, or interactive tool from this repository, please cite:

```bibtex
@article{vakhitova2026criminologists,
  author  = {Vakhitova, Zarina I.},
  title   = {Do Criminologists Read Each Other's Work? {A} Longitudinal 
             Analysis of Cross-Citation Patterns, 1960--2025},
  year    = {2026},
  note    = {Monash University}
}
```

## Licence

The code and interactive tool are released under the [MIT Licence](https://opensource.org/licenses/MIT). The processed data files are released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The raw Web of Science data are subject to Clarivate's terms of use and are not included.

## Contact

Zarina I. Vakhitova — [zarina.vakhitova@monash.edu](mailto:zarina.vakhitova@monash.edu)

School of Social Sciences, Monash University, Melbourne, Australia
