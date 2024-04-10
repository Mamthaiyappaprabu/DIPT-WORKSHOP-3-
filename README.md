# DIPT-WORKSHOP-3-
### NAME : MAMTHA I
### REG NO : 212222230076
## Instructions for submission :
i)Implement the Canny edge detection algorithm on a sample image of your choice to obtain the edges. 


ii)Share the Python code or any other programming language used, and discuss the detected edges.

iii)How do different parameter settings impact the result?

## ANSWER :
### i)Implement the Canny edge detection algorithm on a sample image of your choice to obtain the edges.


The Canny Edge Detector algorithm is a widely-used technique in image processing for detecting and enhancing edges in digital images. It consists of several stages to find the optimal edge locations while reducing noise and maintaining the continuity of the edges. Here's a brief overview of the main steps involved in the Canny Edge Detector algorithm:

***Noise Reduction***
The first step is to reduce the noise present in the input image. This is done by applying a smoothing filter, such as a Gaussian filter, which helps in removing small fluctuations in pixel intensity values.

***Gradient Calculation:*** 
In this step, the algorithm calculates the gradient of the smoothed image. The gradient represents the rate of change in intensity across the image, which helps in identifying areas with significant intensity differences. This is usually done by computing the first-order derivative of the image in both horizontal and vertical directions.

***Non-maximum Suppression:*** 
After calculating the gradient, the algorithm performs non-maximum suppression to eliminate false edges and maintain the most significant edge points. This is done by comparing the gradient direction at each point with its neighboring points and keeping only the maximum gradient value along the dominant edge direction.

***Edge Tracking:***
In this step, the algorithm connects the remaining edge points by tracking the direction of the gradient. This process helps in forming continuous edge segments and further reducing noise.

***Double-Thresholding:***
To obtain a final edge map, the algorithm applies a double-thresholding technique. It separates the edge points into strong and weak edges based on their gradient magnitude values. The strong edges are those with high gradient magnitudes, while the weak edges are those with lower gradient magnitudes. The weak edges are then removed if they don't have enough support from strong edges.

***Edge Smoothing:***
The final step is to smooth the obtained edge map to remove any small discontinuities and improve the overall quality of the detected edges. This can be achieved by applying a smoothing filter, such as a median or bilateral filter.

### ii)Share the Python code or any other programming language used, and discuss the detected edges.
```
import cv2
import matplotlib.pyplot as plt

img=cv2.imread("panda.jpg",0)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
```
```
canny=cv2.Canny(gray,120,150)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(gray)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
***OUTPUT:***

![image](https://github.com/Mamthaiyappaprabu/DIPT-WORKSHOP-3-/assets/119393563/892d21d9-1ad3-49bd-ae1e-ccd47bd3b7b5)

### iii)How do different parameter settings impact the result?

***The size of the Gaussian filter:*** 
the smoothing filter used in the first stage directly affects theresults of the Canny algorithm. Smaller filters cause less blurring, and allow detection of
small, sharp lines. A larger filter causes more blurring, smearing out the value of a given
pixel over a larger area of the image.



***Thresholds:***
the use of two thresholds with hysteresis allows more flexibility than a single- threshold approach, but general problems of thresholding approaches still apply. A
threshold set too high can miss important information. On the other hand, a threshold set
too low will falsely identify irrelevant information (such as noise) as important


