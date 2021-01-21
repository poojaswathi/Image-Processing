# Image-Processing
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



