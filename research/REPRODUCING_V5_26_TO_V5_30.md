# Reproducing the V5.26–V5.30 synthetic experiments

## Evidence boundary
These packages contain synthetic offline experiments. They do not contain real teen data, real user telemetry, human ratings, or production-platform evidence. A successful rerun establishes computational reproducibility in the stated environment only; it does not establish real-world safety, benefit, or causal effects.

## Environment
Use Python 3.10 or newer. The packages list the following core dependencies:
- numpy
- pandas
- scipy

Install them in a clean virtual environment. Exact dependency versions are not yet pinned across every milestone; do not describe this as a fully locked environment until per-milestone lock files are published.

## Windows PowerShell
```powershell
py -3.10 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install numpy pandas scipy
```

## macOS/Linux
```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install numpy pandas scipy
```

## Run each experiment
Extract the chosen original ZIP into its own directory, change into the extracted top-level directory, and run the milestone runner:

```bash
python run_v526.py
python run_v527.py
python run_v528.py
python run_v529.py
python run_v530.py
```

Run only the matching script included in that archive. Each runner writes or verifies milestone outputs according to its own implementation. Preserve the original ZIP and work on a separate extracted copy.

## Package-specific notes
- V5.26 and V5.27 package READMEs identify the runner and outputs but do not state a complete dependency lock; inspect imports in the runner and record the exact environment used.
- V5.28 specifies numpy, pandas, scipy.
- V5.29 specifies Python 3.10+, numpy, pandas, scipy.
- V5.30 specifies Python, numpy, pandas, scipy.

## Reproduction record
For every run, record: archive filename; archive SHA-256; operating system; Python version; package versions (`python -m pip freeze`); exact command; start/end time; exit code; generated output hashes; and any warnings/errors. Compare generated results with the included frozen protocol and audit files. Differences must be reported, not silently normalized.

## Still required for a complete reproducibility release
Exact dependency pins or per-package lock files; a single release manifest covering all original milestone archives; clean-environment reruns; and separate public-download checksum verification.
