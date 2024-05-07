# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages. 

### Step2:
Read the Image and convert to grayscale. 

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program

```python
Developed By : Divadharshini.A
Register Number : 212222240027
```
# Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

# Read the Image and convert to grayscale
```python
image = cv2.imread('kitty.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('kitty.jpeg',0)
```



# Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```



# Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```


# Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```


# Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
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

## Output

### Original Image

![image](https://github.com/divyadharshiniddanbarasu/Thresholdingg/assets/119393424/ae92628f-9069-4d93-8a25-14c108703428)


### Global Thresholding

![image](https://github.com/divyadharshiniddanbarasu/Thresholdingg/assets/119393424/53be057e-6fa5-4850-9633-772fe57e8cc2)

![image](https://github.com/divyadharshiniddanbarasu/Thresholdingg/assets/119393424/1e94f1b6-5162-45b2-a1bc-a07dddac57db)

![image](https://github.com/divyadharshiniddanbarasu/Thresholdingg/assets/119393424/5a3b5254-c703-4a5f-8ad2-b24a9fcd9496)

![image](https://github.com/divyadharshiniddanbarasu/Thresholdingg/assets/119393424/ef35e68b-da8c-46a4-850a-faa0f1f07205)


### Adaptive Thresholding
![image](https://github.com/divyadharshiniddanbarasu/Thresholdingg/assets/119393424/dd7732c6-19d8-4e33-8485-63409cf484b1)

![image](https://github.com/divyadharshiniddanbarasu/Thresholdingg/assets/119393424/aec26981-b271-4520-948c-429b407941a6)



### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/divyadharshiniddanbarasu/Thresholdingg/assets/119393424/f2918fe7-3393-4385-ace1-7815218ab54c)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
