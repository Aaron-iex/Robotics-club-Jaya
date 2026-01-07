# Image Recognition & ArUco Markers

## 1. What is an ArUco Marker?
Robots struggle to understand the real world. A "chair" looks different from every angle. 
**ArUco Markers** are "Fiducial Markers"—reference points that are designed to be easily understood by computers, not humans.

Think of them as **Simplified QR Codes**.
* **Black & White:** High contrast makes them easy to see even in bad lighting.
* **Square Shape:** The math to calculate 3D perspective from a square is very fast.
* **Unique ID:** Each marker has a number (ID 0, ID 1, etc.). You can tell your drone: *"Land on Marker 5, but ignore Marker 2."*


## 2. Why do we use them in Drones?
In the **CropDrop Bot** theme, you might put ArUco markers on the "Landing Zone" or the "Crop Plants."

### The "Superpower": Pose Estimation
This is the main reason we use them. Because the computer knows the marker is a **square of a fixed size** (e.g., exactly 5cm x 5cm), it can analyze how "skewed" the square looks in the camera frame to calculate:
1.  **Distance:** How far the drone is from the wall.
2.  **Orientation:** Is the drone facing the wall straight-on or at a 45-degree angle?
3.  **Position:** The exact X, Y, Z coordinates of the drone relative to the marker.

## 3. How to Detect Them (Python & OpenCV)
You need the `opencv-contrib-python` library.

### The Code Pipeline
1.  **Load Dictionary:** Tell Python which set of markers you are looking for (e.g., 4x4 squares).
2.  **Detect:** Scan the image for square contours.
3.  **Draw:** Draw a box around them to visualize.

```python
import cv2
import cv2.aruco as aruco
import numpy as np

def detect_marker():
    # 1. Initialize the Camera
    cap = cv2.VideoCapture(0)
    
    # 2. Load the Dictionary (Standard 4x4 Markers)
    # We use DICT_4X4_50 (50 unique markers available)
    aruco_dict = aruco.getPredefinedDictionary(aruco.DICT_4X4_50)
    parameters = aruco.DetectorParameters()
    
    while True:
        ret, frame = cap.read()
        if not ret: break
        
        # 3. Convert to Grayscale (Computers read B&W faster)
        gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
        
        # 4. Detect Markers
        # corners: Where the square is
        # ids: What number the marker is
        corners, ids, rejected = aruco.detectMarkers(gray, aruco_dict, parameters=parameters)
        
        # 5. Draw the results
        if ids is not None:
            aruco.drawDetectedMarkers(frame, corners, ids)
            print(f"Detected Marker IDs: {ids.flatten()}")
            
        cv2.imshow('ArUco Detector', frame)
        if cv2.waitKey(1) & 0xFF == ord('q'):
            break

    cap.release()
    cv2.destroyAllWindows()

if __name__ == "__main__":
    detect_marker()
