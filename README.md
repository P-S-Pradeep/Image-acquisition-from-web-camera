# Image-Acquisition-from-Web-Camera
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
Use VideoCapture(0) to access web camera.

### Step 2:
Use imread to read the video or image.

### Step 3:
Use imwrite to save the image.

### Step 4:
Use imshow to show the video.

### Step 5:

End the program and close the output video windows by pressing 'q'.
## Program:
``` Python
### Developed By: PRADEEP PS
### Register No: 212220230034

## i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow("apple.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()


## ii) Display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window

import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video

import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
![WhatsApp Image 2022-04-07 at 1 05 43 PM](https://user-images.githubusercontent.com/102652887/162628481-b752cadb-b599-4a25-8b3b-353351961c0e.jpeg)



### ii) Display the video
![ss1](https://user-images.githubusercontent.com/102652887/162628650-d8a3c2c7-8641-4906-9a71-bd7d76cdfd57.jpeg)



### iii) Display the video by resizing the window
![ss3](https://user-images.githubusercontent.com/102652887/162628582-7a50c549-d2df-40d1-a1ef-919f11073458.jpeg)



### iv) Rotate and display the video
![ss4](https://user-images.githubusercontent.com/102652887/162628531-8583a69a-941e-40a3-b890-4889782d9d9a.jpeg)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
