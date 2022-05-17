# Edge-Detection
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the required packages.

### Step2:
Load the image to operate on.

### Step3:
Convert the image to grayscale image.

### Step4:
Use Sobel operator along x,y and xy directions.

### Step5:
Operate the image using Laplacian operator.

### Step6:
Operate the image using Canny Edge operator.

### Step7:
Show all the operated images output.

### Step8:
End the program.
 
## Program:

``` Python
# Import the packages
import cv2
import matplotlib.pyplot as plt

# Load the image, Convert to grayscale and remove noise
image = cv2.imread("car.jpeg")
grayImage = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imshow("OriginalImage",image)
cv2.imshow("GrayscaleImage",grayImage)
smoothImage = cv2.GaussianBlur(grayImage,(3,3),0)


# SOBEL EDGE DETECTOR
sobelx = cv2.Sobel(smoothImage,cv2.CV_64F,1,0,ksize=5)
sobely = cv2.Sobel(smoothImage,cv2.CV_64F,0,1,ksize=5)
sobelxy = cv2.Sobel(smoothImage,cv2.CV_64F,1,1,ksize=5)



# LAPLACIAN EDGE DETECTOR

laplacian = cv2.Laplacian(smoothImage,cv2.CV_64F)



# CANNY EDGE DETECTOR

cannyEdges = cv2.Canny(smoothImage,120,150)

plt.figure(1)
plt.subplot(2,2,1)
plt.imshow(smoothImage,cmap = 'gray')
cv2.imshow("sobelx",sobelx)
cv2.imshow("sobely",sobely)
cv2.imshow("sobelxy",sobelxy)
cv2.imshow("Laplacian",laplacian)
cv2.imshow("Canny Edges",cannyEdges)
plt.title("Original")
plt.xticks([])
plt.yticks([])
plt.show()



```
## Output:
### Importing
![1 2](https://user-images.githubusercontent.com/94827772/168750353-289e3999-24f2-4eef-af69-88f314f9275c.png)
</br>
![1 1](https://user-images.githubusercontent.com/94827772/168750361-e8578c2c-ea6e-478b-aad1-a36e7410a27b.png)
</br>
![1](https://user-images.githubusercontent.com/94827772/168750449-68129d53-9602-442f-9c3d-a19598689929.png)
</br>
### SOBEL EDGE DETECTOR
</br>
![3 1](https://user-images.githubusercontent.com/94827772/168751276-251ccba8-9d5a-470f-9dbf-e5d52bbc56cd.png)
</br>
![3 2](https://user-images.githubusercontent.com/94827772/168751283-fe66d6fe-483d-4edc-8da6-77a53c794c79.png)
</br>
### LAPLACIAN EDGE DETECTOR
</br>
![2 1](https://user-images.githubusercontent.com/94827772/168751134-af6ba9b9-dc42-4c50-90ad-92fd8cdc275f.png)
</br>
![3 3](https://user-images.githubusercontent.com/94827772/168751143-a6339b24-4b3e-4072-a900-333c7a976ab0.png)
</br>
### CANNY EDGE DETECTOR
</br>
![2 2](https://user-images.githubusercontent.com/94827772/168750601-c79e0e27-4127-44a1-ab50-41d82d3a1e46.png)


## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
