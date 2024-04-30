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

## program
```
Developed by:Kamali e
Register Number: 212222110015
```

```
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

## Output

### Input image and grayscale image

![323206851-1674498a-9824-4bb8-ae9c-843a7581afaa](https://github.com/Kamali22004796/Edge-Linking-using-Hough-Transformm/assets/120567837/f2b1fea6-dfa1-4b66-82c7-21ae7fc592a5)


![323207038-752b11fb-834e-4d55-9987-d2107888d070](https://github.com/Kamali22004796/Edge-Linking-using-Hough-Transformm/assets/120567837/9fb454c4-a130-4f7e-af2b-86437b137e5e)


### Canny Edge detector output

![323207393-5240d06c-7f1e-4ce2-ac45-79b78f862cde](https://github.com/Kamali22004796/Edge-Linking-using-Hough-Transformm/assets/120567837/577b18fd-c907-4705-a518-136b372a6ce1)


### Display the result of Hough transform

![323207555-b89bde7f-b9fa-41ee-b451-5e015c115c39](https://github.com/Kamali22004796/Edge-Linking-using-Hough-Transformm/assets/120567837/271630ba-104a-4776-813d-582675fda492)

## Result:
Thus the program is written with Python and OpenCV to detect lines using Hough transform.
