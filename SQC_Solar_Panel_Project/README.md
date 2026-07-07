# Statistical Quality Control

Coursework projects for the **Statistical Quality Control** course, MSc in Statistics,
Athens University of Economics and Business (AUEB) — Prof. S. Psarakis.

Each project simulates a production process, introduces a controlled shift (in the mean,
standard deviation, or another process parameter), and applies standard SPC control
charts to evaluate how well each chart detects the shift.

## SPC in a Solar Panel Production Process

**Scenario:** A company produces solar panels with a target length of 65 cm
(σ = 1 cm). Quality is monitored by drawing 60 samples of 10 panels each. The project
simulates this process, then introduces a **small shift** (+0.7 cm, i.e. 0.7σ) and a
**large shift** (+2 cm, i.e. 2σ) in the mean, as well as a **small** (σ: 1 → 1.5) and
**large** (σ: 1 → 2) shift in variability, to compare how different control charts
respond.

### Charts implemented

| Chart | Monitors | Purpose in this project |
|---|---|---|
| **X-bar** | Process mean | Baseline detection of shifts in average panel length |
| **S** | Process variability (σ) | Detection of changes in the spread of panel lengths |
| **CUSUM** | Process mean (cumulative deviations) | Sensitive detection of small, sustained mean shifts |
| **EWMA** (λ = 0.1) | Process mean (weighted average) | Robust, smoothed detection of small mean shifts |

### Key findings

- The **X-bar chart** reliably detects large shifts (2σ) but is much less sensitive to
  small shifts (0.7σ), flagging only a couple of points beyond the control limits.
- The **CUSUM** and **EWMA** charts are both markedly more sensitive to the small mean
  shift than the X-bar chart, flagging it earlier and with more points outside the
  control limits.
- The **S chart** effectively detects both the small and large increases in process
  variability (σ: 1→1.5 and 1→2).
- Overall, CUSUM/EWMA are preferable for catching small, gradual process drifts, while
  X-bar and S charts remain useful for monitoring overall process stability and larger,
  more obvious shifts.

### Files

| File | Description |
|---|---|
| `SQC_Project_Description.pdf` | Original assignment brief |
| `SQC_Solar_Panel_Project_Report.pdf` | Full write-up: methodology, all 12 control charts, and discussion |
| `SQC_Solar_Panel_Project_Code.R` | R script simulating the data and generating all control charts |

> Note: all data used in this project is **simulated within the R script** (via
> `rnorm()`), so no external dataset is required — just run the script.

### Requirements

```r
install.packages("qcc")
```

### Usage

```r
source("SQC_Solar_Panel_Project_Code.R")
```

Running the script will:
1. Simulate baseline production data (60 samples × 10 panels, mean 65 cm, σ = 1 cm).
2. Build X-bar, R, S, CUSUM, and EWMA control charts for the baseline (in-control) data.
3. Simulate a small (+0.7 cm) and a large (+2 cm) mean shift and re-plot the X-bar,
   CUSUM, and EWMA charts against the new data.
4. Simulate a small (σ = 1.5) and a large (σ = 2) variability shift and re-plot the
   S chart against the new data.

Each chart is plotted via the `qcc` package's built-in plotting, including calibration
("Phase 1") data and new ("Phase 2") data where relevant.

## Repository structure

```
.
├── README.md
├── SQC_Project_Description.pdf
├── SQC_Solar_Panel_Project_Report.pdf
└── SQC_Solar_Panel_Project_Code.R
```

*(Future SQC course projects can be added as additional subfolders, e.g. `project-3/`.)*

## Author

Konstantinos Grammenos · MSc in Statistics, AUEB
