# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
</br>Import the required libraries.
</br> 

### Step2
</br>Convert the image from BGR to RGB.
</br> 

### Step3
</br>Apply the required filters for the image separately.
</br> 

### Step4
</br>Plot the original and filtered image by using matplotlib.pyplot.
</br> 

### Step5
</br>End the program.
</br> 

## Program:
### Developed By   : YASHWINI M
### Register Number: 212223230249
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
image1=cv2.imread("animal.png")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```

## OUPUT
<img width="752" height="279" alt="image" src="https://github.com/user-attachments/assets/9a3ad644-0545-45fc-9090-27fecb1eb7a6" />

ii) Using Weighted Averaging Filter
```Python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
plt.figure(figsize=(8,8))
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
## OUPUT
<img width="694" height="482" alt="image" src="https://github.com/user-attachments/assets/467653b3-2ff6-4790-8d3b-9b21fe1acfe7" />

iii) Using Gaussian Filter
```Python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.figure(figsize=(8,8))
plt.imshow(image2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
## OUPUT
<img width="653" height="465" alt="image" src="https://github.com/user-attachments/assets/67c53566-6cae-468f-81b3-1a416a5279b9" />

iv)Using Median Filter
```Python
median=cv2.medianBlur(image2,13)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
## OUPUT
<img width="523" height="376" alt="image" src="https://github.com/user-attachments/assets/cf081f2e-b6e4-4d24-b984-3634a552247a" />

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
## OUPUT
<img width="534" height="378" alt="image" src="https://github.com/user-attachments/assets/bf97b630-48f3-44c4-a17b-11f8605a6845" />

ii) Using Laplacian Operator
```Python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
laplacian = cv2.convertScaleAbs(laplacian) 
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
## OUPUT
<img width="512" height="383" alt="image" src="https://github.com/user-attachments/assets/c94f23c4-0bd8-4603-877d-f3cce8f66fb7" />


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
