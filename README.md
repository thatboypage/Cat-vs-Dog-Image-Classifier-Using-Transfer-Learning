# Cat-vs-Dog-Image-Classifier-Using-Transfer-Learning
This project uses transfer learning with the InceptionV3 architecture to classify images as either a cat or a dog. The model was fine-tuned on a labeled dataset and achieved 98% validation accuracy. It includes data preprocessing, model training, image prediction, and a simple interface for uploading and testing new images in real time.

## 📌 Project Overview

- **Goal**: Build a binary image classifier to detect whether an image contains a cat or a dog.
- **Model**: Pre-trained InceptionV3 (excluding top layers) with custom dense layers.
- **Dataset**: Images were loaded using `ImageDataGenerator` from directory structure.
- **Training**: Model was trained for 20 epochs and achieved **~98% validation accuracy**.

---

## 🧠 Model Architecture

- **Base**: InceptionV3 (without top layers, weights loaded from `imagenet`)
- **Added Layers**:
  - GlobalAveragePooling2D
  - Dense (1024 units, ReLU)
  - Dropout (0.2)
  - Output Dense layer (1 unit, sigmoid)

---

## 📊 Performance

| Metric      | Value     |
|-------------|-----------|
| Accuracy    | ~98%      |
| Loss        | ~0.057    |
| Epochs      | 20        |
| Optimizer   | RMSprop   |
| Loss Func.  | Binary Crossentropy |

---

## 🖼️ Sample Prediction

```python
if classes[0]>0.5:
    print("dog")
else:
    print("cat")
````

Uploaded image is resized to (150x150), normalized, and passed to the model. It returns a probability that the image is a dog.

---

## 📈 Training & Validation Graphs

* Plotted using `matplotlib`
* Training and validation accuracy/loss were visualized per epoch

---

## 🛠️ How to Run

1. Clone the repo
2. Install dependencies
3. Upload a cat or dog image
4. Run the prediction script

---

## 📦 Requirements

See [`requirements.txt`](requirements.txt)

---

## 🚀 Future Improvements

* Deploy as a Streamlit web app
* Expand to multiclass classification (e.g., include other animals)
* Add data augmentation and early stopping

---

## 🧾 License

MIT License

