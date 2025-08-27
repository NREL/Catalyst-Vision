# Morphological Analyzer for Pre-Masked Catalyst Layers

## Project Description

This project provides an advanced Python-based tool, primarily designed for use in a Jupyter/Colab notebook, for the quantitative morphological analysis of pre-segmented shapes. While developed for analyzing PEM catalyst layers from microscopy, its methodology is suitable for characterizing any grayscale object provided on a uniform white background.

The tool uses a robust computer vision pipeline based on the Euclidean Distance Transform and skeletonization to accurately measure local thickness and tortuosity, providing a comprehensive characterization of an object's geometry and internal texture.

This tool is developed by Dr. Steven Spurgeon at the National Renewable Energy Laboratory (NREL). NREL Sofware Record #SWR-25-100.

## Features

* **Automatic Mask Isolation:** Automatically detects and isolates a grayscale shape from a white or near-white background to create a high-fidelity binary mask.
* **Advanced Thickness Measurement:** Implements a rigorous thickness calculation using the Euclidean Distance Transform, providing accurate local thickness values across the entire shape, including on curved and irregular features.
* **Rigorous Tortuosity Calculation:**
    * Computes the object's medial axis (skeleton).
    * Identifies the primary path by finding the two most distant endpoints.
    * Uses the A* search algorithm to find the true path length along the skeleton.
    * Calculates tortuosity as `(True Path Length / Straight-Line Distance)`.
* **Comprehensive Shape Metrics:** Calculates key geometric descriptors including Area, Perimeter, Circularity, and Solidity.
* **Thickness Profiling:** Generates a plot of the local thickness vs. the distance along the object's primary axis.
* **Advanced Visualization:**
    * Creates a comprehensive 5-panel figure for a complete overview.
    * **New Feature:** Allows for each of the 5 panels to be exported as a separate, publication-ready image file.
* **Internal Texture Analysis:** Calculates statistical moments (Mean, Std Dev, Skewness, Kurtosis) of the grayscale pixel values within the original shape.

## Setup

### Dependencies

The analysis code requires the following Python libraries:
* `opencv-python`
* `numpy`
* `matplotlib`
* `scikit-image`
* `scipy`
* `pandas`

You can install them using pip:
```bash
pip install opencv-python numpy matplotlib scikit-image scipy pandas
