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

![image](https://user-images.githubusercontent.com/72507759/105334198-9a16be00-5bfc-11eb-9ddd-306a978998cb.png)


**Program4:
Develop the program to convert color image to gray image and binary image.**
**Gray Image:**
  Grayscale is a range of monochromatic shades from black to white. Therefore, a grayscale image contains only shades of gray and no color.
Many image editing programs allow you to convert a color image to black and white, or grayscale. This process removes all color information, leaving only the luminance of each pixel. Since digital images are displayed using a combination of red, green, and blue (RGB) colors, each pixel has three separate luminance values. Therefore, these three values must be combined into a single value when removing color from an image.

**Binary Image:**
   A binary image is the type of image where each pixel is black or white.Binary images are images whose pixels have only two possible intensity values they normally displayed as black and white ,numerically the two values are often 0 for black and either 1 or 255 for  white.binary image  are often produced by thresholding a grayscale or color image in order to separate  an object in the image from background.
 cv2.threshold():. For every pixel, the same threshold value is applied. If the pixel value is smaller than the threshold, it is set to 0, otherwise it is set to a maximum value. The function cv.threshold is used to apply the thresholding. The first argument is the source image, which should be a grayscale image. The second argument is the threshold value which is used to classify the pixel values. The third argument is the maximum value which is assigned to pixel values exceeding the threshold . 
   
   
  ```python
import cv2 as c
img=c.imread('i1.jpg')
c.imshow('colour image',img)
c.waitKey(0)
gray=c.imread('i1.jpg',0)
c.imshow('Result',gray)
c.waitKey(0)
ret,img1=c.threshold(gray,128,255,c.THRESH_BINARY)
c.imshow('image',img1)
c.waitKey(0)
c.destroyAllWindows()
```
**output:**

![image](https://user-images.githubusercontent.com/72507759/105335309-eadae680-5bfd-11eb-8732-0c7e5a08f131.png)
![image](https://user-images.githubusercontent.com/72507759/105336003-bb78a980-5bfe-11eb-8524-837e33369364.png)
![image](https://user-images.githubusercontent.com/72507759/105336003-bb78a980-5bfe-11eb-8524-837e33369364.png)


***Program5:Develop the program to change the image to different color spaces.***
**Color spaces in Opencv:***
Color spaces are a way to represent the color channels present in the image that gives the image that particular hue. There are several different color spaces and each has its own significance.Some of the popular color spaces are RGB (Red, Green, Blue), CMYK (Cyan, Magenta, Yellow, Black), HSV (Hue, Saturation, Value).
cv2.imread() this method loads an image from specified file.
c.cvtColor(img,c.COLOR_BGR2HSV): used to convert BGR color space to HSV color spaces
c.cvtColor(img,c.COLOR_BGR2RGB):used to convert BGR color space to RGB color spaces
 c.cvtColor(img,c.COLOR_BGR2LUV):used to convert BGR color space to LUV color spaces
 c.cvtColor(img,c.COLOR_BGR2Lab):used to convert BGR color space to Labcolor spaces
 cv2.destroyAllWindows() If we have multiple window open and we donot need those to be open we can use this method to close those all
cv2.waitKey(0) this metjod will display the output window infinetely until any key is pressed
cv2.imshow() method is used to display an image in a window. The window automatically fits to the image size.


```python
#code

import cv2 as c
img=c.imread('Rose.jpg')
c.imshow('Original',img)
c.waitKey(0)
nimg=c.cvtColor(img,c.COLOR_BGR2HSV)
c.imshow('Result1',nimg)
c.waitKey(0)
nimg1=c.cvtColor(img,c.COLOR_BGR2RGB)
c.imshow('Result2',nimg1)
c.waitKey(0)
nimg2=c.cvtColor(img,c.COLOR_BGR2LUV)
c.imshow('Result3',nimg2)
c.waitKey(0)
nimg3=c.cvtColor(img,c.COLOR_BGR2Lab)
c.imshow('Result4',nimg3)
c.waitKey(0)
c.destroyAllWindows()
```
**output:**

![image](https://user-images.githubusercontent.com/72507759/105337110-0646f100-5c00-11eb-82f3-749c3dfd26bf.png)
![image](https://user-images.githubusercontent.com/72507759/105335793-7ce2ef00-5bfe-11eb-9920-1fcd0ae8d855.png)
![image](https://user-images.githubusercontent.com/72507759/105336003-bb78a980-5bfe-11eb-8524-837e33369364.png)
![image](https://user-images.githubusercontent.com/72507759/105336213-fb3f9100-5bfe-11eb-9a5d-0765fe0fcbb1.png)
![image](https://user-images.githubusercontent.com/72507759/105336725-93d61100-5bff-11eb-929f-07f9181721ff.png)


***Program6:
Develop a program to create an image from 2D array (generate an array of random size).***
 A image is an array or a matrix of squarepixe arranged in column and rows.
 2D arary means an array of arrays in this type of array the position of an data elements is refered by two indicies instead of one.
 PIL: Python Imaging Library (abbreviated as PIL) (in newer versions known as Pillow) is a free and open-source additional library for the Python programming language that        adds support for opening, manipulating, and saving many different image file formats. 
 The numpy.zeros() function returns a new array of given shape and type, with zeros.
 cv2.waitKey(0) this metjod will display the output window infinetely until any key is pressed
 ```python
 #code
import cv2 as c
import numpy as np
from PIL import Image
array = np.zeros([100, 200, 3], dtype=np.uint8)
array[:,:100] = [255, 130, 0] 
array[:,100:] = [0, 0, 255]
img = Image.fromarray(array)
img.save('image1.png')
img.show()
c.waitKey(0)
```
**output:**

![image](https://user-images.githubusercontent.com/72507759/105337847-e106b280-5c00-11eb-85ee-7ef87b0f74c2.png)


***program7: program to  display the neighbouhood elements of  matrix:***
```python
import numpy as np
i=0
j=0
a= np.array([[1,2,3,4,5], [2,3,4,5,6],[3,4,5,6,7],[4,5,6,7,8],[5,6,7,8,9]])
print("a :\n",str(a))
def neighbors(radius, rowNumber, columnNumber):
     return [[a[i][j] if  i >= 0 and i < len(a) and j >= 0 and j < len(a[0]) else 0
                for j in range(columnNumber-1-radius, columnNumber+radius)]
                    for i in range(rowNumber-1-radius, rowNumber+radius)]
neighbors(1, 2, 3)
```
 ......
 **output:**
  a :
 [[1 2 3 4 5]
 [2 3 4 5 6]
 [3 4 5 6 7]
 [4 5 6 7 8]
 [5 6 7 8 9]]
[[2, 3, 4], [3, 4, 5], [4, 5, 6]


 ***Program 8:Program to find the sum  of neighbour values in  a matrix:***
 ```python
import numpy as np

M = [[1,2,3,4,5], [2,3,4,5,6],[3,4,5,6,7],[4,5,6,7,8],[5,6,7,8,9]]

M = np.asarray(M)
N = np.zeros(M.shape)

def sumNeighbors(M,x,y):
    l = []
    for i in range(max(0,x-1),x+2): 
        for j in range(max(0,y-1),y+2):
            try:
                t = M[i][j]
                l.append(t)
            except IndexError: 
                pass
    return sum(l)-M[x][y]

for i in range(M.shape[0]):
    for j in range(M.shape[1]):
        N[i][j] = sumNeighbors(M, i, j)

print ("Original matrix:\n", M)
print ("Summed neighbors matrix:\n", N) 
```
....
**output:**
 Original matrix:
 [[1 2 3 4 5]
 [2 3 4 5 6]
 [3 4 5 6 7]
 [4 5 6 7 8]
 [5 6 7 8 9]]
Summed neighbors matrix:
 [[ 7. 13. 18. 23. 15.]
 [13. 24. 32. 40. 27.]
 [18. 32. 40. 48. 32.]
 [23. 40. 48. 56. 37.]
 [15. 27. 32. 37. 23.]]
 ...........
 
 
 **program 9:
 program to overload the operators:**
 
```c++
#include <iostream>
using namespace std;
class matrix
{
 int r1, c1, i, j, a1;
 int a[10][10];

public:int get()
 {
  cout << "Enter the row and column size for the  matrix\n";
  cin >> r1;
  cin >> c1;
   cout << "Enter the elements of the matrix\n";
  for (i = 0; i < r1; i++)
  {
   for (j = 0; j < c1; j++)
   {
    cin>>a[i][j];

   }
  }
 
 
 };
 void operator+(matrix a1)
 {
 int c[i][j];
  
   for (i = 0; i < r1; i++)
   {
    for (j = 0; j < c1; j++)
    {
     c[i][j] = a[i][j] + a1.a[i][j];
    }
   
  }
  cout<<"addition is\n";
  for(i=0;i<r1;i++)
  {
   cout<<" ";
   for (j = 0; j < c1; j++)
   {
    cout<<c[i][j]<<"\t";
   }
   cout<<"\n";
  }

 };

  void operator-(matrix a2)
 {
 int c[i][j];
  
   for (i = 0; i < r1; i++)
   {
    for (j = 0; j < c1; j++)
    {
     c[i][j] = a[i][j] - a2.a[i][j];
    }
   
  }
  cout<<"subtraction is\n";
  for(i=0;i<r1;i++)
  {
   cout<<" ";
   for (j = 0; j < c1; j++)
   {
    cout<<c[i][j]<<"\t";
   }
   cout<<"\n";
  }
 };

 void operator*(matrix a3)
 {
  int c[i][j];

  for (i = 0; i < r1; i++)
  {
   for (j = 0; j < c1; j++)
   {
    c[i][j] =0;
    for (int k = 0; k < r1; k++)
    {
     c[i][j] += a[i][k] * (a3.a[k][j]);
    }
  }
  }
  cout << "multiplication is\n";
  for (i = 0; i < r1; i++)
  {
   cout << " ";
   for (j = 0; j < c1; j++)
   {
    cout << c[i][j] << "\t";
   }
   cout << "\n";
  }
 };

};

int main()
{
 matrix p,q;
 p.get();
 q.get();
 p + q;
 p - q;
 p * q;
return 0;
}
```
 **output:**
 
 Enter the row and column size for the  matrix
2
2
Enter the elements of the matrix
7
5
6
9
Enter the row and column size for the  matrix
2
2
Enter the elements of the matrix
4
5
6
1
addition is
 11	10	
 12	10	
subtraction is
 3	0	
 0	8	
multiplication is
 58	40	
 78	39	
 
 
 
  **program 9:
  Develop the program to read gray scale image and convert the gray image to nagative image:**
  
  
  ````python
  import cv2
import numpy as np
# Load the image
img = cv2.imread("images (3).jpg",0)
cv2.imshow('original',img)
cv2.waitKey(0)
# Check the datatype of the image
print(img.dtype)
# Subtract the img from max value(calculated from dtype)
img_neg = 255 - img
# Show the image
cv2.imshow('negative',img_neg)
cv2.waitKey(0)

`````
 
 **OUTPUT***
 ![image](https://user-images.githubusercontent.com/72507759/107623118-ddee6780-6c7e-11eb-92f9-4fec338a60e5.png)
 
 
 ***PROGRAM 10:
 


