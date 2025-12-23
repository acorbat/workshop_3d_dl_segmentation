# Workshop: 3D Deep Learning Segmentation - Step by Step Guide

This guide will walk you through the workshop materials and hands-on exercises.

## Prerequisites

Before starting, ensure you have:
1. Completed the installation steps in the [README.md](README.md)
2. Run `pixi install` to set up the environment
3. Downloaded the dataset with `pixi run download-data`

## Working Through the Notebooks

### Cellpose 3D Segmentation

**Overview**: This notebook demonstrates how to use Cellpose for 3D cell segmentation with Napari visualization.

**Steps to open and run**:

1. From the terminal within the workshop folder:
   ```bash
   pixi run cellpose
   ```
   
   Alternatively, if using VS Code with the Jupyter extension:
   - Open VS Code in the workshop folder
   - Click on `notebooks/cellpose_napari_3d.ipynb` in the file explorer
   - Select the Pixi kernel when prompted

2. **Follow the notebook cells in order**:
   - Read the introduction and understand the Cellpose model
   - Load the `Lund.tif` dataset
   - Run the segmentation model on the 3D volume
   - Visualize results in Napari
   - Explore different parameters and their effects

3. **Expected outputs**:
   - A segmentation mask showing identified cells
   - Interactive 3D visualization in Napari viewer
   - Performance metrics and processing time

### StarDist 3D Segmentation

**Overview**: This notebook demonstrates how to use StarDist for 3D segmentation, an alternative approach using star-convex polygons.

**Steps to open and run**:

1. From the terminal with the Pixi environment activated, launch Jupyter:
   ```bash
   pixi run stardist
   ```
   
   Or open directly in VS Code via the Jupyter extension.

2. **Follow the notebook cells in order**:
   - Understand the StarDist model architecture
   - Load the `lund1051_resampled.tif` dataset
   - Run the 3D StarDist model
   - Compare results with Cellpose
   - Visualize and analyze the segmentation output

3. **Expected outputs**:
   - StarDist segmentation masks
   - Interactive 3D visualization
   - Comparison metrics between models

## Next Steps: Test PlantSeg on BioImage.io

After completing the notebooks, explore additional segmentation models on **[BioImage.io](https://bioimage.io/)**:

1. Visit [https://bioimage.io/](https://bioimage.io/)
2. You can try the models in the webpage by logging in and clickong on test run model.
3. You can:
   - Read the model documentation and paper references
   - View example segmentations and 3D visualizations
   - Download the model for use in your own projects
   - Test the model interactively if available
   - This [notebook](https://github.com/bioimage-io/core-bioimage-io-python/blob/main/example/model_usage.ipynb) can help you download a model from BioImage and run it for yourself. 

PlantSeg is an excellent example of how specialized deep learning models can be developed and shared for specific biological imaging applications. Explore how it compares to the general-purpose Cellpose and StarDist models you've used in this workshop.

## Tips for Success

- **Start with Cellpose**: It's often more user-friendly for beginners
- **Experiment with parameters**: Try different thresholds and settings to see how they affect results
- **Use Napari's features**: Zoom, rotate, and toggle layers to understand the 3D structure
- **Compare models**: Run both notebooks on the same data to see how different approaches differ
- **Check intermediate outputs**: Most notebooks save intermediate results for inspection

## Key Learning Objectives

By the end of these notebooks, you should understand:
- How deep learning models for cell segmentation work
- The differences between Cellpose and StarDist approaches
- How to use Napari for 3D visualization
- How to evaluate and compare segmentation results

## Troubleshooting

- If Napari doesn't display correctly, ensure your graphics drivers are up to date
- If memory issues occur, the notebooks can be modified to process smaller slices
- Contact the workshop instructor if you encounter any problems

---

Happy segmenting! 🔬
