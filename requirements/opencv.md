# OpenCV

## Description
- **Main Functionality**: OpenCV is a popular open-source computer vision library that provides tools for image and video processing, including advanced algorithms for object detection, image segmentation, and machine learning.
- **Use in Planetology**: Useful for processing and analyzing planetary images obtained from various missions, such as enhancing image quality, detecting features, and performing quantitative analysis.

## Technical Requirements
- **Dependencies**: Requires numpy for array operations, and optionally matplotlib for visualization.

## Links and Resources
- **Official Documentation**: [OpenCV Documentation](https://opencv.org/)
- **Additional References**: [OpenCV Github repository](https://github.com/opencv/opencv)

## code snippet

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load and display an example image from a planetary mission
image_path = 'path/to/planetary_image.jpg'
image = cv2.imread(image_path)

# Convert image to RGB (OpenCV loads images as BGR by default)
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Display the original image
plt.figure(figsize=(8, 6))
plt.imshow(image_rgb)
plt.axis('off')
plt.title('Original Planetary Image')
plt.show()

# Perform image processing operations (e.g., edge detection)
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
edges = cv2.Canny(gray_image, threshold1=30, threshold2=100)

# Display the edge-detected image
plt.figure(figsize=(8, 6))
plt.imshow(edges, cmap='gray')
plt.axis('off')
plt.title('Edge-detected Image')
plt.show()
