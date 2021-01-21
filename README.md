# Image-Processing
**program 1: Develop a program to display grayscale image using read and write operation**

In digital photography, computer-generated imagery, and colorimetry, a grayscale or image is one in which the value of each pixel is a single sample representing only an amount of light; that is, it carries only intensity information. Grayscale images, a kind of black-and-white or gray monochrome, are composed exclusively of shades of gray.

To convert an image to grayscale in any of the Microsoft Office suite apps, right-click it and select Format Picture from the context menu . This will open an image editing panel on the right. Go to the Picture tab (the very last one). Expand the Picture Color options, and click the little dropdown next to the Presets for Color Saturation.

```paython
import cv2 
image=cv2.imread('original.jpg') 
grey_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY) 
cv2.imwrite('original.jpg',image) 
cv2.imshow("org",image)
cv2.imshow("gimg",grey_image) 
cv2.waitKey(0) 
cv2.destroyAllWindows()
````
**output:

![image](https://user-images.githubusercontent.com/72507759/105328425-08a44d80-5bf6-11eb-8b15-86d88428d0ba.png)




**program 2:Develop a program to perform linear transformation on image.**

Linear Transformation is type of gray level transformation that is used for image enhancement. It is a spatial domain method. It is used for manipulation of an image so that the result is more suitable than the original for a specific application.

Image scaling is a computer graphics process that increases or decreases the size of a digital image. An image can be scaled explicitly with an image viewer or editing software, or it can be done automatically by a program to fit an image into a differently sized area.

Image rotation is a common image processing routine with applications in matching, alignment, and other image-based algorithms. The input to an image rotation routine is an image, the rotation angle θ, and a point about which rotation is done.


```paython
Scaling: 

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

*output

![image](https://user-images.githubusercontent.com/72507759/105330541-6d60a780-5bf8-11eb-93f3-7d2826c72c65.png)




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



