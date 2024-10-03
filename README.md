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

## Program:
```
Name : M Sanjay
Register Number : 212222240090
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('shika.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
# Display all results
plt.show
```
## Output
### Input image
![Screenshot 2024-10-03 160836](https://github.com/user-attachments/assets/48ceca7d-bd85-4f88-85c0-8256dd9379a5)

```
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
# Display all results
plt.show()
```
### Grayscale Image
![Screenshot 2024-10-03 160842](https://github.com/user-attachments/assets/343ba7e7-3fbc-4d1f-9230-83e332e40ed1)

```
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
plt.show()
```

## Canny Edge detector output
#![Screenshot 2024-10-03 160848](https://github.com/user-attachments/assets/7f155f87-2612-4341-844a-939f24fb280e)

```
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
# Display all results
plt.show()
```
### Display the result of Hough transform

![Screenshot 2024-10-03 160853](https://github.com/user-attachments/assets/63bc315b-ea6c-4723-8b84-c4902916b340)
