# AI406: Thresholding 
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

Use Global thresholding to segment the image

### Step4:

Use Adaptive thresholding to segment the image.

### Step5:

Use Otsu's method to segment the image and display the results.

## Program

#### Developed By: MALAR MARIAM S
#### Register Number: 212223230118

## Load the necessary packages

```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

## Read the Image and convert to grayscale

```
image = cv2.imread('girl.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('girl.jpg',0)
```

# Use Global thresholding to segment the image

```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

# Use Adaptive thresholding to segment the image

```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

# Use Otsu's method to segment the image 

```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

# Display the results

```
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

![image](https://github.com/user-attachments/assets/9accbc07-a3bf-41bb-94cb-5e618d2487eb)



### Global Thresholding

![image](https://github.com/user-attachments/assets/8e853b8e-9fa4-4fb9-86de-fab5283bc39c)

![image](https://github.com/user-attachments/assets/a6465f80-a081-40a6-acec-522205bf0443)

![image](https://github.com/user-attachments/assets/695106f4-d959-40cb-8571-f45e45f434da)

![image](https://github.com/user-attachments/assets/a21da00e-992d-4481-9874-c3ee54547378)

![image](https://github.com/user-attachments/assets/4adb6aed-89f5-457e-8210-1609661e17f1)

### Adaptive Thresholding

![image](https://github.com/user-attachments/assets/2543a10d-09a1-414d-8834-7e953f6bd961)

![image](https://github.com/user-attachments/assets/7821db0b-d4d4-4a82-94ce-e98639865126)

### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/user-attachments/assets/fea5f411-2314-4fec-8557-df5fdba00b73)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
