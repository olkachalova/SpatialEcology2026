# RF versus RFSI: why does validation strategy matter?

**A spatial modelling experiment with Meuse zinc (in Python)**  
Olha Kachalova

This teaching notebook compares Random Forest (RF) and Random Forest Spatial Interpolation (RFSI), examines four sets of environmental predictors, and explores random, spatial and kNNDM cross-validation under different sampling designs.

## Notebook

[View or download the Jupyter notebook](Meuse_RF_RFSI_Validation_Case_Study.ipynb)

The original notebook is distributed unchanged, including the embedded illustrations and saved analytical results. You can read the saved results without running the code. No separate image files are needed.

## Run online in Google Colab

1. Go to [Google Colab](https://colab.research.google.com/).
2. Open the notebook from GitHub using the **GitHub** tab (or download the `.ipynb` file and use the **Upload** tab).
3. Use a standard CPU runtime and select **Runtime > Run all**.

No GPU, R installation or GIS software is required. The first run needs internet access to download the data and install any missing Python packages.

## Run locally with Jupyter

Download or clone the repository. Open a terminal in the repository directory. A fresh Python 3.12 environment is recommended (the notebook was saved using Python 3.12.7).

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it using one of the commands below.

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

macOS or Linux:

```bash
source .venv/bin/activate
```

Install the required packages and start JupyterLab:

```bash
python -m pip install -r requirements.txt
python -m jupyterlab
```

Open `Meuse_RF_RFSI_Validation_Case_Study.ipynb` using the Python 3 kernel and select **Kernel > Restart Kernel and Run All Cells**.

The notebook uses 600 trees per forest and five nearest neighbours. The full experiment may take some time on a CPU. Exact results can differ slightly across library versions.

## Data

The notebook loads the original Meuse observations (155 rows) and prediction grid (3,103 rows) from the `sp` R package, with a CSV fallback. It automatically creates a `data/` cache. An internet connection is required if those files are not already available locally.

For offline use, place the original `meuse.rda` and `meuse.grid.rda` (or `meuse.csv` and `meuse.grid.csv`) in a `data/` folder relative to the notebook's working directory. The `pyreadr` package reads the R data without installing R. Data files are not included in this distribution.

Data documentation: [Meuse observations](https://edzer.github.io/sp/reference/meuse.html) and [prediction grid](https://edzer.github.io/sp/reference/meuse.grid.html).

## References

- Sekulic et al. (2020), [Random Forest Spatial Interpolation](https://doi.org/10.3390/rs12101687).
- Linnenbrink et al. (2024), [kNNDM cross-validation](https://doi.org/10.5194/gmd-17-5897-2024).

## Reproducibility

The notebook's saved output reports the following package versions: NumPy 2.4.2, pandas 3.0.0, SciPy 1.17.0, scikit-learn 1.8.0, Matplotlib 3.10.8 and seaborn 0.13.2. The requirements file specifies the minimum core versions used by the notebook setup, together with JupyterLab and the R data reader. These are not an exact environment lockfile.
