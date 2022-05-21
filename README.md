# Thresholding of Images
## Aim:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required:
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm:

### Step1:

Load the necessary packages.

### Step2:

Read the Image and convert to grayscale.

### Step3:

Use Global thresholding to segment the image.

### Step4:

Use Adaptive thresholding to segment the image.

### Step5:

Use Otsu's method to segment the image.

### Step6:

Display the results.

## Program:

```python
# Load the necessary packages

import cv2
import matplotlib.pyplot as plt
import numpy as np

# Read the Image and convert to grayscale

image=cv2.imread("dream.jpg")
image1=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

# Use Global thresholding to segment the image

ret, thresh1 = cv2.threshold(image1,100,200,cv2.THRESH_BINARY)
ret, thresh2 = cv2.threshold(image1,100,200,cv2.THRESH_BINARY_INV)
ret, thresh3 = cv2.threshold(image1,100,200,cv2.THRESH_TRUNC)
ret, thresh4 = cv2.threshold(image1,100,200,cv2.THRESH_TOZERO)
ret, thresh5 = cv2.threshold(image1,100,200,cv2.THRESH_TOZERO_INV)


# Use Adaptive thresholding to segment the image

th1=cv2.adaptiveThreshold(image1,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
th2=cv2.adaptiveThreshold(image1,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret2,th3 = cv2.threshold(image1,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","THRESH_BINARY","THRESH_BINARY_INV","THRESH_TRUNC"
       ,"THRESH_TOZERO","THRESH_TOZERO_INV","ADAPTIVE_THRESH_MEAN_C","ADAPTIVE_THRESH_GAUSSIAN_C","OTSU"]
images=[image1,thresh1,thresh2,thresh3,thresh4,thresh5,th1,th2,th3]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()



```
## Output:

### Original Image

![img](https://user-images.githubusercontent.com/75413726/169659333-affe77ae-4370-47bf-8727-094cfbb7e2d9.jpg)

### Global Thresholding

![img1](https://user-images.githubusercontent.com/75413726/169659362-3278ea2d-3c84-413f-a100-18a1ce11f32e.jpg)
![img2](https://user-images.githubusercontent.com/75413726/169659394-0d1a81c7-da49-4cdc-8205-75a0ba4e5911.jpg)

### Adaptive Thresholding

![img3](https://user-images.githubusercontent.com/75413726/169659421-8a78ce75-caf6-4c7d-a07b-318cbbd452e8.jpg)

### Optimum Global Thesholding using Otsu's Method

![img4](https://user-images.githubusercontent.com/75413726/169659435-4ebffb6f-9ba2-464d-881e-04d44bb03ee3.jpg)

## Result:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

