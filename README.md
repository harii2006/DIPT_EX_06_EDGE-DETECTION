# DIPT_EX_06_EDGE-DETECTION
### Name : SHRIHARI M
### Reg.No : 212225230265
### Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

### Software Required:
```
Anaconda - Python 3.7
```
Algorithm:
Step1:
Import all the necessary modules for the program.

Step2:
Load a image using imread() from cv2 module.

Step3:
Convert the image to grayscale

Step4:
Using Sobel operator from cv2,detect the edges of the image.

Step5:
Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.

### PROGRAM :
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Load the image
image = cv2.imread('j.jpg') 
# Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Apply Sobel operator


sobelx  = cv2.Sobel(src = gray_image, ddepth = cv2.CV_64F, dx = 1, dy = 0, ksize = 3) 
sobely  = cv2.Sobel(src = gray_image, ddepth = cv2.CV_64F, dx = 0, dy = 1, ksize = 3)


sobelx = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=3)  # Sobel X
sobely = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=3)  # Sobel Y
sobel_combined = cv2.magnitude(sobelx, sobely) 



plt.axis('on'); 
plt.imshow(image[:,:,::-1]); 
plt.title('Original')
plt.show()


plt.axis('on'); 
plt.imshow(gray_image, cmap='gray');
plt.title('Grayscale') 
plt.show()


plt.axis('on'); 
plt.imshow(sobelx);
plt.title('Sobel-X Edge Map')
plt.show()


plt.axis('on'); 
plt.imshow(sobely);
plt.title('Sobel-Y Edge Map');
plt.show()
plt.axis('off'); 
plt.imshow(sobel_combined, cmap='gray' ); 
plt.title('sobel_combined ');



# Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Apply Laplacian operator
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.axis('off'); 
plt.imshow(gray_image, cmap='gray'); 
plt.title('Inputimage (Gray Image)')
plt.show()
plt.imshow(laplacian, cmap='gray');
plt.axis('off'); 
plt.title('Output Image (laplacian)');



img = cv2.imread('j.jpg')
img_gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
edges = cv2.Canny(img_gray, threshold1 = 180, threshold2 = 200)
plt.axis("on"); 
plt.imshow(img[:,:,::-1]); 
plt.title('Original')
plt.show()


plt.axis("on"); 
plt.imshow(img_gray, cmap='gray');      
plt.title('Grayscale') 
plt.show()


plt.axis("on"); 
plt.imshow(edges,cmap='gray');
plt.title('Canny Edge Map');
```
### OUTPUT :
<img width="487" height="721" alt="image" src="https://github.com/user-attachments/assets/7f35a4e0-e5ab-4fc9-a6f7-72d027bc9e9e" />

<img width="517" height="704" alt="image" src="https://github.com/user-attachments/assets/c3e55015-26fa-4eee-9d8b-6d6fa2457666" />

<img width="471" height="729" alt="image" src="https://github.com/user-attachments/assets/31f495a8-5f1e-4d2a-9b55-65f92aff4e11" />

### RESULT :
Thus, we successfully executed the edges are detected using Sobel, Laplacian, and Canny edge detectors.
