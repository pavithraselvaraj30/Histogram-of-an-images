## Name:Pavithra S
## Reg no:212223230147
## Ex no:2  Histogram-of-an-images
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
# Developed By: Pavithra S
# Register Number: 212223230147 

import cv2
import numpy as np
import matplotlib.pyplot as plt
from google.colab.patches import cv2_imshow

# Load the image in grayscale
# Make sure to replace 'my img.jpg' with the actual path to your image file
image_path = '/content/my img.jpg'
gray_image = cv2.imread(image_path, cv2.IMREAD_GRAYSCALE)

# Check if the image was loaded successfully
if gray_image is None:
    print(f"Error: Could not load image from {image_path}")
else:
    # Perform histogram equalization
    equalized_image = cv2.equalizeHist(gray_image)

    # Display the original and equalized images
    print("Original Grayscale Image:")
    cv2_imshow(gray_image)
    print("Equalized Image:")
    cv2_imshow(equalized_image)

    # Calculate and plot histograms
    hist_original = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
    hist_equalized = cv2.calcHist([equalized_image], [0], None, [256], [0, 256])

    plt.figure(figsize=(12, 6))

    # Plot original histogram
    plt.subplot(1, 2, 1)
    plt.plot(hist_original, color='black')
    plt.title('Original Histogram')
    plt.xlabel('Pixel Intensity')
    plt.ylabel('Frequency')
    plt.xlim([0, 256])

    # Plot equalized histogram
    plt.subplot(1, 2, 2)
    plt.plot(hist_equalized, color='black')
    plt.title('Equalized Histogram')
    plt.xlabel('Pixel Intensity')
    plt.ylabel('Frequency')
    plt.xlim([0, 256])

    plt.tight_layout()
    plt.show()
```

## Output:
# Original Grayscale image

 <img width="363" height="336" alt="Screenshot 2025-09-29 114336" src="https://github.com/user-attachments/assets/cf700c5d-da40-4dc9-8f9a-301ef0331712" />

 
# Equalized image

<img width="409" height="371" alt="Screenshot 2025-09-29 114348" src="https://github.com/user-attachments/assets/ff36a249-bad4-472e-8006-577c34fd345b" />

# Original Histogram 

<img width="370" height="347" alt="Screenshot 2025-09-29 114405" src="https://github.com/user-attachments/assets/2eb0167d-4e37-4bbc-a9d5-145ee7a4ef0d" />

 # Equalized Histogram
 
 <img width="375" height="339" alt="Screenshot 2025-09-29 114425" src="https://github.com/user-attachments/assets/c48f1173-dc2d-4eb5-a145-147bc53e10aa" />




## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
