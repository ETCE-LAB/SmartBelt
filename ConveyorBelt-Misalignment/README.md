Line Detection using OpenCV

📌 Overview

This project demonstrates how to detect lines in an image using OpenCV and NumPy in Python. The Jupyter Notebook processes an image step by step, including grayscale conversion, region-of-interest cropping, Gaussian Blur, edge detection with Canny, and line detection using the Hough Transform.

🛠️ Required Libraries

Make sure you have the necessary libraries installed before running the notebook. You can install them using:

pip install opencv-python matplotlib numpy

📂 Files

LineDetection.ipynb → Jupyter Notebook containing the line detection steps.

msg1033807294-27153.jpg → Example image used in the notebook.

🚀 How to Run

Open a terminal and navigate to the directory containing this project.

Launch Jupyter Notebook:

jupyter notebook LineDetection.ipynb

Run each cell in order to see the image processing and line detection steps.

📝 Steps in the Notebook

Read the Image: Load an image using OpenCV.

Convert to Grayscale: Simplifies processing.

Define Region of Interest (ROI): Focus on a specific part of the image.

Apply Gaussian Blur: Reduces noise.

Edge Detection (Canny): Detects edges in the image.

Hough Line Transform: Identifies straight lines.

⚡ Experimentation

Try different images by replacing 'msg1033807294-27153.jpg' with your own image.

Adjust the Canny edge detection parameters for better results.

Modify the ROI selection to focus on different areas.

📌 Example Output

The notebook visualizes each step with matplotlib, showing the processed images at different stages.

🔗 References

OpenCV Documentation

NumPy Documentation

