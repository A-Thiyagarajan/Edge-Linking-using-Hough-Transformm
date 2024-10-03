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
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```
image = cv2.imread('dog.jpg')  # Replace with your image path
```
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
```
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
```
```
# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)

```
```
# Display Input Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
plt.show()

# Display Grayscale Image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.show()

# Display Canny Edge Detection Output
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
plt.show()

# Display Hough Transform Result
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
plt.show()

```


## Output

### Input image and grayscale image
![image](https://github.com/user-attachments/assets/0182d68d-e5c3-4943-8fd1-c6cbe4123758)
![image](https://github.com/user-attachments/assets/abb88483-bbf8-4199-b785-c8074d94cb58)


### Canny Edge detector output
![image](https://github.com/user-attachments/assets/d17d4ada-0353-4561-bc5f-8d31b8c5570c)

### Display the result of Hough transform
![image](https://github.com/user-attachments/assets/ca3e2fa7-ba51-4c78-b5ea-3634e53822f6)


## Result: 
Thus the python program to detect the lines using Hough Transform was successfully completed.
 
