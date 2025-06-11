# DeepFake Detection with SentiNelAI 🚀

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Flask](https://img.shields.io/badge/Flask-2.0.1-lightgrey)
![PyTorch](https://img.shields.io/badge/PyTorch-1.9.0-orange)
![GitHub](https://img.shields.io/github/repo-size/rudrakadel/DeepFake_SentiNelAI)

A Flask-based web application developed by **Team Wolfenstein** for **Smart India Hackathon 2024 (SIH-1683)**.  
This project addresses the detection of **face-swap-based deepfake videos** using a ResNeXt + LSTM hybrid model, achieving **90% accuracy** on benchmark datasets.

---

## 🧠 Problem Statement (SIH 1683)

> **Title**: Development of AI/ML-based solution for detection of face-swap-based deepfake videos  
> **Theme**: Miscellaneous  
> **Team**: Wolfenstein (Team ID: 33570)

Our system detects manipulated videos by analyzing spatial features (using ResNet/ResNeXt) and temporal patterns (using LSTM), ensuring accurate and explainable predictions.

---

## 🔥 Features

- 🎥 **Real-time Prediction**: Classifies videos as "REAL" or "FAKE" with confidence scores.
- 🧠 **Frame-Level Face Analysis**: Extracts and highlights faces for individual frame analysis.
- 🌡️ **Heatmap Visualization**: Visual attention maps help interpret model behavior.
- 🎚️ **Adjustable Sensitivity**: Analyze more or fewer frames using the UI slider.
- 🔒 **Model Transparency**: Uses confusion matrix, accuracy metrics, and attention maps to ensure transparency.

---

## ⚙️ Installation

### Prerequisites

- Python 3.8+
- [Git LFS](https://git-lfs.github.com/) for handling large model files

### Steps

```bash
git lfs install
git clone https://github.com/rudrakadel/DeepFake_SentiNelAI.git
cd DeepFake_SentiNelAI
pip install -r requirements.txt
```

> ⚠️ Download the trained model file (`model_90_acc_60_frames_final_data.pt`) and place it inside the `models/` folder.

---

## 🚀 Usage

1. **Start the App**:

   ```bash
   python app.py
   ```

2. **Visit** [http://localhost:5000](http://localhost:5000)

3. **Upload a Video** → Adjust the frame slider → Submit

4. **Output**:

   * ✅ REAL / ❌ FAKE label
   * 🔢 Confidence score
   * 🖼️ Face-cropped frames
   * 🔥 Heatmap overlays

---

## 🧱 Project Structure

```
DeepFake_SentiNelAI/
├── app.py                # Flask backend
├── models/               # Pretrained models
│   └── model_90_acc_60_frames_final_data.pt
├── static/               # Frontend assets
│   ├── images/           # Extracted face frames
│   └── video/            # Uploaded videos
├── templates/            # HTML pages
│   ├── first.html
│   ├── uploader.html
│   └── results.html
└── README.md
```

---

## 🔍 Technical Workflow

1. **Data Acquisition & Preprocessing**

   * Source real and fake videos
   * Split videos into frames
   * Detect and crop faces
   * Save face-only video snippets

2. **Model Development**

   * Use **ResNet/ResNeXt** for spatial feature extraction
   * Apply **LSTM** for capturing temporal sequence patterns

3. **Training & Evaluation**

   * Split into Train/Validation/Test sets
   * Train with labeled face-video sequences
   * Evaluate using confusion matrix and accuracy metrics

4. **Inference**

   * Upload video → Face detection → Frame extraction → Inference
   * Result with calibrated softmax thresholding

---

## 💡 Innovation & Uniqueness

* Combines **CNN and LSTM** in a hybrid manner for both spatial and temporal analysis
* Uses **face-only cropped videos**, enhancing detection precision
* **Heatmap visualization** for interpretable AI results
* User-controllable **frame sensitivity slider**
* Designed with performance and clarity in mind for real-world deployment

---

## 🧰 Tech Stack

* **Frontend**: HTML5, CSS, Jinja2 (Flask templates)
* **Backend**: Flask (Python)
* **ML Framework**: PyTorch
* **Face Detection**: `face_recognition`
* **Visualization**: Matplotlib & OpenCV

---

## ⚖️ Feasibility & Challenges

| Challenge             | Strategy                                   |
| --------------------- | ------------------------------------------ |
| Large datasets        | Used Git LFS + Preprocessed face videos    |
| Model overfitting     | Augmentation & proper validation splits    |
| Real-time performance | Optimized video pre-processing pipeline    |
| Explainability        | Integrated heatmap attention visualization |

---

## 🎯 Impact & Benefits

* ❗ Helps combat misinformation by detecting manipulated media
* 👨‍💻 Useful for journalists, law enforcement, and content platforms
* 📊 Transparent, interpretable, and tunable detection pipeline
* 🧠 Educational value for ML-based security projects

---

## 📜 License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

* Based on the **FaceForensics++** dataset
* Inspired by state-of-the-art DeepFake detection research
* Uses open-source tools like `face_recognition` and `PyTorch`

---

---

## 🧭 Future Enhancements

* Webcam/live-stream DeepFake detection
* Mobile-friendly UI or Android version
* RESTful API for batch detection services

---

## 📊 Optional: "How It Works" Diagram

> *Add a block diagram showing:*
> **Input Video ➡ Frame Split ➡ Face Crop ➡ ResNeXt ➡ LSTM ➡ Confidence Score ➡ Result Display + Heatmaps**

---

## 📌 SIH Presentation Deck

This solution was developed and submitted as part of **Smart India Hackathon 2024** under Problem Statement ID **SIH 1683** by **Team Wolfenstein**.
