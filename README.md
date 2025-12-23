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

#### Cellpose

```bash
pixi run jupyter notebook notebooks/cellpose_napari_3d.ipynb
```

#### Stardist

```bash
pixi run jupyter notebook notebooks/stardist_napari_3d.ipynb
```

Or open them in VS Code with the Jupyter extension.

## Workshop Guide

For a detailed walkthrough of the notebooks and additional learning resources, see the [**workshop.md**](workshop.md) file. It includes:
- Step-by-step instructions for each notebook
- Learning objectives
- Tips for success
- Information about testing additional models on BioImage.io

## Environment Details

- **Python**: 3.11 (required for StarDist compatibility)
- **Key packages**: napari, bioio, cellpose, stardist
- **Platforms**: Windows, Linux

## License

This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).
