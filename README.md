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
output:





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



