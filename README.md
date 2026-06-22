# 👤 Face Recognition & Verification System

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://www.python.org)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green?logo=opencv&logoColor=white)](https://opencv.org)
[![Face Recognition](https://img.shields.io/badge/Face__Recognition-dlib-red)](https://github.com/ageitgey/face_recognition)

A Python-based facial verification and identification pipeline. This project utilizes state-of-the-art deep learning models (via the `face_recognition` library) to detect human faces within images, extract 128-dimensional facial embedding vectors, and compute distance metrics to verify whether two different photos belong to the same individual.

---

## ✨ Key Features

- **Facial Landmark & Location Detection:** Automatically pinpoints the exact bounding box coordinates `(top, right, bottom, left)` of faces in any image.
- **128-D Embedding Extraction:** Transforms high-level visual facial features into a robust numerical vector using a pre-trained dlib ResNet model.
- **Face Verification (1-to-1 Matching):** Compares unknown target face encodings against registered profiles, outputting a precise boolean (`True`/`False`) decision.
- **Color-Space Optimization:** Integrates OpenCV to safely handle color channel conversions (BGR to RGB) ensuring accurate model predictions.

---

## 🛠️ Tech Stack & Dependencies

* **Language:** Python
* **Deep Learning Framework:** `face_recognition` (built on top of `dlib`)
* **Image Processing:** `OpenCV (cv2)`
* **Array Manipulation:** `NumPy`

---

## ⚙️ Installation & Setup

### Prerequisites
The core dependency `dlib` requires CMake and a C++ compiler installed on your machine.
- **Windows:** Install Visual Studio with "Desktop development with C++".
- **macOS/Linux:** `pip install cmake`

### Environment Setup
1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
   cd your-repo-name

   Install the required libraries:Bashpip install opencv-python numpy face_recognition
🚀 How It Works
The system pipeline inside face_recognizer.ipynb follows these sequential computer vision steps:

1.Image Loading: Reads input images using fr.load_image_file().
2.Face Masking/Bounding: Finds facial zones using HOG (Histogram of Oriented Gradients) via fr.face_locations().
3.Feature Encoding: Computes facial embeddings:

Extracts structural facial landmarks into a 128-dimensional vector
sabt_sorat = fr.face_encodings(image)[0]

Distance Comparison: Measures the Euclidean distance between vectors using fr.compare_faces(). If the distance is below the default threshold (0.6), it confirms a match.

📊 Evaluation Workflow
The script demonstrates verification through two test instances:

o . Test Case 1 (Different People): Compares Image A with Image B $\rightarrow$ Output: [False] (Successfully detects identity mismatch).
o . Test Case 2 (Same Person): Compares Image A with Image C $\rightarrow$ Output: [True] (Successfully verifies identity under different lighting/angles).

📝 Roadmap / Next Steps
o . [ ] Implement Live Webcam Verification (Real-time Face Lock/Unlock).[ ]
o . Add support for a SQLite/PostgreSQL database to manage and query multiple registered users.
o . [ ] Build a lightweight web interface using Streamlit or Flask for user onboarding.

Developed by Amirali Afshariyan
