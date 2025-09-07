# 🌑 Lunar Rock Detection: Exploring the Moon Pixel by Pixel  

**Authors**: Juan Ramírez, Juan Cardona  

---

## 🚀 Objective  
To design and evaluate an image processing pipeline capable of detecting and analyzing lunar rocks. Using the `romainpessia/artificial-lunar-rocky-landscape-dataset`, the project puts a variety of transformations and filters to the test, aiming to discover the most effective preprocessing strategies for robust rock detection under challenging lunar conditions.  

---

## 🌌 Project Overview  
Imagine trying to spot lunar rocks on a dusty, unevenly lit, extraterrestrial surface. Shadows, noise, and lighting variations make this task far from trivial. This project tackles that challenge by experimenting with a **toolbox of image processing techniques**, implemented in Python with **OpenCV, NumPy, Matplotlib, and scikit-image**.  

From color transformations to advanced segmentation, the pipeline was designed not just to enhance images, but also to **separate meaningful lunar features (rocks) from distractions**—helping pave the way for applications in planetary exploration and autonomous navigation.  

---

## 🔑 Key Features  

- **Dataset**: 9 carefully selected images from the `romainpessia/artificial-lunar-rocky-landscape-dataset`, balancing computational efficiency with diversity in surface and lighting conditions.  

- **Explored Techniques**:  
  - 🎨 **Basic Transformations**: RGB channel separation, grayscale conversion, and binary thresholding.  
  - ➕ **Arithmetic Operations**: Brightness/contrast adjustments and arithmetic manipulations (sum, subtraction, multiplication, division) to normalize illumination.  
  - 🔗 **Logical Operations**: AND, OR, XOR, NOT to refine or combine binary masks.  
  - 🌀 **Spatial Filters**: Gaussian blur, median, Laplacian, Sobel, Prewitt, and Canny for noise reduction and edge enhancement.  
  - 🧱 **Morphological Operations**: Erosion, dilation, opening, closing, gradients, top-hat, and black-hat for cleaner segmentations.  
  - 🎯 **Segmentation Methods**: Fixed/adaptive thresholding, edge-based, region-based, and Watershed segmentation.  
  - 📊 **Region Analysis**: Leveraging `skimage.measure.regionprops` to extract rock properties such as area, perimeter, centroid, bounding box, and orientation.  

- **Pipeline Output**: Processed results are neatly stored in structured directories (e.g., `output/spatial_filters`, `output/segmentation`) for visual comparison and documentation.  

---

## 🏆 Best Performing Techniques  
After testing the full arsenal of methods, the following emerged as the most effective:  

- **Gaussian Blur** → smooths noise without losing rock boundaries.  
- **Canny Edge Detection** → delivers crisp and reliable rock contours.  
- **Adaptive Thresholding** → adapts to uneven lunar lighting.  
- **Morphological Opening & Closing** → refine rock shapes and eliminate noise specks.  

Together, these techniques create a **robust preprocessing pipeline** that not only detects rocks but also prepares them for **quantitative analysis**.  

---

## 🌠 Why It Matters  
The Moon doesn’t forgive mistakes—uneven illumination, jagged shadows, and noise can fool any algorithm. By testing a **broad spectrum of transformations**, this project identifies the strategies that consistently highlight and segment lunar rocks.  

The chosen pipeline—Gaussian blur, Canny edges, adaptive thresholding, and morphology—proves to be a **winning combination**, offering clean rock segmentation and precise feature extraction. These results are essential for future **autonomous exploration systems**, where reliable rock detection can guide navigation, geological studies, and mission safety.  

---

✨ *In short: from pixels to craters, this project shows how image processing can make sense of the lunar surface, one rock at a time.*  
