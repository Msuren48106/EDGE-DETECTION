# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.

### Program :
```

import cv2
import matplotlib.pyplot as plt

# 1. Read the image using imread
# Replace 'your_image.jpg' with your actual file path
img = cv2.imread('rose.png')

# 2. Convert the color (Note: OpenCV reads in BGR, so we convert BGR to RGB for Matplotlib)
gray = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
gray_single_channel = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY) # Often used for processing
gray = cv2.GaussianBlur(gray, (3,3), 0)

# --- Sobel X ---
sobelx = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=5)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(gray)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(sobelx)
plt.title("Sobel X axis")
plt.axis("off")
plt.show()

# --- Sobel Y ---
# 3. Complete the Sobel Y code
sobely = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=5) 
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(gray)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(sobely)
plt.title("Sobel Y axis")
plt.axis("off")
plt.show()

# --- Sobel XY ---
sobelxy = cv2.Sobel(gray, cv2.CV_64F, 1, 1, ksize=5)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(gray)
plt.title("Original Image")
plt.axis("off")
# 4. Add the subplot command for the second image
plt.subplot(1,2,2)
plt.imshow(sobelxy)
plt.title("Sobel XY axis")
plt.axis("off")
plt.show()

# --- Laplacian ---
lap = cv2.Laplacian(gray, cv2.CV_64F)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(gray)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
# 5. Display the image using imshow
plt.imshow(lap) 
plt.title("Laplacian Edge Detector")
plt.axis("off")
plt.show()

# --- Canny ---
canny = cv2.Canny(img, 120, 150) # Canny usually works best on the original or grayscale
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(gray)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(canny, cmap='gray')
# 6. Provide the title
plt.title("Canny Edge Detection") 
plt.axis("off")
plt.show()

```

## Output:
### SOBEL EDGE DETECTOR
</br>
</br>
<img width="840" height="513" alt="Screenshot 2026-02-12 113647" src="https://github.com/user-attachments/assets/87948f7f-104a-460c-8468-64b1febac918" />

<img width="830" height="507" alt="Screenshot 2026-02-12 113657" src="https://github.com/user-attachments/assets/040b94aa-7785-46cc-81b5-5563a49ddf26" />

<img width="826" height="518" alt="Screenshot 2026-02-12 113710" src="https://github.com/user-attachments/assets/00c30ab3-43cc-449e-9010-546a4eacd385" />

</br>
</br>

### LAPLACIAN EDGE DETECTOR
</br>
</br>
<img width="817" height="515" alt="Screenshot 2026-02-12 113723" src="https://github.com/user-attachments/assets/fb264c24-1d4b-49af-954d-05ff736900da" />
</br>
</br>


### CANNY EDGE DETECTOR
</br>
</br>
<img width="811" height="528" alt="Screenshot 2026-02-12 113736" src="https://github.com/user-attachments/assets/8d9a4854-98e0-4673-a562-23e8d4dbc1bc" />
</br>
</br>
## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
