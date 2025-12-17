# Adapt a Pre-trained Model for Custom Image Classification

## Overview

This project focuses on building an image classification model to identify whether an image contains a cat or a dog.  
The main objective was to understand and apply transfer learning using a pre-trained CNN model and compare its performance with a basic CNN built from scratch.

The project was implemented using TensorFlow and Keras, and all experiments were carried out in a Jupyter Notebook.

---

## Dataset
- Custom Cats vs Dogs image dataset
- Around 1500 images per class
- Dataset was manually organized into:
  - train
  - validation
  - test folders
- During preprocessing, a few corrupted images were found and removed using PIL image verification

 **Note:**  
 Due to size limitations, the dataset is not included directly in this repository.  
 The folder structure used for training is shown in the notebook.

---

## Approach
1. A simple baseline CNN model was created to understand basic performance.
2. ResNet50 pre-trained on ImageNet was used for transfer learning.
3. **Phase 1 (Feature Extraction):**
   - All layers of ResNet50 were frozen.
   - A custom classification head was added and trained.
4. **Phase 2 (Fine-tuning):**
   - The top layers of ResNet50 were unfrozen.
   - Training continued with a very small learning rate to improve performance.
5. The final model was evaluated on the test dataset.
6. Grad-CAM was used to visualize which regions of an image influenced the model’s predictions.

---

## Results
- Baseline CNN Accuracy: ~70%
- ResNet50 after Phase 1 showed improved accuracy
- After fine-tuning (Phase 2), accuracy increased further (around 80%+)
- Transfer learning clearly performed better than training a model from scratch

---

## Model Evaluation
The model was evaluated using:
- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

These metrics helped analyze both overall performance and class-wise predictions.

---

## Model Interpretability
Grad-CAM visualizations were generated to understand where the model focused while making predictions.  
This helped in interpreting the model’s decisions instead of treating it as a black box.

---

## Files Not Included in the Repository
Some files were intentionally not pushed to GitHub due to size and best practices:

- Trained model files (`.h5` / `.keras`)  
  - These files are larger than GitHub’s 100MB limit.
- Virtual environment (`venv/`)
  - Dependencies are listed in `requirements.txt`.

This follows standard machine learning project practices.

---

## Tools and Libraries Used
- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- PIL
- OpenCV
- Jupyter Notebook

---

## How to Run

pip install -r requirements.txt
jupyter notebook