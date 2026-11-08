# Ion-decay half-life analysis

(staircase_sim.ipynb) extracts a monotonic integer staircase from complex IQ data and estimates the half-life with a discrete, truncated maximum-likelihood fit. A simulation processed with the same staircase fit is included as a validation check.

## Input data

The first notebook cell expects a `.npy` object array. Each entry must be a dictionary containing `filename`, `data` (complex IQ samples), and `fs` (sampling rate in Hz). 

## Usage

Check or adjust:

- `DATA_FILE`, `DT_BIN`, and `NPERSEG`
- `BAND_E` and `BG_BANDS`
- the `A1` calibration and staircase-fit settings
- `FILE_START`, `BAD_RANGES`, and the simulation parameters

## Half-life analysis with RionDS (`notebooks/rionsis_analysis.ipynb`)

One notebook for the 72Ge (long and short settings) and 98Mo data sets: choose the data set with `DATASET` in the first cell and set `DATA_FILE` and `RIONDS_DIR` to your own paths. It extracts the single-ion step ΔI (mixture EM with a recovery test), the noise parameters σ0 and k, n̄ and I0, the exponential fit of the summed curve, and writes the RionDS input file (`simparams_<tag>.toml`).
