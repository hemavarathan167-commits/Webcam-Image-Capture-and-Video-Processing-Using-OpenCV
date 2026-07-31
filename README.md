# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program
import cv2

cap = cv2.VideoCapture(0)

if not cap.isOpened():
    print("Cannot open webcam")
else:
    while True:

        ret, frame = cap.read()

        if not ret:
            print("Failed to capture frame")
            break

        cv2.imwrite("captured_image.jpg", frame)

        cv2.imshow("Live Webcam", frame)

        resized = cv2.resize(frame, (800, 600))
        cv2.imshow("Resized Video", resized)

        rotated = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
        cv2.imshow("Rotated Video", rotated)

        if cv2.waitKey(1) & 0xFF == ord('q'):
            break

cap.release()
cv2.destroyAllWindows()

### Developed By:
**Name:** HEMAVARATHAN S  

### Register No:
212225240050 

---

## Output

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`
<img width="1406" height="766" alt="Screenshot 2026-07-31 093900" src="https://github.com/user-attachments/assets/ef436714-6187-471b-ab67-2f92a6ff5169" />


### ii) Display the video
Live webcam video is displayed

### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
<img width="1917" height="1078" alt="Screenshot 2026-07-31 093931" src="https://github.com/user-attachments/assets/9156f44a-e016-4390-847c-cc5a909e33cf" />


### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
<img width="1917" height="1077" alt="Screenshot 2026-07-31 093948" src="https://github.com/user-attachments/assets/17d61aca-593d-4ba4-b494-f770a61fafda" />

---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
