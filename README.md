# Impact of Missing Data and Different Imputation Methods on Image Processing

---

## Overview

This project explores the impact of missing data on image processing and evaluates various imputation techniques to handle such data. By using two distinct paintings—"Starry Night on the Rhone" by Vincent Van Gogh and an unnamed abstract piece resembling Jackson Pollock's style—we will simulate data loss, apply different imputation methods, and analyze their effectiveness. This hands-on approach aims to provide insights into handling missing data in a spatial context, crucial for image processing tasks.

---

## Introduction

In image processing, missing data can significantly affect the quality and interpretability of images. Imputation methods, which fill in the missing data, are essential for maintaining the integrity of image data. This project investigates the effects of missing data and compares various imputation techniques using Python. We will simulate different levels of data loss (25%, 50%, and 75%) and apply random filling, mean and median filling, and spatial interpolation methods (nearest neighbor, linear, and cubic).

---

## Dependencies and Resources

- **Python Libraries**:
  - `matplotlib`: For image loading, manipulation, and visualization.
  - `numpy`: For numerical operations and handling missing data.
  - `scipy.interpolate`: For spatial interpolation of missing data.

- **Images**:
  - 'starry_night_on_the_rhone_.png': "Starry Night on the Rhone" by Vincent Van Gogh.
  - 'jackson_pollock.png': An unnamed abstract piece resembling Jackson Pollock's style.

---

## Detailed Description

### 1. Paintings Selection and Loading

Two paintings were selected for this project to analyze the impact of missing data and different imputation techniques. These paintings are loaded into Python using `matplotlib.image` and converted to grayscale by averaging the RGB values.

### 2. Simulate Missing Data

We simulate losing different proportions (25%, 50%, and 75%) of the image data. A random selection matrix is created to preserve certain pixel positions, while the remaining pixels are replaced with `np.NaN`.

### 3. Random Imputation

All missing values (`NaN`) are replaced with zeros. This simple imputation method provides a baseline for comparison with other techniques.

### 4. Mean and Median Imputation

The missing values are replaced with the mean and median of the non-missing data, respectively. These statistical imputation methods are evaluated for their effectiveness in preserving image quality.

### 5. Spatial Interpolation

Given the spatial structure of image data, we apply interpolation methods to estimate the missing values. Using `scipy.interpolate.griddata`, we perform nearest neighbor, linear, and cubic interpolations. These methods are particularly useful for maintaining the continuity and smoothness of the images.

### 6. Pixel Value Distributions

Histograms of pixel values are calculated for the original data and for all interpolation methods. This analysis helps in understanding how each method affects the distribution of pixel intensities.

### 7. Pointwise Errors

The Frobenius norm is calculated for the filled and interpolated images. This norm measures the difference between the original and processed images, providing a quantitative assessment of the imputation methods' accuracy.

### 8. Varying Missing Data Proportions

The procedures are repeated for 25% and 75% data loss. Subplots are created to visualize the original, randomly filled, mean filled, median filled, and interpolated images. This comparison highlights the performance of each imputation method under different levels of data loss.

---

## Applications

This project has significant applications in various fields where image data integrity is critical. These include:

- **Medical Imaging**: Handling missing data in medical scans to ensure accurate diagnostics.
- **Remote Sensing**: Filling in missing satellite imagery data for environmental monitoring.
- **Computer Vision**: Improving the robustness of machine learning models dealing with incomplete image data.
- **Art Restoration**: Digital restoration of damaged artworks by accurately imputing missing parts.

---

## Conclusion

By analyzing the impact of missing data and evaluating different imputation techniques, this project provides valuable insights into maintaining image quality and integrity. The findings demonstrate the strengths and weaknesses of each method, guiding the selection of appropriate imputation techniques for various image processing applications. 