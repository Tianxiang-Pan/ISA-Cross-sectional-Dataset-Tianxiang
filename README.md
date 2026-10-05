# Liberal Peacemaking: ICB Cross-sectional Dataset

Replication materials for the cross-sectional analysis in *Liberal Peacemaking* (ISA 2026 paper). The project examines how the regime characteristics of third-party interveners relate to short-term (agreement at crisis termination) and long-term (tension reduction over five years) outcomes of international crises.

## Folder structure

| Folder | Contents |
|---|---|
| `Raw Data/` | Original source datasets and their codebooks, kept as downloaded. |
| `Cleaned Data/` | `ICB_oob.csv`, the crisis-dyad dataset produced by `ICB Cleaning.Rmd` and used for all analyses. |
| `R Code/` | The three R Markdown scripts (cleaning, analysis, plots) and their rendered HTML output. |
| `models/` | `ICB_models.RData`, the fitted models and matched data saved by `ICB analysis.Rmd` and loaded by `ICB Plots.Rmd`. |
| `Plots/` | All exported figures (see below). |

### `Raw Data/`

| Subfolder | Source |
|---|---|
| `ICB data/` | International Crisis Behavior (ICB) project, v15: system-, actor- and dyad-level data, intervener data, codebooks |
| `V-Dem-CY-FullOthers-v14_csv_YyKfizl/` | V-Dem Country-Year Full+Others, v14 (regime type and democracy indices) |
| `NMC_Documentation-6/` | Correlates of War National Material Capabilities, v6.0 (military expenditure) |
| `version4.1_csv/` | Correlates of War Formal Interstate Alliance, v4.1 (ties to both sides) |
| `DirectContiguity320/` | Correlates of War Direct Contiguity, v3.2 |
| `dyadic_mid_4.03_update/` | Dyadic Militarized Interstate Disputes, v4.03 |
| `polity v data/` | Polity5 |
| `UNGA Ideal Points/` | United Nations General Assembly ideal points / agreement scores |
| `API_NY/` | World Bank GDP (current US$) |

The first five are read by `ICB Cleaning.Rmd`. The remaining datasets are not used by the current code.

#### Files not included in this repository

Two raw data files exceed GitHub's 100 MB file size limit and are excluded via `.gitignore`. Their folders (with codebooks) are kept. To rerun `ICB Cleaning.Rmd`, download the files and place them at the paths below.

| File | Size | Version | Where to put it |
|---|---|---|---|
| `V-Dem-CY-Full+Others-v14.csv` | 381 MB | V-Dem Country-Year Full+Others **v14** (released March 2024; covers **1789–2023**) | `Raw Data/V-Dem-CY-FullOthers-v14_csv_YyKfizl/` |
| `AgreementScores.csv` | 139 MB | UNGA Ideal Points, Erik Voeten (codebook version July 28, 2025) | `Raw Data/UNGA Ideal Points/` |

- V-Dem: <https://v-dem.net/data/dataset-archive/> (choose v14, Country-Year: V-Dem Full+Others, CSV). **Required** by `ICB Cleaning.Rmd`.
- UNGA Ideal Points: Harvard Dataverse, *United Nations General Assembly Voting Data* (Bailey, Strezhnev & Voeten). Not used by the current code.

`ICB analysis.Rmd` and `ICB Plots.Rmd` only need `Cleaned Data/ICB_oob.csv` and `models/ICB_models.RData`, which are included, so the analyses and figures can be reproduced without downloading these files.

### `R Code/`

Run the scripts in this order:

1. **`ICB Cleaning.Rmd`**: merges the raw datasets and writes `Cleaned Data/ICB_oob.csv`.
2. **`ICB analysis.Rmd`**: matching and model estimation; saves `models/ICB_models.RData`.
3. **`ICB Plots.Rmd`**: predicted-probability plots with 95% crisis-clustered HC3 confidence intervals; exports all figures to `Plots/`.

### `Plots/`

- `Core Finding Plots/`: Figures 2–7 in the paper body (main models).
- `Other Plots/Main Models/`: remaining figures from the main models.
- `Other Plots/Robustness - US Involvement/`: all figures from the robustness models that control for US involvement.

Hypotheses H1.x use the long-term outcome (tension reduction) and H2.x the short-term outcome (agreement). Continuous regime indices are plotted at the sample mean ± 1 SD. Military expenditure is shown up to 4 × 10^8 (only the US exceeds this value).

## Reproducing the results

Open `Peacemaking data.Rproj` in RStudio and knit the three scripts in the order above. All file paths are built with `here::here()` relative to the project root, so the `.Rproj` file must remain in the root folder.

Required R packages:

```r
install.packages(c(
  "broom", "car", "countrycode", "dplyr", "ggplot2", "gt", "haven", "here",
  "kableExtra", "lmtest", "magick", "marginaleffects", "MatchIt", "mediation",
  "modelsummary", "pandoc", "readr", "readxl", "sandwich", "scales",
  "stringr", "tidyr", "webshot2", "writexl"
))
```
