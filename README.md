# Thresholding
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## PROGRAM:
```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("dog.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("dog.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_jk1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_jk2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_jk3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_jk4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_jk5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_jk7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_jk8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_jk6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_jk1,thresh_jk2,thresh_jk3,thresh_jk4,thresh_jk5,thresh_jk6,thresh_jk7,thresh_jk8]
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
## OUTPUT:

### Original Image and Grayscale Image
![download](https://github.com/jagadeeshreddy561/Thresholding/assets/120623104/2d9df715-a6a8-4ed6-8353-1d609a8a9b8e)




### Global Thresholding

![download](https://github.com/jagadeeshreddy561/Thresholding/assets/120623104/196ca064-652b-47aa-a3f8-c831ad46c4e1)

![download](https://github.com/jagadeeshreddy561/Thresholding/assets/120623104/3a328d11-d8e7-451a-b9b6-4db37bb1c6c9)
![download](https://github.com/jagadeeshreddy561/Thresholding/assets/120623104/59209f28-2186-4ebf-b358-9dcc6b02da1f)
![download](https://github.com/jagadeeshreddy561/Thresholding/assets/120623104/2bdcc5c2-7042-456f-92cc-c42b44b38474)![download](https://github.com/jagadeeshreddy561/Thresholding/assets/120623104/c838bcfa-40d1-4170-baf5-67e6a04df07c)



### Adaptive Thresholding

![download](https://github.com/jagadeeshreddy561/Thresholding/assets/120623104/7354ae13-347a-4098-9ac2-8ed2031e866d)
![download](https://github.com/jagadeeshreddy561/Thresholding/assets/120623104/602dd8ab-d7c1-41c5-90f8-b4f833e3c7bb)



### Optimum Global Thesholding using Otsu's Method

![download](https://github.com/jagadeeshreddy561/Thresholding/assets/120623104/e6a5712b-fc8c-416d-a6d9-d1d966172397)

## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
