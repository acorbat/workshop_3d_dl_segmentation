# Workshop: 3D Deep Learning Segmentation

This repository contains materials for a workshop on 3D cell segmentation using deep learning tools, specifically **Cellpose** and **StarDist** with **Napari** visualization.

## Prerequisites

Install [Pixi](https://pixi.sh) - a fast, cross-platform package manager built on conda-forge:

- **Installation guide**: [https://pixi.sh/latest/#installation](https://pixi.sh/latest/#installation)
- Quick install (Unix/macOS):
  ```bash
  curl -fsSL https://pixi.sh/install.sh | bash
  ```
- Quick install (Windows PowerShell):
  ```powershell
  iwr -useb https://pixi.sh/install.ps1 | iex
  ```

## Getting Started

### Clone this repository

```bash
git clone https://github.com/acorbat/workshop_3d_dl_segmentation.git
cd workshop_3d_dl_segmentation
```

### Install the environment

```bash
pixi install
```

This will set up Python 3.11 and all required packages (napari, bioio, cellpose, stardist).

### Download the workshop dataset

```bash
pixi run download-data
```

This downloads `Lund.tif` (a 3D microscopy volume) from Zenodo to the `data/` folder.

### Open the workshop notebook

```bash
pixi run jupyter notebook notebooks/cellpose_napari_3d.ipynb
```

Or open it in VS Code with the Jupyter extension.

## Workshop Content

- **`notebooks/cellpose_napari_3d.ipynb`**: Step-by-step tutorial on loading 3D images with BioIO, running Cellpose segmentation, and visualizing results in Napari.
- **`data/Lund.tif`**: Sample 3D microscopy dataset (downloaded via the `download-data` task).

## Visualizing Data

To open the dataset directly in Napari:
```bash
pixi run napari data/Lund.tif
```

## Environment Details

- **Python**: 3.11 (required for StarDist compatibility)
- **Key packages**: napari, bioio, cellpose, stardist
- **Platforms**: Windows, Linux, macOS (Intel & Apple Silicon)

## License

Workshop materials provided for educational purposes.
