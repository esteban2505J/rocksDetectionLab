# 🪨 Rock Detection: Exploring Surfaces Pixel by Pixel

**Authors**: Juan Ramírez, Juan Cardona

---

## 🚀 Objective
Design and evaluate an image-processing pipeline to **detect, segment and count rocks** in natural images. We use the **`rocks-dataset` by Neel Gajare (Kaggle)** to train, test and validate preprocessing + classical computer-vision methods that generalize across different rock types, sizes and textures.

**Dataset:** https://www.kaggle.com/datasets/neelgajare/rocks-dataset

---

## 🌌 Project Overview
Detecting rocks in real-world photos is challenging due to variations in lighting, texture, shape and background clutter. This repository experiments with a toolbox of image-processing techniques (OpenCV + NumPy + scikit-image) to robustly isolate rock instances and count them reliably.

The pipeline is intended to be modular: apply transforms → segment → clean with morphology → analyze regions → count and store results.

---

## 🔑 Key Features

- **Dataset**: The `rocks-dataset` (Kaggle) — diverse rock images with multiple classes and conditions, improving detection performance vs. synthetic-only datasets.
- **Implemented Techniques**:
  - Basic transforms: channel splits, grayscale, histogram equalization.
  - Illumination normalization: brightness/contrast, CLAHE.
  - Spatial filters: Gaussian, median, Laplacian, Sobel, Prewitt.
  - Edge detection: Canny.
  - Thresholding: global & adaptive.
  - Morphology: erosion, dilation, opening, closing, top-hat, black-hat.
  - Segmentation: watershed, connected components, contour extraction.
  - Region analysis: `skimage.measure.regionprops` — area, perimeter, bbox, centroid, orientation.
- **Outputs**: structured `output/` folders with processed images, masks, annotated images and CSV summaries (counts and per-region features).

---

## 🧭 Recommended Pipeline (default)
1. Load image → convert to grayscale.  
2. Apply **CLAHE** or histogram equalization (improves contrast).  
3. **Gaussian blur** (noise smoothing).  
4. **Canny edge** detection to get crisp boundaries.  
5. **Adaptive thresholding** (handles uneven illumination).  
6. Morphological **opening** then **closing** to remove small artifacts and fill holes.  
7. Connected-components or **watershed** for separating touching rocks.  
8. Extract `regionprops` and apply size filters → count rocks.  
9. Save annotated visualization + CSV with features.

---

## 🏆 Best Performing Techniques (empirical)
- **CLAHE / histogram equalization** — improves contrast on varied surfaces.  
- **Gaussian blur** — reduces salt-and-pepper noise while preserving contours.  
- **Adaptive thresholding** — copes with locally varying illumination.  
- **Canny + morphology** — robust contour extraction and cleanup.  
- **Watershed** (when rocks touch) — better separation of adjacent rocks.

---
