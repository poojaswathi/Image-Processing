# Image-Processing
**program 1: 
**Develop a program to display grayscale image using read and write operation**

In digital photography, computer-generated imagery, and colorimetry, a grayscale or image is one in which the value of each pixel is a single sample representing only an amount of light; that is, it carries only intensity information. Grayscale images, a kind of black-and-white or gray monochrome, are composed exclusively of shades of gray.

To convert an image to grayscale in any of the Microsoft Office suite apps, right-click it and select Format Picture from the context menu . This will open an image editing panel on the right. Go to the Picture tab (the very last one). Expand the Picture Color options, and click the little dropdown next to the Presets for Color Saturation.

```python
import cv2 
image=cv2.imread('original.jpg') 
grey_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY) 
cv2.imwrite('original.jpg',image) 
cv2.imshow("org",image)
cv2.imshow("gimg",grey_image) 
cv2.waitKey(0) 
cv2.destroyAllWindows()
````
**OUTPUT:

![image](https://user-images.githubusercontent.com/72507759/105328425-08a44d80-5bf6-11eb-8b15-86d88428d0ba.png)




**program 2:
**Develop a program to perform linear transformation on image.**

Linear Transformation is type of gray level transformation that is used for image enhancement. It is a spatial domain method. It is used for manipulation of an image so that the result is more suitable than the original for a specific application.

Image scaling is a computer graphics process that increases or decreases the size of a digital image. An image can be scaled explicitly with an image viewer or editing software, or it can be done automatically by a program to fit an image into a differently sized area.

Image rotation is a common image processing routine with applications in matching, alignment, and other image-based algorithms. The input to an image rotation routine is an image, the rotation angle θ, and a point about which rotation is done.

**SCALING:** 

```python
import cv2
image= cv2.imread('panda.jpg')
cv2.imshow('Original', image)
cv2.waitKey(0)
scale_percent = 500
width = int(image.shape[1] * scale_percent / 100)
height = int(image.shape[0] * scale_percent / 100)
dsize = (width, height)
output = cv2.resize(image, dsize)
cv2.imshow('Original',output) 
cv2.waitKey(0)
````

**OTPUT:

![image](https://user-images.githubusercontent.com/72507759/105330541-6d60a780-5bf8-11eb-93f3-7d2826c72c65.png)


**ROTATION:

```python
import cv2
image=cv2.imread('panda.jpg')
cv2.imshow('original',image)
cv2.waitKey(0)
src=cv2.rotate(image,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow('rotation',src)
cv2.waitKey(0)
```


**OUTPUT

![image](https://user-images.githubusercontent.com/72507759/105331748-d268cd00-5bf9-11eb-9d35-181fb601addc.png)


**Horizontal

```python
import cv2
src = cv2.imread('panda.jpg', cv2.IMREAD_UNCHANGED)
new_width = 600
dsize = ( src.shape[0],new_width)
output = cv2.resize(src, dsize, interpolation = cv2.INTER_AREA)
cv2.imwrite('pooja.jpg',output)
cv2.imshow('original',output)
cv2.waitKey(0)
```

**OUTPUT

![image](https://user-images.githubusercontent.com/72507759/105332276-70f52e00-5bfa-11eb-92f2-e97e93703043.png)



**program 3:Develop a program to find the sum and mean of a set of images. 
 a.Create ‘n’ number of images and read them from the directory and perform the operations.***
**Mean:**
   'mean' value gives the contribution of individual pixel intensity for the entire image & variance is normally used to find how each pixel varies from the neighbouring pixel (or centre pixel) and is used in classify into different regions

The OS module in python provides functions for interacting with the operating system. OS, comes under Python’s standard utility modules. This module provides a portable way of using operating system dependent functionality. The *os* and *os.path* modules include many functions to interact with the file system.

```python

import cv2
import os
path = "D:/flower"
imgs = []

files = os.listdir(path)
for file in files:
    filepath=path+"\\"+file
    imgs.append(cv2.imread(filepath))
i=0
im = []
for im in imgs:
  
    im+=imgs[i]
    i=i+1
cv2.imshow("sum of four pictures",im)
meanImg = im/len(files)
cv2.imshow("mean of four pictures",meanImg)
cv2.waitKey(0)
```
**OUTPUT





**program 1: Coverting image to gray scale and gray scale to binary image**
description:


```python
import cv2
image1=cv2.imread('panda.jpg')
cv2.imshow('original',image1)
cv2.waitKey(0)
image=cv2.imread('panda.jpg',0)
cv2.imshow('gray1',image)
cv2.waitKey(0)
ret,bimg=cv2.threshold(image,17,56,cv2.THRESH_BINARY)
cv2.imshow('binary',bimg)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
output:

![image](https://user-images.githubusercontent.com/72507759/105326836-338da200-5bf4-11eb-890c-b53c290a0907.png)



