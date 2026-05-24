#  IMPLEMENTATION OF EROSION AND DILATION

## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:

# Step-1:
Create a black image of size 100x600 pixels.

# Step-2:
Use a specified font to write the word "Lifestyle" on the image at a defined position.

# Step-3:
Show the image containing the text without axis labels.

# Step-4:
Define a structuring element for morphological operations (e.g., a cross-shaped kernel).

# Step-5:
Apply erosion to the image using the defined structuring element to reduce the size of white regions.

# Step-6:
Apply dilation to the original image using the same structuring element to increase the size of white regions.
 
## Program:


# Import the necessary packages

```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
```

# Create the Text using cv2.putText

```python
img = np.zeros((100, 600, 3), dtype='uint8') 
font = cv2.FONT_HERSHEY_COMPLEX
text_color = (255, 255, 255)  
cv2.putText(img, 'NAVEEN KUMAR E', (60, 70), font, 2, text_color, 5, cv2.LINE_AA)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.axis('off')
plt.show()
```

# Create the structuring element

```python
kernel = np.ones((5,5),np.uint8)
kernel1 = cv2.getStructuringElement(cv2.MORPH_CROSS,(5,5))
cv2.erode(img,kernel)

kernel = np.ones((3, 3), np.uint8)
```

# Erode the image

```python
img_erode = cv2.erode(img,kernel1)
plt.imshow(img_erode)
plt.axis('off')
```


# Dilate the image

```python
img_dilate = cv2.dilate(img,kernel1)
plt.imshow(img_dilate)
plt.axis('off')
```



## Output:

### Display the input Image

<img width="666" height="440" alt="image" src="https://github.com/user-attachments/assets/89ce5661-2857-4d8c-8fef-d7492b3eb18a" />


### Display the Eroded Image

<img width="641" height="436" alt="image" src="https://github.com/user-attachments/assets/830f0d15-850a-4751-b4fb-ad5f5e228e5f" />



### Display the Dilated Image

<img width="538" height="415" alt="image" src="https://github.com/user-attachments/assets/bee02602-26a4-4e41-9c63-ffc163b71416" />


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
