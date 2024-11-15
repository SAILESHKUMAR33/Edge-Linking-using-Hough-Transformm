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

## DEVELOPED BY: SAILESHKUMAR A
## REG NO: 212222230126
## Output
```
 import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('cute.jpeg')
# Input Image and Grayscale Image
plt.imshow(image)
plt.title('Input Image')
plt.axis('off')
plt.show()

```
![Screenshot 2024-11-15 184009](https://github.com/user-attachments/assets/3fb2248b-6364-4b23-8d36-43c575c30170)



### Input image and grayscale image
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

```

![Screenshot 2024-11-15 184121](https://github.com/user-attachments/assets/64f76f30-c6a3-4bcc-8223-95b3c13e676b)


### Canny Edge detector output
```
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)

plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
```

![image](https://github.com/Ramsai1234/Edge-Linking-using-Hough-Transformm/assets/94269989/bcb4f6f6-9fdc-4fda-8de0-58013538c232)


### Display the result of Hough transform
```
# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
# Hough Transform Result
plt.imshow(output_image)
plt.title('Hough Transform - Line Detection')
plt.axis('off')
plt.show()
# Displaying results using Matplotlib
plt.figure(figsize=(12, 12))
# Display all results
plt.show()

```
![image](https://github.com/Ramsai1234/Edge-Linking-using-Hough-Transformm/assets/94269989/27903228-30c6-4d63-a212-620266ee84c1)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.



### Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
