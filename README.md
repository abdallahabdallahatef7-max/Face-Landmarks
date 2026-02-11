Face Landmark Detection with MediaPipe TasksThis project utilizes the MediaPipe Face Landmarker (Python Tasks API) to detect 478 3D facial landmarks and overlay them onto an image using OpenCV.

🚀 FeaturesUses the modern MediaPipe Tasks API for high-performance detection.
Converts normalized coordinates into pixel-perfect screen coordinates.

Visualizes facial geometry by drawing landmarks directly on the source image

.Automatically saves the processed result to a local directory.

🛠️ PrerequisitesBefore running the script, ensure you have the following libraries installed:Bashpip install opencv-python numpy mediapipe

📥 Model FileYou must download the pre-trained model file face_landmarker.task from the Google MediaPipe Solutions page and place it in the same directory as your script.

📂 Project Structuremain.py: The core Python script.face_landmarker.task: The trained model asset.download.jpg: Your input image.mesh_face.jpg: The output image (generated after execution).

💻 Code Logic BreakdownConfiguration: Defines the BaseOptions and FaceLandmarkerOptions, setting the maximum number of faces to detect.

Image Processing:Loads the image via OpenCV for drawing.Loads the image via MediaPipe for the AI processing task.Inference: The detect() function processes the image and returns a list of facial landmarks.
Coordinate Mapping: Since landmarks are returned in normalized values ($0.0$ to $1.0$), the script multiplies them by the image width ($w$) and height ($h$) to map them to specific pixels.Visualization: Uses cv2.circle to draw green points on every detected landmark.

⚙️ Setup & UsagePlace your target image in the project folder and name it download.jpg.Run the script:Bashpython main.py
A window will pop up showing the "FaceMesh". Press any key to close the window and save the image.
