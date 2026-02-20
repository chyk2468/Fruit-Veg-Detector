<div align="center">

# 🍎🥕 Fruit & Vegetable Detector

### Deep Learning Image Classifier — 36 Classes of Fresh Produce

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Model](https://img.shields.io/badge/Model-fruit__model.h5-brightgreen?style=for-the-badge)](fruit_model.h5)
[![Classes](https://img.shields.io/badge/Classes-36%20Produce%20Types-orange?style=for-the-badge)](#-recognized-classes)

> A **Convolutional Neural Network** trained to identify **36 types of fruits and vegetables** from images — with a pre-trained model ready to use right out of the box.

</div>

---

## 🌟 Highlights

| Feature | Detail |
|---------|--------|
| 🏷️ **36 Classes** | Covers a wide variety of common fruits & vegetables |
| 🤖 **Pre-trained Model** | Ready-to-use `fruit_model.h5` — no retraining needed |
| 📓 **Full Pipeline** | Training + Testing notebooks included |
| ⚡ **Fast Inference** | Single image prediction in milliseconds |
| 🔌 **Easy Integration** | Load model in 2 lines of Python |

---

## 🖼️ Live Demo

<img width="1637" height="826" alt="Fruit & Vegetable Detector Demo" src="https://github.com/user-attachments/assets/0f17a3d6-29ff-448b-8a38-6854a983805a" />

---

## 🥦 Recognized Classes

The model classifies images into **36 categories** of fresh produce:

| 🍎 Fruits | 🥕 Vegetables |
|-----------|--------------|
| Apple | Beetroot |
| Banana | Bell Pepper |
| Grapes | Cabbage |
| Kiwi | Capsicum |
| Lemon | Carrot |
| Mango | Cauliflower |
| Orange | Chilli Pepper |
| Paprika | Corn |
| Pear | Cucumber |
| Pineapple | Eggplant |
| Pomegranate | Garlic |
| Watermelon | Ginger |
| — | Jalepeno |
| — | Lettuce |
| — | Onion |
| — | Peas |
| — | Potato |
| — | Raddish |
| — | Soy Beans |
| — | Spinach |
| — | Sweetcorn |
| — | Sweetpotato |
| — | Tomato |
| — | Turnip |

> 36 classes total — stored in [`labels.txt`](labels.txt)

---

## ⚙️ Pipeline Overview

```
   Raw Image Dataset (fruits & vegetables)
              │
              ▼
   ┌─────────────────────────┐
   │  Data Preprocessing     │
   │  - Resize to 224×224    │
   │  - Normalize (0–1)      │
   │  - Augmentation         │
   └────────────┬────────────┘
                │
                ▼
   ┌─────────────────────────┐
   │  CNN Model Training     │  ← Training_fruit_vegetabble.ipynb
   │  - Conv2D + MaxPooling  │
   │  - Dropout              │
   │  - Dense (36 classes)   │
   │  - Softmax output       │
   └────────────┬────────────┘
                │
                ▼
   ┌─────────────────────────┐
   │  Save Model             │  → fruit_model.h5
   └────────────┬────────────┘
                │
                ▼
   ┌─────────────────────────┐
   │  Testing & Evaluation   │  ← Test.ipynb
   │  - Load model           │
   │  - Predict class        │
   │  - Display result       │
   └─────────────────────────┘
```

---

## 📁 Repository Structure

```
📦 Fruit-Veg-Detector/
├── 📓 Training_fruit_vegetabble.ipynb   # CNN model training pipeline
├── 📓 Test.ipynb                        # Model evaluation & prediction
├── 🤖 fruit_model.h5                   # Pre-trained Keras model (~27 MB)
├── 🏷️ labels.txt                       # 36 class label definitions
└── 📄 README.md                         # Project documentation
```

---

## 🚀 Quick Start

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/chyk2468/Fruit-Veg-Detector.git
cd Fruit-Veg-Detector
```

### 2️⃣ Install Dependencies

```bash
pip install tensorflow numpy pillow matplotlib
```

### 3️⃣ Load and Use the Pre-trained Model

```python
import numpy as np
from tensorflow.keras.models import load_model
from tensorflow.keras.preprocessing import image

# Load model and labels
model = load_model('fruit_model.h5')
labels = open('labels.txt').read().strip().split('\n')

# Preprocess your image
img = image.load_img('your_image.jpg', target_size=(224, 224))
img_array = image.img_to_array(img) / 255.0
img_array = np.expand_dims(img_array, axis=0)

# Predict
predictions = model.predict(img_array)
class_id = np.argmax(predictions)
confidence = predictions[0][class_id] * 100

print(f"Prediction : {labels[class_id].title()}")
print(f"Confidence : {confidence:.1f}%")
```

**Example Output:**
```
Prediction : Mango
Confidence : 94.7%
```

---

## 📓 Notebooks

### 🏋️ `Training_fruit_vegetabble.ipynb`
The end-to-end **training pipeline**:
- Loads and augments the dataset
- Builds and compiles the CNN architecture  
- Trains with callbacks (EarlyStopping, ModelCheckpoint)
- Saves the final model as `fruit_model.h5`

### 🧪 `Test.ipynb`
The **evaluation & inference notebook**:
- Loads `fruit_model.h5` and `labels.txt`
- Runs predictions on test images
- Displays results with confidence scores
- Visualizes sample predictions with matplotlib

---

## 📈 Model Details

| Parameter | Value |
|-----------|-------|
| **Architecture** | Convolutional Neural Network (CNN) |
| **Input Size** | 224 × 224 × 3 |
| **Output Classes** | 36 |
| **Activation (Output)** | Softmax |
| **Model Format** | Keras HDF5 (`.h5`) |
| **Model Size** | ~27 MB |

---

## 🛠️ Technologies Used

<div align="center">

| Category | Tool |
|----------|------|
| **Language** | Python 3.8+ |
| **Deep Learning** | TensorFlow / Keras |
| **Data Processing** | NumPy, Pillow |
| **Visualization** | Matplotlib |
| **Notebook** | Jupyter |
| **Model Format** | HDF5 (`.h5`) |

</div>

---

## 👤 Author

**Yashwant Kumar Chitchula**  
B.Tech CSE (AI & ML) — VIT Chennai

[![GitHub](https://img.shields.io/badge/GitHub-chyk2468-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/chyk2468)

---

<div align="center">

⭐ **If this project helped you, please give it a star!** ⭐

</div>
