# Exp-8  THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program


```python
#Name: Ashwina K N
#Reg No: 212223230025
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale

image = cv2.imread('cheetah.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('cheetah.jpeg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)jujupitr
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
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
## Output

## Original Image
![Screenshot 2025-04-28 220415](https://github.com/user-attachments/assets/03b61205-4d8e-463c-84ef-eddf024c23d3)


## Global Thresholding

![Screenshot 2025-04-28 220614](https://github.com/user-attachments/assets/b3c70d98-2509-4fb9-874d-91ac1c3f7949)
![Screenshot 2025-04-28 220627](https://github.com/user-attachments/assets/e154151b-f0cf-47ca-a0e8-6e6a51db984c)
![Screenshot 2025-04-28 220637](https://github.com/user-attachments/assets/93a7de2a-de6a-48fc-b2e4-91ab85939ba6)
![Screenshot 2025-04-28 220647](https://github.com/user-attachments/assets/05243836-eaa2-4e4e-a21b-f2665fceca5f)
![Screenshot 2025-04-28 220655](https://github.com/user-attachments/assets/48654f89-7b73-4395-ad1a-132d0596303b)



## Adaptive Thresholding
![Screenshot 2025-04-28 220716](https://github.com/user-attachments/assets/89a4d25b-b6f7-481d-836b-f09aae4fe2e6)
![Screenshot 2025-04-28 220727](https://github.com/user-attachments/assets/173614fa-2cf5-4eb5-84de-1cde1ccde298)

## Optimum Global Thesholding using Otsu's Method

![Screenshot 2025-04-28 220704](https://github.com/user-attachments/assets/ffc153bc-fa39-4cf3-850f-7564289fd771)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
