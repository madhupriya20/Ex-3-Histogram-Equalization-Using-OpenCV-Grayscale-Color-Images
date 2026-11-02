# EX-3: Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---
### Developed By:
### Name: Madhupriya R

### Register No: 212224040177
____________________________  

## Program
## 1. Import the required libraries and read the grayscale image.
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('passport.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
## 2. Plot the histogram of the grayscale image.
```
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Image Histogram')
plt.show()
```
## 3. Apply histogram equalization.
```
img_eq = cv2.equalizeHist(img)
```
## 4. Display the histogram of the equalized image.
```
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')
plt.show()
```
## 5. Display the equalized grayscale image.
```
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()
```
## 6. Read the image in color mode and convert to HSV.
```
img = cv2.imread('passport.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```
## 7. Apply histogram equalization to the V channel.
```
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
```
## 8. Convert the enhanced HSV image back to BGR.
```
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```
## 9. Display the original and equalized color images.
```
plt.subplot(121)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(122)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.show()
```
## 10. Display the original and equalized images along with their histograms.
```
plt.figure(figsize=[12,10])

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Histogram Equalized')

plt.show()
```

---


---

##  Output
<img width="436" height="529" alt="image" src="https://github.com/user-attachments/assets/8b788d8a-4b02-4846-bca1-1eee07da3133" />

<img width="710" height="516" alt="image" src="https://github.com/user-attachments/assets/e6282926-fdcf-485c-8552-c775ca443dce" />

<img width="721" height="510" alt="image" src="https://github.com/user-attachments/assets/e9038c26-a7be-48e3-a89c-1c50e2c54147" />

<img width="447" height="519" alt="image" src="https://github.com/user-attachments/assets/e2b54c0a-9e62-4630-82cf-7aff87b451f4" />

<img width="440" height="519" alt="image" src="https://github.com/user-attachments/assets/a6cd0d4c-90b0-4fce-b67e-d7afd9c77f7a" />

<img width="714" height="534" alt="image" src="https://github.com/user-attachments/assets/dbc2ea3c-a73d-4232-840d-239ea91a3136" />

<img width="807" height="313" alt="image" src="https://github.com/user-attachments/assets/97460f59-454b-4017-9574-3be7f217352e" />

<img width="798" height="253" alt="image" src="https://github.com/user-attachments/assets/76923b2f-083f-4a59-bf1d-558051ad8b3b" />


### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
