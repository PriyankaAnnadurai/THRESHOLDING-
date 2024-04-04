# THRESHOLDING
## Aim

### To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
### 1. Anaconda - Python 3.7
### 2. OpenCV

## Algorithm

### Step1:

Import necessary packages



### Step2:


Read the image


### Step3:

If the read image is a color image, convert it into a grayscale image



### Step4:

Perform the threshold operation you want to do(global thresholding or adaptive thresholding or otsu's thresholding)



### Step5:

Display the Results

### Developed By : Priyanka A

### Reg.No. 212222230113

## Program

```python
# Load the necessary packages

import cv2
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale


# Read the image
img = cv2.imread('Sample.jpg')
o_image = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
image_path = 'Sample.jpg'
image = cv2.imread(image_path, cv2.IMREAD_GRAYSCALE)

if image is None:
    raise FileNotFoundError(f"Image not found at path: {image_path}")



# Use Global thresholding to segment the image

_, binary_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_BINARY)
_, binary_inv_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_BINARY_INV)
_, tozero_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_TOZERO)
_, tozero_inv_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_TOZERO_INV)
_, truncate_thresh = cv2.threshold(image, 127, 255, cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image

adaptive_mean_thresh = cv2.adaptiveThreshold(image, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 2)
adaptive_gaussian_thresh = cv2.adaptiveThreshold(image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)



# Use Otsu's method to segment the image 

_, otsu_thresh = cv2.threshold(image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results

plt.figure(figsize=(12, 15))

# Original and Gray Image
plt.subplot(1, 2, 1)
plt.imshow(o_image)
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(image, cmap='gray')
plt.title('Gray Iamge')
plt.axis('off')


 # Original, Threshold (Binary) and Threshold (Binary inverse)
plt.subplot(1, 2, 1)
plt.imshow(image, cmap='gray')
plt.title('Gray Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(binary_thresh, cmap='gray')
plt.title('Binary Threshold')
plt.axis('off')

plt.subplot(1, 2, 1)
plt.imshow(binary_thresh, cmap='gray')
plt.title('Binary Threshold')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(binary_inv_thresh, cmap='gray')
plt.title('Binary Inverse Threshold')
plt.axis('off')

#  Threshold (to Zero) and Threshold (to Inverse Zero)
plt.subplot(1, 2, 1)
plt.imshow(tozero_thresh, cmap='gray')
plt.title('Threshold(To Zero)')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(tozero_inv_thresh, cmap='gray')
plt.title('Threshold(To Inverse Zero)')
plt.axis('off')

# Original, Threshold Image (Truncate)
plt.subplot(1, 2, 1)
plt.imshow(image, cmap='gray')
plt.title('Gray Image')
plt.axis('off')


plt.subplot(1, 2, 2)
plt.imshow(truncate_thresh, cmap='gray')
plt.title('Truncate Threshold')
plt.axis('off')

# Adaptive threshold (mean) and Adaptive threshold (Gaussian)
plt.subplot(1, 2, 1)
plt.imshow(adaptive_mean_thresh, cmap='gray')
plt.title('Adaptive Threshold (Mean)')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(adaptive_gaussian_thresh, cmap='gray')
plt.title('Adaptive Threshold (Gaussian)')
plt.axis('off')



# Original, Otsu's threshold
plt.subplot(1, 2, 1)
plt.imshow(image, cmap='gray')
plt.title('Gray Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(otsu_thresh, cmap='gray')
plt.title("Otsu's Threshold")
plt.axis('off')





```
## Output

### Original Image
<br>
<br>

![image](https://github.com/PriyankaAnnadurai/THRESHOLDING-/assets/118351569/14bf45ba-b416-4a99-a29d-aa0186231e8e)

<br>
<br>

### Global Thresholding
<br>
<br>

![image](https://github.com/PriyankaAnnadurai/THRESHOLDING-/assets/118351569/a30f26ec-5415-4ca5-96ee-9ae10c29564b)

![image](https://github.com/PriyankaAnnadurai/THRESHOLDING-/assets/118351569/1095942f-2241-4a5d-bd20-91e4b54c79af)

![image](https://github.com/PriyankaAnnadurai/THRESHOLDING-/assets/118351569/786cbf64-fdd1-47fc-b460-2c3b085a8eaa)

![image](https://github.com/PriyankaAnnadurai/THRESHOLDING-/assets/118351569/91a86ccf-325b-4741-88a3-6eaab991d8ef)


<br>
<br>

### Adaptive Thresholding
<br>
<br>

![image](https://github.com/PriyankaAnnadurai/THRESHOLDING-/assets/118351569/2971b967-4a17-435f-9e84-f83233c4c86d)

<br>
<br>

### Optimum Global Thesholding using Otsu's Method
<br>
<br>

![image](https://github.com/PriyankaAnnadurai/THRESHOLDING-/assets/118351569/ba8eab62-08de-4f28-a94f-a9d484adff83)


<br>
<br>


## Result
### Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
