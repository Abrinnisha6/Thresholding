# Thresholding of Images

## Aim :

To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required :

1. Anaconda - Python 3.7
2. OpenCV

## Algorithm :

### Step 1:

Load the necessary packages.

### Step 2:

Read the Image and convert to grayscale.

### Step 3:

Use Global thresholding to segment the image.

### Step 4:

Use Adaptive thresholding to segment the image.

### Step 5:

Use Otsu's method to segment the image.

### Step 6:

Display the results.

## Program :

### DEVELOPED BY : ABRIN NISHA A
### REG NO : 212222230005

### Load the necessary packages :

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Read the Image and convert to grayscale :

```python
image=cv2.imread("white.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("white.jpg",0)
```

### Use Global thresholding to segment the image :
 
```python
ret,thresh_white1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_white2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_white3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_white4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_white5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

### Use Adaptive thresholding to segment the image :

```python
ret,thresh_white6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

# Use Otsu's method to segment the image :
```python
thresh_white7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_white8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

### Display the results :

```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_white1,thresh_white2,thresh_white3,thresh_white4,thresh_white5,thresh_white6,thresh_white7,thresh_white8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```


## Output :


### Original Image and Grayscale Image :

![Screenshot 2023-04-26 140646](https://user-images.githubusercontent.com/118889454/234518970-6ec45a8b-93a6-4118-ac44-ab833122a83c.png)


### Global Thresholding :

![Screenshot 2023-04-26 140814](https://user-images.githubusercontent.com/118889454/234519940-17dab81b-051e-4754-9f03-2615a810e3e3.png)
![Screenshot 2023-04-26 141301](https://user-images.githubusercontent.com/118889454/234520615-f24f3621-b768-463c-876f-d8f9d135c7b9.png)

### Adaptive Thresholding :

![Screenshot 2023-04-26 141424](https://user-images.githubusercontent.com/118889454/234520939-4fbc7a13-6134-4405-8806-3a7804c82752.png)


### Optimum Global Thesholding using Otsu's Method :

![Screenshot 2023-04-26 141504](https://user-images.githubusercontent.com/118889454/234521114-11511627-32d5-4d42-9ef9-1e68d180bf60.png)

## Result :

Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

