Real-Time Facial Emotion Detection

A real-time computer vision system that detects faces through a webcam and classifies emotions live: happy, sad, angry, surprised, and more, with confidence scores, running entirely in the browser.

Features:


Detects multiple faces simultaneously
Classifies 7 emotions per face: neutral, happy, sad, angry, fearful, disgusted, surprised
Live confidence score per detected emotion
Color-coded bounding box and landmark overlay per emotion, so results are readable at a glance instead of raw numbers
Runs fully client-side. No backend, no video data ever leaves the browser


Tech Stack:


JavaScript
face-api.js (built on TensorFlow.js)- face detection, facial landmarks, and expression classification
HTML5 Canvas - live overlay rendering


How It Works:


face-api.js models (Tiny Face Detector, Face Landmark 68, Face Expression) are loaded from a CDN.
A webcam video stream is captured using getUserMedia.
For each video frame, the model detects faces, extracts 68 facial landmarks, and predicts expression probabilities.
The highest-confidence emotion per face is selected and mapped to a distinct color.
A soft-filled, rounded bounding box, landmark dots, and a pill-style label (emotion + confidence %) are drawn on an HTML canvas overlay in real time.


Setup & Usage:

This project is designed to run in a Google Colab / Jupyter notebook.


Run the notebook cell containing the emotion tracker code.
It will render a live webcam view in the notebook output and request camera permission.
Look into the camera — the overlay will show a color-coded box and live emotion label with confidence score.


Notes


Requires a webcam and browser camera permissions.
All inference runs client-side via TensorFlow.js. No images or video are sent to any server.
