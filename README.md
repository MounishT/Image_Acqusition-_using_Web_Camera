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
### Developed By:T MOUNISH
### Register No:212223240098
```
## i) Write the frame as JPG file
```
import cv2
videoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=videoCaptureObject.read()
    cv2.imwrite("krishna_12.jpg",frame)
    result=False
videoCaptureObject.release()
cv2.destroyAllWindows()

```
## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('image',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```
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
    cv2.imshow('212222230070',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```

## iv) Rotate and display the video
```
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
    cv2.imshow('212222230070',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```








## Output

### i) Write the frame as JPG image
![image](https://github.com/MounishT/Image_Acqusition-_using_Web_Camera/assets/138955798/6a20c631-1794-4d0e-9b86-ca1177cd6071)



### ii) Display the video
![image](https://github.com/MounishT/Image_Acqusition-_using_Web_Camera/assets/138955798/f265879d-6a71-4162-8843-c345d65ea2ba)



### iii) Display the video by resizing the window
![image](https://github.com/MounishT/Image_Acqusition-_using_Web_Camera/assets/138955798/112cd334-4fa0-4443-a73e-a9633523005e)




### iv) Rotate and display the video
![image](https://github.com/MounishT/Image_Acqusition-_using_Web_Camera/assets/138955798/43cce374-ee25-44e4-9779-d4bdb3fe099b)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
