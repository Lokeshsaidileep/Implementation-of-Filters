# Implementation-of-Filters
## Aim:

To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import the required libraries and read the image.

### Step 2:
Convert the saved BGR image to RGB using cvtColor().

### Step 3:
Use the filters required for image smoothing and sharpening.

### Step 4:
Apply the filters using cv2.filter2D() for each respective filters.
 

### Step 5:
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().
 

## Program:
~~~
Developed By   : S.LOKESH SAI DILEEP
Register Number: 212221230111
~~~
~~~
import cv2
import numpy as np
import matplotlib.pyplot as plt
image=cv2.imread('car.jpg')
image2=cv2.cvtColor (image1, cv2.COLOR_BGR2RGB)
~~~
## 1. Smoothing Filters :
### i) Using Averaging Filter:
~~~
kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(image2,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")
~~~
### ii) Using Weighted Averaging Filter:
~~~
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(image2,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")
~~~
### iii) Using Gaussian Filter:
~~~
gaussian_blur = cv2.GaussianBlur(src = image2, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")
~~~
### iv) Using Median Filter:
~~~
median = cv2.medianBlur(src=image2,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered (Median)")
plt.axis("off")
~~~
## 2. Sharpening Filters:
### i) Using Laplacian Kernal:
~~~
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(image2,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered (Laplacian Kernel)")
plt.axis("off")
~~~
### ii) Using Laplacian Operator:

~~~
laplacian_operator = cv2.Laplacian(image2,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered (Laplacian Operator)")
plt.axis("off")
~~~

## Output:
### Smoothing Filters:
#### i)  Using Averaging Filter:
![image](https://user-images.githubusercontent.com/94883079/230030774-ef20850f-83f1-4c1d-883c-7c90195ccf44.png)
#### ii) Using Weighted Average Filter:
![image](https://user-images.githubusercontent.com/94883079/230030133-edc8d558-93be-46ff-bafc-329276de18df.png)
#### iii) Using Gaussian Filter:
![image](https://user-images.githubusercontent.com/94883079/230030203-b764840b-4096-4f6e-8d19-cd6aea2c2216.png)
#### iv) Using Median Filter:
![image](https://user-images.githubusercontent.com/94883079/230030272-80ec563d-826a-4575-a373-2dc00ea9dcb2.png)
### Sharpening Filters:
#### i) Using Laplacian Kernel:
![image](https://user-images.githubusercontent.com/94883079/230030339-51b3e3cb-ad46-4794-afc4-2e1cb2f0251d.png)
#### ii) Using Laplacian Operator:
![image](https://user-images.githubusercontent.com/94883079/230030399-13a6fc72-0752-4559-b4d2-8057a610de2c.png)
## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
