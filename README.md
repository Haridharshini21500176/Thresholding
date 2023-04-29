# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
<br>
Load the necessary packages.

### Step2:
<br>
Read the Image and convert to grayscale.

### Step3:
<br>
Use Global thresholding to segment the image.

### Step4:
<br>
Use Adaptive thresholding to segment the image.

### Step5:
<br>
Use Otsu's method to segment the image.

### Step6:
<br>
Display the results.


## Program
```
Developed by:HARIDHARSHINI.S
REG_NO:212221230033
```
```python
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# convert to grayscale
image = cv2.imread("mick.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("mick.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
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

### Original Image

![9 1](https://user-images.githubusercontent.com/94168395/235293346-e309f078-8931-4e58-8465-8271d9d8fb5d.png)

### Global Thresholding

![9 2](https://user-images.githubusercontent.com/94168395/235293617-ef60e000-5943-446a-b866-9813929281ac.png)

![9 3](https://user-images.githubusercontent.com/94168395/235293630-64b9bd23-a663-44bd-8805-b272c4dee6f5.png)

![9 4](https://user-images.githubusercontent.com/94168395/235293640-02eefefc-4efe-4e6c-9e3d-7ba6b50a2681.png)

![9 5](https://user-images.githubusercontent.com/94168395/235293688-d486905a-05c8-4d7a-b7ec-b0fe46548ed3.png)

![9 6](https://user-images.githubusercontent.com/94168395/235293694-8add7d1c-2dc7-4360-8644-ddb58bae07c6.png)

### Adaptive Thresholding

![9 8](https://user-images.githubusercontent.com/94168395/235293710-d7b731be-973f-4ee4-b343-ede1244452ff.png)


![9 9](https://user-images.githubusercontent.com/94168395/235293716-e1943bdc-f259-48e3-92c2-d410e4a39ff0.png)

### Optimum Global Thesholding using Otsu's Method

![9 7](https://user-images.githubusercontent.com/94168395/235293700-822d6a57-98d0-4ec8-b304-1fd9784970d6.png)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

