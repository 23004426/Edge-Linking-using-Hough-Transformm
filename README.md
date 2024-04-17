# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.
### Step2:
Load a image using imread() from cv2 module.
### Step3:
Convert the image to grayscale.
### Step4:
Using Canny operator from cv2,detect the edges of the image.
### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

### Program:
# Developed by: Tirupathi Jayadeep
# Register Number: 212223240169
```p
import cv2
import numpy as np
r=cv2.imread('flower.jpg',-1)
gray=cv2.cvtColor(r,cv2.COLOR_BGR2GRAY)
img = cv2.GaussianBlur(gray,(3,3),0)
cv2.imshow('original',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imshow('gray',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()

canny_edges = cv2.Canny(img, 50, 120)
cv2.imshow('canny',canny_edges)
cv2.waitKey(0)
cv2.destroyAllWindows()

lines =cv2.HoughLinesP(canny_edges, 1, np.pi/180,threshold = 15, minLineLength =5 ,
maxLineGap = 7)

for line in lines:
 x1,y1,x2,y2 = line[0]
 cv2.line(r, (x1,y1),(x2,y2),(255,0,0),3)

cv2.imshow('hough_detected',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output

## Input image and grayscale image
![image](https://github.com/23004426/Edge-Linking-using-Hough-Transformm/assets/144979327/1674498a-9824-4bb8-ae9c-843a7581afaa)
![image](https://github.com/23004426/Edge-Linking-using-Hough-Transformm/assets/144979327/752b11fb-834e-4d55-9987-d2107888d070)

## Canny Edge detector output
![image](https://github.com/23004426/Edge-Linking-using-Hough-Transformm/assets/144979327/5240d06c-7f1e-4ce2-ac45-79b78f862cde)

## Display the result of Hough transform
![image](https://github.com/23004426/Edge-Linking-using-Hough-Transformm/assets/144979327/b89bde7f-b9fa-41ee-b451-5e015c115c39)

### Result:
Thus the program is written with Python and OpenCV to detect lines using Hough transform.
