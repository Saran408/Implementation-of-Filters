### EXP NO: 06
### DATE:

# <p align='center'>Implementation-of-Filters</p>
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import the necessary modules

### Step 2:

```
For performing smoothing operation on a image.
```
Average filter:
```
avg_kernel=np.ones((13,13),np.float32)/169
average_filter_image=cv2.filter2D(image,-1,avg_kernel)
Weighted average filter :
```
wt_avg_kernel=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
wt_average_filter_image=cv2.filter2D(image,-1,wt_avg_kernel)
Gaussian Blur:
```
gaussian_blur=cv2.GaussianBlur(image,(31,31),0,0)
Median filter:
```
median_blur=cv2.medianBlur(image,11)
### Step 3:
For performing sharpening on a image.
```
Laplacian Kernel:
```
lap_kernel=np.array([[-1,-1,-1],[-1,8,-1],[-1,-1,-1]])
lap_image=cv2.filter2D(image,-1,lap_kernel)
Laplacian Operator:
```
Lap_sharp=cv2.Laplacian(image,cv2.CV_64F)
### Step4
Display all the images with their respective filters.
```
## Program:
### Developed By   :M.Saran
### Register Number:212220230044
</br>

```python

import cv2
import numpy as np
import matplotlib.pyplot as plt
img=cv2.imread('rr.jpg')
img1=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)

```
### 1. Smoothing Filters

i) Using Averaging Filter
```Python
kernel=np.ones((13,13),np.float32)/169
image=cv2.filter2D(img1,-1,kernel)
plt.figure(figsize=(10,10))

plt.subplot(1,2,1)

plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(image)

```
ii) Using Weighted Averaging Filter
```Python

kernel2=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image1=cv2.filter2D(img1,-1,kernel2)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(image1)

```
iii) Using Gaussian Filter
```Python

img4=cv2.GaussianBlur(src=img1,ksize=(11,11),sigmaX=0,sigmaY=0)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)

plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img4)
```

iv) Using Median Filter
```Python
img5=cv2.medianBlur(src=img1,ksize=11)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img4)

```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
kernel3=np.array([[0,1,0],[1,-4,1],[0,1,0]])
img6=cv2.filter2D(img1,-1,kernel3)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img6)

```
ii) Using Laplacian Operator
```Python

img7=cv2.Laplacian(img1,cv2.CV_64F)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img7)
```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter
![image](https://user-images.githubusercontent.com/75235427/167810086-f28ad41a-de01-49e2-af13-35604fb9b7c3.png)


ii) Using Weighted Averaging Filter
![image](https://user-images.githubusercontent.com/75235427/167810589-7188abd1-3e3a-4a64-b264-4fffda7451f9.png)


iii) Using Gaussian Filter
![image](https://user-images.githubusercontent.com/75235427/167810733-8c2287ee-b883-4fcb-9602-ec2f69ab2116.png)



iv) Using Median Filter
![image](https://user-images.githubusercontent.com/75235427/167810919-4e81272e-9068-4a53-bfb2-bbef898697b0.png)



### 2. Sharpening Filters
![image](https://user-images.githubusercontent.com/75235427/167811564-a1ebd272-7546-4dbf-843c-04b08b1b8343.png)



i) Using Laplacian Kernal
![image](https://user-images.githubusercontent.com/75235427/167811719-a9340e5b-aeb5-488a-81e5-b190b2f79999.png)



ii) Using Laplacian Operator
![image](https://user-images.githubusercontent.com/75235427/167811742-3b9d667e-5668-4328-9bcb-de6e7062fe31.png)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
