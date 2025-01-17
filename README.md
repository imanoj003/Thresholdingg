# THRESHOLDING

### EXP : 8

### DATE : 14 / 10 / 24
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program

#### Developed By: MANOJ M
#### Register No.: 212221240027
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the image
image = cv2.imread('HappyFish.jpg')

# Convert to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display the original grayscale image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()

```
![Screenshot 2024-10-28 151746](https://github.com/user-attachments/assets/b6b9c8bd-59b6-472a-bc56-d3e861de5abd)


# Global thresholding
```
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Display the global thresholding result
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()

```




![Screenshot 2024-10-28 151751](https://github.com/user-attachments/assets/d6ae7916-e18f-4c14-aa5c-327e73d3bd42)


# Adaptive thresholding (Gaussian)
```
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                    cv2.THRESH_BINARY, 11, 2)

# Display the adaptive thresholding result
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()
```


![Screenshot 2024-10-28 151758](https://github.com/user-attachments/assets/dd3257db-5a02-4b7a-a08e-8ed0d5da11cf)





# Otsu's thresholding
```
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the Otsu thresholding result
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()
```



![Screenshot 2024-10-28 151802](https://github.com/user-attachments/assets/1f301cb4-2f84-45ac-a4b5-e8049b452bc1)






## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
