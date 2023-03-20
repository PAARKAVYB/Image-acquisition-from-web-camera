# Image-Acquisition-from-Web-Camera
## AIM:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## SOFTWARE USED:
Anaconda - Python 3.7

## ALGORITHM:
Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0)

Step 2:
Write the captured image using cv2.imwrite("NewPicture.jpg",frame)

Step 3:
Resize the image using cv2.resize() to get a four-split screen.

Step 4:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

Step 5:
Display the image until the key to close the window is pressed.

## PROGRAM:
``` 
/*
Developed By: Paarkavy B
Register No: 212221230072
*/
```

## i) Write the frame as JPG file
```
VidCap2 = cv2.VideoCapture(0)
while(True):
    ret,frame = VidCap2.read()
    cv2.imshow('video_image',frame)
    cv2.imwrite("212221230072.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
    result = False
VidCap2.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```
VidCap=cv2.VideoCapture(0)
while(True):
    ret,frame=VidCap.read()
    cv2.imshow('video_image',frame)
    if cv2.waitKey(1) == ord('q'):
        break
VidCap.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window
```
cap=cv2.VideoCapture(0)
while(True):
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame = cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=smaller_frame
    image[height//2:,:width//2]=smaller_frame
    image[:height//2,width//2:]=smaller_frame
    image[height//2:,width//2:]=smaller_frame
    
    cv2.imshow('quadrant_screen',image)
    if cv2.waitKey(1) == ord('q'):
        break
VidCap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```
cap2=cv2.VideoCapture(0)
while(True):
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame = cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,:width//2]=smaller_frame
    image[:height//2,width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,width//2:]=smaller_frame
    
    cv2.imshow('quadrant_rotated_screen',image)
    if cv2.waitKey(1) == ord('q'):
        break
cap2.release()
cv2.destroyAllWindows()
```

## OUTPUT:

### i) Write the frame as JPG image
![output](op1.png)

### ii) Display the video
![output](op2.png)

### iii) Display the video by resizing the window
![output](op3.png)

### iv) Rotate and display the video
![output](op4.png)

## RESULT:
Thus the image is accessed from webcamera and displayed using openCV.
