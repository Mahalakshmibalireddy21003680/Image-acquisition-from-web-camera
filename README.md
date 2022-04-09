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
Import Opencv Package.
<br>

### Step 2:
Capture the Video from the WebCamera.
<br>

### Step 3:
Write the image to a file.
<br>

### Step 4:
Show the image or the live camera.
<br>

### Step 5:
End the program.
<br>

## Program:
``` Python
### Developed By:Balireddy.Mahalakshmi.
### Register No:212221240008

## i) Write the frame as JPG file
import cv2
video = cv2.VideoCapture(0)
while(True):
    t,frame = video.read()
    cv2.imwrite("Newpicture.jpg",frame)
    result=False
    if cv2.waitKey(1) == ord('b'):
        break
video.release()
cv2.destroyAllWindows()




## ii) Display the video
import cv2
pic = cv2.VideoCapture(0)
while True:
    t,frame = pic.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1) == ord('b'):      
        break
pic.release()
cv2.destroyAllWindows()




## iii) Display the video by resizing the window
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = smallerFrame
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = smallerFrame
    cv2.imshow('frame',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    cv2.imshow('frame',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()

```
## Output

i) Write the frame as JPG image
###![mahe1](https://user-images.githubusercontent.com/93427286/162565524-f53178f0-cc9a-4532-bca6-eefe87e24124.png)
</br>
</br>


### ii) Display the video
![mahe2](https://user-images.githubusercontent.com/93427286/162565557-64d8b43c-54f5-413b-b460-acb0c6348220.png)
</br>
</br>

iii) Display the video by resizing the window
###![mahe3](https://user-images.githubusercontent.com/93427286/162565623-bdf1c124-e237-49e9-834b-55c7f5c79144.png)
</br>
</br>



### iv) Rotate and display the video
![mahe4](https://user-images.githubusercontent.com/93427286/162565739-393633cc-f2c7-496d-babe-b1aea67a5a78.png)
</br>
</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
