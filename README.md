# HISTOGRAM
# Histogram and Histogram Equalization of an image
# Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

# Software Required:
Anaconda - Python 3.7

# Algorithm:
## Step1: 
Import necessary libraries
## Step2: 
Use cv2.calcHist(images, channels, mask, histSize, ranges[, hist[, accumulate]]) to find the histogram of the image.
## Step3: 
Plot the image and its stem plots using the plt.show() and plt.stem() functions.
## Step4: 
Equalize the grayscale image (cv2.equalizeHist().)
## Step5: 
Print and end the program.



## Program:
```python
# Developed By: Akshayaa M
# Register Number: 212222230009
import cv2
import matplotlib.pyplot as plt

# Write your code to find the histogram of gray scale image and color image channels.

## For GrayImage:
grayImage =cv2.imread('grayImage.jpg',0)
cv2.imshow('GrayImage',grayImage)
cv2.waitKey(0)
cv2.destroyAllWindows()

hist = cv2.calcHist([gray_image],[0],None,[256],[0,255])

## For ColorImage:
color_image =cv2.imread('nature.jpg',-1)
cv2.imshow('Color_Image',color_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

### For Blue channel
hist0 = cv2.calcHist([color_image],[0],None,[256],[0,255])
### For Green channel
hist1 = cv2.calcHist([color_image],[1],None,[256],[0,255])
### For Red channel 
hist2 = cv2.calcHist([color_image],[2],None,[256],[0,255])

# Display the histogram of gray scale image and channels histogram from color image

## For GrayImage

plt.figure()
plt.title("Histogram Of GrayImage")
plt.xlabel('grayscale value')
plt.ylabel('pixel count')
plt.stem(hist)
plt.show()

## For ColorImage

### For Blue channel 

plt.figure()
plt.title("Histogram Of Blue Channel")
plt.xlabel('blue value')
plt.ylabel('pixel count')
plt.stem(hist0)
plt.show()

### For Green channel 

plt.figure()
plt.title("Histogram Of Green Channel")
plt.xlabel('green value')
plt.ylabel('pixel count')
plt.stem(hist1)
plt.show()

### For Red channel 

plt.figure()
plt.title("Histogram Of Red Channel")
plt.xlabel('red value')
plt.ylabel('pixel count')
plt.stem(hist2)
plt.show()


# Write the code to perform histogram equalization of the image. 

equ_image = cv2.equalizeHist (grayImage)

equal_hist = cv2.calcHist([equ_image],[0],None,[256],[0,255])

plt.figure()
plt.title("Histogram Of Equalized Image")
plt.xlabel('grayscale value')
plt.ylabel('pixel count')
plt.stem(equal_hist)
plt.show()
```
# Output:
## Input Grayscale Image and Color Image
![histogram](1.png)
![histogram](5.png)
## Histogram of Grayscale Image and channels of Color Image
### For GrayImage
![histogram](2.png)
### For Blue Channel
![histogram](6.png)
### For Green Channel
![histogram](7.png)
### For Red Channel
![histogram](8.png)

## Histogram Equalization of Grayscale Image
![histogram](3.png)
![histogram](4.png)

# Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
