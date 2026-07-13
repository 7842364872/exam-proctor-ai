🎓 AI-Powered Online Exam Monitoring System

A real-time exam proctoring dashboard that automatically detects cheating behaviors using computer vision, identity verification, audio monitoring, and browser activity tracking.


📌 Project Overview

Online exams face a major trust problem — no one is physically watching students. This system solves that by monitoring students automatically across multiple channels simultaneously, raising instant alerts when violations are detected.

Built with: Python · YOLO v8 · DeepFace · OpenCV · Streamlit


✨ Key Features


🎯 Real-time object detection — detects no-face, multiple faces, and electronic devices using YOLO v8
🔐 Identity verification — confirms the registered student is present throughout using DeepFace
🔊 Audio monitoring — detects suspicious sounds during the exam session
🌐 Browser tab detection — flags when student switches away from the exam tab
📊 Live dashboard — real-time alerts, session timer, and live violation report via Streamlit
⚙️ Calibration flow — verifies student identity and lighting conditions before exam begins



🛠️ Tech Stack

CategoryToolsLanguagePythonObject DetectionYOLO v8Face VerificationDeepFaceVideo ProcessingOpenCVDashboardStreamlitAudio MonitoringPyAudioIDEVS Code / PyCharmOSWindows / Linux

⚙️ How It Works

Layer 1 — Visual Monitoring (YOLO v8)
----------------------------------------

YOLO divides each camera frame into a grid and detects objects in a single forward pass — making it fast enough for real-time use. It detects:


❌ No face in frame → student left the seat
❌ Multiple faces → someone else is present
❌ Electronic devices → phone, book, or tablet detected


Layer 2 — Identity Verification (DeepFace)
---------------------------------------------

Compares the detected face against the student's registered photo throughout the session. Ensures the same person is sitting the exam from start to finish.

Layer 3 — Audio & Browser Monitoring
---------------------------------------

Audio: Detects suspicious noise levels beyond a calibrated threshold
Browser: Flags tab-switch events when student leaves the exam window


Dashboard (Streamlit)
----------------------

All three layers feed into a live Streamlit dashboard showing:


Real-time camera feed with bounding boxes
Instant alerts with timestamps
Session timer
Downloadable violation report at the end



📊 Results
-------------

MetricValueDetection Precision89%Cheating vectors covered4+ (visual, audio, browser, identity)Alert response timeReal-time (per frame)Frame optimizationEvery 3rd frame processed for performance


🚀 Getting Started
------------------------
Prerequisites

bashPython 3.8+
Webcam

Installation

bash# Clone the repository
git clone https://github.com/yourusername/ai-exam-monitoring.git
cd ai-exam-monitoring

# Install dependencies
pip install -r requirements.txt

Requirements

streamlit
opencv-python
ultralytics
deepface
pyaudio
numpy
pandas

Run the app

bashstreamlit run app.py


🔧 Challenges & Solutions
------------------------------

ChallengeSolutionVideo feed lagging heavilyOptimized to process every 3rd frame instead of every frameFalse alerts on partial face detectionTuned YOLO confidence threshold to reduce false positivesMultiple bounding boxes per faceApplied Non-Max Suppression (NMS) via YOLO's built-in IOU filtering


🔮 Future Improvements
-------------------------------

 Multi-student monitoring (support multiple camera feeds)
 Backend database to log all violations with timestamps
 Cloud deployment on AWS EC2 for remote access
 Gaze detection to track eye movement direction
 REST API for integration with existing LMS platforms



👩‍💻 Author

Poojitha Bathala


📧 pooja09020112@gmail.com
💼 LinkedIn
🐙 GitHub
🌐 Portfolio


