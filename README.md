# Image-Acquisition-from-Web-Camera
## Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 

ii) Display the video 

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0).

### Step 2:
Write the captured image using cv2.imwrite("NewPicture.jpg",frame).

### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5).

### Step 4:
Display the image until the loop gets over.

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180).

## Program:
``` Python
### Developed By: POOJA A
### Register No: 212222240072

## i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)

while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    
    result = False
videoCaptureObject.release()
cv2.DestroyAllWindows()



## ii) Display the video

import cv2
videoCaptureObject = cv2.VideoCapture(0)

while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
    


## iii) Display the video by resizing the window

import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=small_frame
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=small_frame
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video

import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=cv2.rotate(small_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=cv2.rotate(small_frame,cv2.ROTATE_180)
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



```
## Output
### i) Write the frame as JPG image
![WhatsApp Image 2023-11-14 at 02 43 07_1cf1dcf7](https://github.com/poojaanbu0/Image-Acquisition-from-Web-Cameraa/assets/119390329/bc0aca6d-35e5-4118-b2ec-4e38b00afb24)

### ii) Display the video
![WhatsApp Image 2023-11-14 at 02 42 36_a870daa2](https://github.com/poojaanbu0/Image-Acquisition-from-Web-Cameraa/assets/119390329/7c0630b8-82b0-43b6-953c-cc23d8332ca6)

### iii) Display the video by resizing the window
![WhatsApp Image 2023-11-14 at 02 42 12_50479f72](https://github.com/poojaanbu0/Image-Acquisition-from-Web-Cameraa/assets/119390329/18874d72-5561-4a5b-8580-0b64618a808e)

### iv) Rotate and display the video
![WhatsApp Image 2023-11-14 at 02 41 47_37d261e1](https://github.com/poojaanbu0/Image-Acquisition-from-Web-Cameraa/assets/119390329/5cdee36c-a3c4-40c1-b222-e2ee252c96e7)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
