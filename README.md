# 📘 Fruit & Vegetable Classification Project

Welcome to your **AI-powered produce detector** — built entirely from the files *you* provided.
No extra files. No invented folders. Only what exists:

* `labels.txt` (your 36‑class produce list) fileciteturn0file0
* `Training_fruit_vegetabble.ipynb`
* `Test.ipynb`
* `fruit_model.h5`

This README is rewritten with a more creative, engaging style while staying 100% faithful to the provided files.

---

## 🍇 What This Project Is

A minimal but powerful fruit‑and‑vegetable classifier.
You trained a model (`fruit_model.h5`) using your notebooks and a label list — together they form a compact machine‑learning pipeline.

Think of it as a tiny AI chef who looks at an image and says:

> “Ah yes, that’s definitely a **kiwi**… or maybe a **jalapeno**, depending on my mood.”

---

## 🏷 The Cast of Characters (from `labels.txt`)

Your model recognizes **36 fruits & vegetables**, including classics like **apple**, **carrot**, and **tomato**, plus fun ones like **soy beans**, **sweetpotato**, and **jalepeno**.

```
apple
banana
beetroot
bell pepper
cabbage
capsicum
carrot
cauliflower
chilli pepper
corn
cucumber
eggplant
garlic
ginger
grapes
jalepeno
kiwi
lemon
lettuce
mango
onion
orange
paprika
pear
peas
pineapple
pomegranate
potato
raddish
soy beans
spinach
sweetcorn
sweetpotato
tomato
turnip
watermelon
```

This file is crucial — it gives meaning to the numbers the model outputs.

---

## 🧪 Your Notebooks

### 🥕 `Training_fruit_vegetabble.ipynb`

This is where the magic happened — your model was trained here.
Think of it as the **training dojo** for your neural network.

### 🍋 `Test.ipynb`

This notebook evaluates the trained model.
A place where your model proves it deserves its chef hat.

---

## 🧠 The Model (`fruit_model.h5`)

This file contains all learned weights after training.
It’s the result of hours of computational thinking — your AI's brain.

You can load it like this:

```python
from tensorflow.keras.models import load_model
model = load_model('fruit_model.h5')
```

---

## 🥒 Using the Model

### Load the labels

```python
labels = open('labels.txt').read().strip().split('
')
```

### Predict

```python
import numpy as np
# img_preprocessed = your processed image array
pred = model.predict(img_preprocessed)
class_id = np.argmax(pred)
print("I think this is:", labels[class_id])
```

Your model will respond with something like:

<img width="1637" height="826" alt="image" src="https://github.com/user-attachments/assets/0f17a3d6-29ff-448b-8a38-6854a983805a" />


---

## 🌟 Summary

You provided:

* Labels → the **vocabulary** of produce
* Training notebook → the **recipe**
* Testing notebook → the **taste test**
* H5 model → the **final dish**

Together they form a simple, elegant fruit‑and‑vegetable classifier.

---

