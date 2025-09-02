## Ex.No:02
## Image Acquisition using Web Camera
## Name:G.Ramanujam            
## Reg.No:212224240129 

## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
<br>
Import the cv2 and numpy package.

### Step 2:
<br>
Read the Video frame using the cv2.VideoCapture(0)

### Step 3:
<br>
Write the image using imwrite().

### Step 4:
<br>
Display the frame using the imshow().

### Step 5:
<br>
Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().

## Program:

## i)Write the frame as JPG File
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```

```
captured_image=cv2.imread("captured_frame.jpg")
```

```
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```

## ii) Display the video
```
cap=cv2.VideoCapture(0)
for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

## iii) Display the video by resizing the window
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

## iv)Rotate and display the video
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)  
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
## Output

## i)Write the frame as JPG File
<img width="662" height="530" alt="Screenshot 2025-09-02 204241" src="https://github.com/user-attachments/assets/3e6f1d23-9b1c-4cb7-a485-b60eea42e44c" />

## ii) Display the video
<img width="652" height="491" alt="Screenshot 2025-09-02 204253" src="https://github.com/user-attachments/assets/e4390bb2-c6f1-4cda-93ab-35523d5666b6" />

## iii) Display the video by resizing the window
<img width="327" height="472" alt="Screenshot 2025-09-02 204304" src="https://github.com/user-attachments/assets/49707df5-c4e5-409a-8ef0-b7547a169ff5" />

## iv)Rotate and display the video
<img width="381" height="493" alt="Screenshot 2025-09-02 204315" src="https://github.com/user-attachments/assets/5b1c9dd7-7d25-4cde-88cc-61c81a76e4ce" />


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
