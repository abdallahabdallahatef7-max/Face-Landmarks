



# Face Landmark Detection with MediaPipe Tasks

This project utilizes the **MediaPipe Face Landmarker** (Python Tasks API) to detect 478 3D facial landmarks and overlay them onto an image using **OpenCV**.

## 🚀 Features

* Uses the modern **MediaPipe Tasks API** for high-performance detection.
* Converts normalized coordinates into pixel-perfect screen coordinates.
* Visualizes facial geometry by drawing landmarks directly on the source image.
* Automatically saves the processed result to a local directory.

## 🛠️ Prerequisites

Before running the script, ensure you have the following libraries installed:

```bash
pip install opencv-python numpy mediapipe

```

### 📥 Model File

You must download the pre-trained model file `face_landmarker.task` from the [Google MediaPipe Solutions](https://www.google.com/search?q=https://developers.google.com/mediapipe/solutions/vision/face_landmarker%23models) page and place it in the same directory as your script.

## 📂 Project Structure

* `main.py`: The core Python script.
* `face_landmarker.task`: The trained model asset.
* `download.jpg`: Your input image.
* `mesh_face.jpg`: The output image (generated after execution).

## 💻 Code Logic Breakdown

1. **Configuration**: Defines the `BaseOptions` and `FaceLandmarkerOptions`, setting the maximum number of faces to detect.
2. **Image Processing**:
* Loads the image via OpenCV for drawing.
* Loads the image via MediaPipe for the AI processing task.


3. **Inference**: The `detect()` function processes the image and returns a list of facial landmarks.
4. **Coordinate Mapping**: Since landmarks are returned in normalized values ( to ), the script multiplies them by the image width () and height () to map them to specific pixels.
5. **Visualization**: Uses `cv2.circle` to draw green points on every detected landmark.

## ⚙️ Setup & Usage

1. Place your target image in the project folder and name it `download.jpg`.
2. Run the script:
```bash
python main.py

```


3. A window will pop up showing the "FaceMesh". Press **any key** to close the window and save the image.

---

### ⚠️ Important Note

Make sure the path `C:\Users\abdal\OneDrive\Desktop\nti\` exists on your machine. If it doesn't, the `cv2.imwrite` function will fail to save the image. You may want to change it to a relative path like:
`path_save = "mesh_face.jpg"`

**Would you like me to help you modify the code to run in real-time using your webcam?**
