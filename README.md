# Remote Sensing Notebooks
**Author:** Julian Linke<br>
**Affiliation:** Remote Sensing Research Group, TU Wien<br>
**Period:** July 2024 – August 2024

# Remote Sensing Notebooks

This repository contains two Jupyter notebooks used for demonstration purposes within the Remote Sensing Research Group at TU Wien. 
The examples illustrate typical workflows in Earth observation data handling, but they are **not intended to be fully reproducible**, as some data sources used during development have restricted access.

---

## Included notebooks

### `dask.ipynb`
A short demonstration of parallel and distributed computation with Dask:
- creating a local Dask client
- understanding lazy evaluation and task graphs
- applying chunked operations to array-based data

### `stac_xarray.ipynb`
A demonstration of how STAC metadata can be queried and how assets can be opened with xarray:
- basic STAC search patterns
- loading assets with `odc.stac` / `pystac-client`
- simple visualization and inspection steps

---

## Environment

An accompanying `env.yml` file defines a conda environment containing the main Python packages used in the notebooks (xarray, dask, rasterio, geopandas, etc.). 
It is provided **only as a convenience** and may include packages that were available in the original research environment.

To create the environment:

```bash
conda env create -f env.yml
conda activate remote_sensing


## Acknowledgements
Developed as part of research activities within the Remote Sensing Research Group, TU Wien.
Special thanks to open-source contributors and data providers (EODC) for their enabling tools and services.
