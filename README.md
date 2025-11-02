# Ex 03: Histogram-of-an-images
# Name:P.Senthil Arunachalam
# Reg No:212224240147
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Name:P.Senthil Arunachalam
# Reg No:212224240147

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the image in grayscale format.
img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

# Display the images.
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

# Display the images
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

# Display the images.
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

# Display the images.
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

# Read the color image.
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

import cv2

img = cv2.imread('parrot.jpg')  # make sure extension is correct

if img is None:
    print("Image not loaded. Check path or filename.")
else:
    img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
    print("Converted to HSV successfully.")

# Convert to HSV.
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# Perform histogram equalization only on the V channel, for value intensity.
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

# Convert back to BGR format.
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

# Display the images.
#plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

# Display the histograms.
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output:
<img width="800" height="499" alt="image" src="https://github.com/user-attachments/assets/d54ed326-a12c-43e9-9091-ea33256b66c6" />
<img width="832" height="542" alt="image" src="https://github.com/user-attachments/assets/9d6495ad-c699-4002-8477-bb2426474f27" />
<img width="895" height="539" alt="image" src="https://github.com/user-attachments/assets/353900bd-deeb-4151-bc7c-b529689f2b53" />
<img width="803" height="517" alt="image" src="https://github.com/user-attachments/assets/0d32877c-656f-446f-9cc3-4d7dc57e2cf1" />
<img width="774" height="493" alt="image" src="https://github.com/user-attachments/assets/0835f491-e4dd-4da0-8d3a-2ad9c137c93d" />
<img width="857" height="553" alt="image" src="https://github.com/user-attachments/assets/e3c817b0-d95f-48f8-90e1-7fcaeff215db" />
<img width="886" height="546" alt="image" src="https://github.com/user-attachments/assets/d030522d-1851-433d-93b4-f22f6563f293" />
<img width="1372" height="465" alt="image" src="https://github.com/user-attachments/assets/fac77158-35e5-4af5-8736-9cdbeb4190d8" />




## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
