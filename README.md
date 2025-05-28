# 🧠 MedSight AI

**MedSight AI** is a deep learning-based medical diagnostic tool that analyzes CT scan images of the **lungs**, **breast**, and **brain** to detect cancer and predict its severity. It generates **Grad-CAM heatmaps** for infected areas and offers personalized **Do’s and Don’ts** based on the predicted **malignancy score** (ranging from 1 to 5).

> ⚠️ This tool requires a CUDA-enabled **GPU** with **at least 8GB VRAM**. It does **not** support CPU-only systems.

---

## 🖼️ Demo

<p float="left">
  <img src="screenshots/lung_ct_original.png" width="45%" title="Uploaded CT Scan"/>
  <img src="screenshots/lung_ct_gradcam.png" width="45%" title="Grad-CAM Heatmap"/>
</p>

<p align="center">
  <img src="screenshots/predicted_class_1.png" width="80%" title="Predicted Class and Suggestions"/>
</p>

---

## 🚀 Features

- ✅ Detects presence and severity of cancer (malignancy score: 1–5)
- 🔥 Grad-CAM heatmaps highlight the infected regions
- 🩺 Offers personalized Do’s and Don’ts based on malignancy stage
- 🫁 Fine-tuned on **LIDC-IDRI** (lung cancer CT dataset)
- 💻 User-friendly **Streamlit** web interface
- 🧠 Based on the pretrained **MedViT** architecture

---

## 📂 Input Format

- Upload `.jpg`, `.jpeg`, or `.png` files
- Best results with `.jpg` lung CT scan images

---

## 🧠 Malignancy Score Scale

| Score | Description                  |
|-------|------------------------------|
| 1     | No signs of cancer           |
| 2     | Low suspicion                |
| 3     | Indeterminate                |
| 4     | Moderately likely cancer     |
| 5     | Highly likely / serious case |

---

## 💡 Sample Prediction Output

**Class: 1 (No signs of cancer)**  
- ✅ Lungs appear healthy and clear  
- ❌ No abnormal growths or spots  
- 🛑 No treatment or follow-up required  
- 🗓️ Keep up with routine annual check-ups  

> ✔️ **Analysis Complete** — Please consult a medical professional for further evaluation.

---

## 🧪 Preprocessing Steps

### Before Model Inference:
```python
transforms.Compose([
    transforms.Resize((224, 224)),
    transforms.ToTensor(),
    transforms.Normalize(mean, std)
])
Before Grad-CAM:
Grayscale → 3-Channel RGB → Resize → Normalize → Tensor

⚙️ How to Use
Clone the repository:

bash
Copy
Edit
git clone https://github.com/shubh03210/MedSight-AI.git
cd MedSight-AI
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Launch the web app:

bash
Copy
Edit
streamlit run app.py
Upload a .jpg CT scan and view:

Grad-CAM heatmap

Malignancy score (1–5)

Health recommendations

📦 Dependencies
txt
Copy
Edit
torch==2.5.1+cu121
torchvision==0.20.1+cu121
torchaudio==2.5.1+cu121
timm==1.0.15
grad-cam==1.5.5
numpy==1.26.4
pillow==11.2.1
matplotlib==3.10.1
opencv-python==4.11.0.86
💻 Hardware Requirements
NVIDIA GPU (CUDA-enabled)

Minimum 8GB GPU memory

❌ CPU-only environments not supported

📄 License
Currently no license. Please contact the repository owner before reuse.

🙏 Acknowledgements
MedViT

LIDC-IDRI Dataset

Open-source community for libraries and tools

⚠️ Disclaimer
This tool is intended for research and educational purposes only. It is not a replacement for professional medical advice. Always consult with a certified radiologist or physician for diagnosis and treatment.

markdown
Copy
Edit

---

### ✅ Next Steps for You:

1. **Create a folder in your repo named `screenshots/`**
2. Add:
   - `lung_ct_original.png` (first CT image)
   - `lung_ct_gradcam.png` (Grad-CAM heatmap)
   - `predicted_class_1.png` (output card)
3. Add a `requirements.txt` file with the given dependencies.

Let me know if you’d like help generating the `requirements.txt`, `app.py`, or deployment instructions!







