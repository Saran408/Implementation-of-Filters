# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

###Algorithm:
### Step1
Import the necessary modules
```
### Step2
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
### Step3
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

![f8](https://user-images.githubusercontent.com/75241366/167802381-1bbbf283-29b9-4d9f-a902-db27151f3189.jpg)

iii) Using Gaussian Filter
![f9 (1)](https://user-images.githubusercontent.com/75241366/167802474-38a232ff-96b3-409b-92a2-e77aab0333c0.jpg)


iv) Using Median Filter
![f10](https://user-images.githubusercontent.com/75241366/167802629-c3a61da2-aa8b-4333-8af3-001dd9e39bbf.jpg)


### 2. Sharpening Filters
![f11](https://user-images.githubusercontent.com/75241366/167802988-10b6cc20-3b1c-4c59-8f32-3ca2e2004ca0.jpg)


i) Using Laplacian Kernal
![f12](https://user-images.githubusercontent.com/75241366/167803074-749c376d-b229-4a1f-9273-a90ad82b1643.jpg)


ii) Using Laplacian Operator
![f12 (1)](https://user-images.githubusercontent.com/75241366/167803164-6405e54a-e2fb-49df-8c56-e5c62b9dc3ee.jpg)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
