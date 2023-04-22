### Edge-Linking-using-Hough-Transform
### Aim:
To write a Python program to detect the lines using Hough Transform.

### Software Required:
Anaconda - Python 3.7

### Algorithm:
### Step1:
Import all the necessary packages required for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale image.

### Step4:
Using Canny edge operator from cv2, detect the edges of the image.

### Step5:
Using the HoughLinesP(), detect the line co-ordinates for every points in the images. Using For loop, draw the lines on the found co-ordinates.

### Step6:
Display the image found by the HoughLinesP() and end the program.


## Program:

### Read image and convert it to grayscale image
```
# Read image and convert it to grayscale image:

import numpy as np
import matplotlib.pyplot as plt
import cv2
image = cv2.imread("street.jpg",0)
img = cv2.GaussianBlur(image,(3,3),0)
plt.axis('off')
plt.imshow(img)
plt.show()
```
### Find the edges in the image using canny detector and display
```
# Find the edges in the image using canny detector and display:

edge = cv2.Canny(img,50,100)
plt.imshow(edge,cmap='gray')
plt.title('Edged Image after applying Canny Edge Detector')
plt.xticks([])
plt.yticks([])
plt.show()
```
### Detect points that form a line using HoughLinesP
```
# Detect points that form a line using HoughLinesP:

lines=cv2.HoughLinesP(edge,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)
```
### Draw lines on the image
```
# Draw lines on the image:

for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(250,0,0),3)
    
```
### Display the result
```
# Display the result:

plt.imshow(edge)
plt.axis('off')
plt.show()
```
## Output

### Input image and grayscale image
![Screenshot_20230422_055021](https://user-images.githubusercontent.com/95266350/233784684-138fb98b-1f91-4254-a257-1675c68a84ff.png)

### Canny Edge detector output
![Screenshot_20230422_055045](https://user-images.githubusercontent.com/95266350/233784688-23a5d6a4-78c4-46e5-8761-18261ccd9fc2.png)


### Display the result of Hough transform
![Screenshot_20230422_055058](https://user-images.githubusercontent.com/95266350/233784693-4f644df7-c433-41a7-a591-2d244461388f.png)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
