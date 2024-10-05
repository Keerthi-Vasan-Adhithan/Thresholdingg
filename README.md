# Experiment - 8
## Date : 
# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the required libraries like OpenCV, NumPy, and Matplotlib.

### Step2:
Read the input image from the file and convert it to grayscale using OpenCV.

### Step3:
Apply different thresholding techniques: Global thresholding (binary, binary inverse, truncate, to zero, to zero inverse). Otsu’s thresholding. Adaptive thresholding (mean, Gaussian).
### Step4:
Store the results of each thresholding operation in a list for easy visualization.

### Step5:
Display the original grayscale image and the thresholded images side by side using Matplotlib to compare results.

## Program:

### Developed By : KEERTHI VASAN A
### Reg No : 212222240048

```py
# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt



# Read the Image and convert to grayscale

image = cv2.imread('dog.jpg')
plt.imshow(image)
plt.title('Original Image')
plt.xticks([]), plt.yticks([])
plt.show()
# Convert to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display the original grayscale image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()



# Use Global thresholding to segment the image

ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Display the global thresholding result
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()


# Use Adaptive thresholding to segment the image


th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                    cv2.THRESH_BINARY, 11, 2)

# Display the adaptive thresholding result
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()

# Use Otsu's method to segment the image 

ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the Otsu thresholding result
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()

```
## Output

### Original Image

![{C8E71D8D-C2B5-43D1-B9EE-35CBE462A920}](https://github.com/user-attachments/assets/2f385e1d-624c-4000-a56e-0467d4737edb)

### Grayscale Image

![{CDDD6328-A31E-4FEE-A90C-A473D813483C}](https://github.com/user-attachments/assets/5141d84d-09af-4b6a-8a2a-90f8f5637c0c)


### Global Thresholding
![{CE1DE763-AF37-43FE-A277-2C0613A63375}](https://github.com/user-attachments/assets/22da4410-c32f-4f5b-a248-49642af96470)


### Adaptive Thresholding
![{C3985DD4-9271-40EA-81CB-BD2815E515F5}](https://github.com/user-attachments/assets/47762a25-a39e-4e92-930b-e99b383a2ecf)


### Optimum Global Thesholding using Otsu's Method
![{71CAEDD1-BFE6-42B7-B74E-EA56BC4FDC57}](https://github.com/user-attachments/assets/3b314af7-97ff-4991-a01e-60542d4293c5)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
