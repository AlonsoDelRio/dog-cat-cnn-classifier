# 🐶🐱 Dog vs Cat Image Classifier — CNN + TensorFlow.js

> Proyecto académico de IA (UABC, 2022) — Clasificador de imágenes en tiempo real desplegado en el navegador.

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=flat&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00?style=flat&logo=tensorflow&logoColor=white)
![TensorFlow.js](https://img.shields.io/badge/TensorFlow.js-web-FF6F00?style=flat&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-CNN-D00000?style=flat&logo=keras&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Status](https://img.shields.io/badge/status-academic%20project-blue?style=flat)
[![Paper](https://img.shields.io/badge/paper-Overleaf%20LaTeX-47A141?style=flat&logo=overleaf&logoColor=white)](https://es.overleaf.com/read/ynwrhnsqkqvs#c41eab)

---

## 📌 Overview

A Convolutional Neural Network (CNN) trained to classify images as **dog or cat** in real time, using a webcam feed directly from the browser. The model was trained in Python/TensorFlow, exported as a `.json` + `.bin` bundle, and deployed via **TensorFlow.js** on a lightweight HTML/JS/CSS page — no server required.

> 📄 Full methodology and results available in the **[academic paper (Spanish)](https://es.overleaf.com/read/ynwrhnsqkqvs#c41eab)** — written in IEEE format using LaTeX.

---

## 🧠 Model Architecture

Three neural network models were compared:

| Model | Dataset | Notes |
|---|---|---|
| Dense (baseline) | Normal | 3 layers × 100 neurons |
| CNN | Normal | 3 Conv+MaxPool pairs (32→64→128 filters) |
| CNN + Dropout | Augmented | 50% dropout per epoch for regularization |

- **Optimizer:** Adam
- **Loss function:** Binary crossentropy (binary output: 0 = cat, 1 = dog)
- **Training epochs:** 150
- **Input size:** 100×100px grayscale

---

## 📊 Dataset

- Source: `tensorflow_datasets` — `cats_vs_dogs`
- Original size: **23,262 labeled images**
- After augmentation: **46,514 images** (transformations applied to extend dataset)

---

## ⚙️ Tech Stack

| Layer | Technology |
|---|---|
| Model training | Python, TensorFlow, Keras, NumPy, Matplotlib, OpenCV (CV2) |
| Data loading | TensorFlow Datasets |
| Visualization | TensorBoard |
| Export format | `.json` + `.bin` (TensorFlow.js compatible) |
| Web deployment | TensorFlow.js, HTML, CSS, JavaScript |
| Real-time inference | Browser webcam via Canvas API |

---

## 🚀 How It Works

```
Webcam feed
    └─► Canvas (100x100px grayscale)
            └─► TensorFlow.js model inference
                    └─► Output: "Perro" (>0.5) / "Gato" (<0.5)
```

1. User accesses the web page and grants camera access
2. A secondary canvas captures frames at 100×100px and converts to grayscale
3. Pixel data is passed to the exported TF.js model
4. The model outputs a value between 0 and 1 — displayed as a live label

---

## 📁 Repository Structure

```
├── dog-cat-classifier.ipynb   # Training notebook (Google Colab)
```

---

## 📎 Academic Reference

- **Course:** Inteligencia Artificial 2022-2 — Facultad de Ciencias, UABC
- **Institution:** Universidad Autónoma de Baja California
- **Paper:** [Read on Overleaf](https://es.overleaf.com/read/ynwrhnsqkqvs#c41eab)
- **Notebook:** Available in this repository (`dog-cat-classifier.ipynb`)

---

## 🔗 Related Projects

- [Edge-Telemetry-Pipeline](https://github.com/AlonsoDelRio/Edge-Telemetry-Pipeline) — Production IoT architecture with CI/CD
- [Bookmark Manager](https://github.com/AlonsoDelRio/bookmark-manager) — Full-stack app with FastAPI + React
