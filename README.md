# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
<br>

### Step2:
<br>

### Step3:
<br>

### Step4:
<br>

### Step5:
<br>

## Program

```python
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2


# Read the Image and convert to grayscale

image = cv2.imread("peppa.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("peppa.jpg",0)


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

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
![image](https://user-images.githubusercontent.com/93427594/235703551-b22fca62-9368-4422-a202-e9e9b8f1bee7.png)

### Global Thresholding
![image](https://user-images.githubusercontent.com/93427594/235703622-c5009471-6f3b-4520-9395-955130706507.png)
![image](https://user-images.githubusercontent.com/93427594/235703673-46a440d9-8ae9-4381-8777-7650a8612b3b.png)
![image](https://user-images.githubusercontent.com/93427594/235703727-59b5722e-b2c1-4bf9-ad2a-0110e159965e.png)
![image](https://user-images.githubusercontent.com/93427594/235703794-3a1cce91-66e3-4714-8973-83e0de3889de.png)
![image](https://user-images.githubusercontent.com/93427594/235703854-267d507d-43d9-480e-b08d-fa809e0d4e87.png)

### Adaptive Thresholding
![image](https://user-images.githubusercontent.com/93427594/235703976-0ef4038d-2b5f-4670-90e6-b2a5016fec1a.png)
![image](https://user-images.githubusercontent.com/93427594/235704068-c697400c-806d-45b0-95d9-0ca6db3aa88c.png)


### Optimum Global Thesholding using Otsu's Method

![image](https://user-images.githubusercontent.com/93427594/235703936-ef891ebc-20c8-4f72-92cd-a9670956960a.png)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

