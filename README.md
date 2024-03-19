# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.
### Step2
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.
### Step3
Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.
### Step4
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.
### Step5
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.
### Step 6
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.
## Program:
### Developed By : DINESH KUMAR R
### Register Number:212222110010


### 1. Smoothing Filters

i) Using Averaging Filter
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('picture 2.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Orignal')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```
ii) Using Weighted Averaging Filter
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('picture 2.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')

```
iii) Using Gaussian Filter
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('picture 2.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```

iv) Using Median Filter
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('picture 2.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')

```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('picture 2.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
ii) Using Laplacian Operator
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('picture 2.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```

## OUTPUT:

### 1. Smoothing Filters

i) Using Averaging Filter

![01](https://github.com/DINESH18032004/Implementation-of-filter/assets/119477784/df9f85aa-77d8-4e24-bd82-182a3b6e282f)



ii) Using Weighted Averaging Filter

![02](https://github.com/DINESH18032004/Implementation-of-filter/assets/119477784/e95e5999-5ae7-4971-bb6f-f40342b0ec12)



iii) Using Gaussian Filter


![03](https://github.com/DINESH18032004/Implementation-of-filter/assets/119477784/3726da8c-e737-47cb-a141-0a751db642ca)



iv) Using Median Filter


![04](https://github.com/DINESH18032004/Implementation-of-filter/assets/119477784/55e95468-00c9-462f-b736-f20d3894968a)


### 2. Sharpening Filters


i) Using Laplacian Kernal


![05](https://github.com/DINESH18032004/Implementation-of-filter/assets/119477784/10959b13-db91-4e27-8adc-962f4869d292)


ii) Using Laplacian Operator


![06](https://github.com/DINESH18032004/Implementation-of-filter/assets/119477784/82b4fca7-84eb-4654-8306-62f9596f64c6)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
