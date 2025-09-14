# LensPostMCMC: Post-MCMC Analysis for Strong Gravitational Lensing

This repository contains post-processing and analysis scripts for strong gravitational lensing models, specifically tailored for the AGEL1507 system as described in Sahu et al. (2025). The workflow is designed to process outputs from [lenstronomy](https://github.com/sibirrer/lenstronomy) MCMC runs, visualize model fits, extract physical parameters, and propagate uncertainties.

## Reference

If you use this code or results in your work, please cite:

> Sahu, N., et al. 2025, "Strong Lensing Cosmography with AGEL1507: Joint Constraints from Double Source Plane Lenses", *ApJ*, in press.

## Directory Structure

- `Post_MCMC_Analysis.ipynb`: Main Jupyter notebook for post-MCMC analysis, including data import, visualization, parameter extraction, and uncertainty propagation.
- `data/`: Contains HST imaging data in HDF5 format.
- `PSF files/`: Contains PSF models for each filter.
- `midway_temp/`: Stores intermediate and output files from MCMC and PSO runs.
- `downsampled_mcmc_samples.csv`: Example output of downsampled MCMC chains for further analysis.

## Dependencies

The analysis requires the following Python packages:

- [lenstronomy](https://github.com/sibirrer/lenstronomy)
- [matplotlib](https://matplotlib.org/)
- [numpy](https://numpy.org/)
- [seaborn](https://seaborn.pydata.org/)
- [coloripy](https://github.com/pmelchior/coloripy)
- [astropy](https://www.astropy.org/)
- [chainconsumer](https://samreay.github.io/ChainConsumer/)
- [getdist](https://getdist.readthedocs.io/)
- [corner](https://corner.readthedocs.io/)
- [pandas](https://pandas.pydata.org/)
- [joblib](https://joblib.readthedocs.io/)
- [h5py](https://www.h5py.org/)
- [colossus](https://bdiemer.bitbucket.io/colossus/)
- [scipy](https://scipy.org/)

Install dependencies with:

```bash
pip install lenstronomy matplotlib numpy seaborn coloripy astropy chainconsumer getdist corner pandas joblib h5py colossus scipy
```

## Workflow Overview

1. **Data Import**: Load HST imaging and PSF data for multiple filters.
2. **Cosmology Setup**: Define cosmological parameters and compute angular diameter distances.
3. **Model Output Loading**: Read MCMC and PSO results from lenstronomy runs.
4. **Visualization**: Plot observed, reconstructed, and residual images; model breakdowns; and corner plots for parameter inference.
5. **Parameter Extraction**: Compute medians and credible intervals for lens and source parameters, including fluxes, half-light radii, magnitudes, and masses.
6. **Uncertainty Propagation**: Propagate uncertainties from MCMC chains and cosmological parameters to derived quantities.
7. **Physical Interpretation**: Calculate lens properties such as Einstein radii, convergence, stellar and total masses, and compare with theoretical predictions.

## Usage

Open `Post_MCMC_Analysis.ipynb` in JupyterLab or VSCode and run cells sequentially. The notebook is organized into sections:

- **Imports and Setup**: Loads all required libraries and sets plotting styles.
- **Data Loading**: Imports imaging and PSF data.
- **Cosmology**: Sets up cosmological models and computes relevant distances.
- **Model Results**: Loads MCMC/PSO outputs and extracts parameter chains.
- **Visualization**: Generates diagnostic plots and corner plots.
- **Parameter Analysis**: Computes medians, uncertainties, and physical properties.
- **Downsampling**: Provides tools for thinning or subsampling MCMC chains for publication or further analysis.
- **Physical Properties**: Calculates fluxes, magnitudes, masses, and lensing quantities for all components.

## Customization

- Change file paths in the notebook to match your local directory structure.
- Adjust grid sizes, aperture radii, and other analysis parameters as needed for your system.
- The notebook is modular; you can run only the sections relevant to your analysis.

## Output

- Diagnostic plots (PDF/PNG) for model fits and parameter inference.
- CSV files with downsampled MCMC chains.
- Printed summaries of physical parameters with uncertainties.

## Notes

- The analysis is designed for multi-band, multi-component lens models as in Sahu et al. (2025).
- For new systems, update the data import and model parameter sections accordingly.
- For questions or issues, please contact the corresponding author of Sahu et al. (2025).

## License

This code is provided for academic use in support of published research. Please cite Sahu et al. (2025) when using or adapting this workflow.
