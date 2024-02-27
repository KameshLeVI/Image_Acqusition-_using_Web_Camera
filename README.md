# Image_Acqusition-_using_Web_Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera
<br>

### Step 2:
Use cv2.imread to read the video or image
<br>

### Step 3:
Use cv2.imwrite to save the image
<br>

### Step 4:
Use cv2.imshow to show the video
<br>

### Step 5:
End the program and close the output video window by pressing 'q'.
<br>

## Program:
``` Python
### Developed By: kamesh D
### Register No: 212222240043
```

## i) Write the frame as JPG file
```Python
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("kamesh.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('anime',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222240043_kamesh',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222240043_kamesh',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output
### i) Write the frame as JPG image
![Screenshot 2024-02-27 105045](https://github.com/KameshLeVI/Image_Acqusition-_using_Web_Camera/assets/120780633/1f485e43-75ba-47ce-9d66-84fac67870d8)

</br>
</br>

### ii) Display the video
![dip exp1](https://github.com/KameshLeVI/Image_Acqusition-_using_Web_Camera/assets/120780633/8ee49974-0742-48db-b0eb-4d6515fd6ccc)


</br>
</br>

### iii) Display the video by resizing the window
![dip exp3](https://github.com/KameshLeVI/Image_Acqusition-_using_Web_Camera/assets/120780633/6c01abf4-83d4-4442-b404-31cc058db617)

</br>
</br>

### iv) Rotate and display the video
![dip exp2](https://github.com/KameshLeVI/Image_Acqusition-_using_Web_Camera/assets/120780633/6ce7db27-5931-41b1-9e20-5c5f373a7ffe)

</br>
</br>

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
