# Cats vs Dogs Image Classification using Transfer Learning

## About the Project
This project is about building an image classification model that can tell whether an image contains a cat or a dog.  
I used a pre-trained deep learning model (ResNet50) and applied transfer learning to adapt it to a custom dataset.

The main goal of this project was to understand how transfer learning works in practice and how a pre-trained CNN can be fine-tuned for a new task.

---

## Dataset
- Cats vs Dogs image dataset
- Around 1500 images for each class
- The dataset was manually organized into:
  - training
  - validation
  - test folders
- While working with the dataset, I noticed that some images were corrupted.  
  These images were detected using PIL and removed before training.

---

## Approach
1. First, I built a simple baseline CNN model from scratch to understand the performance without transfer learning.
2. Then, I used ResNet50 pre-trained on ImageNet as the base model.
3. **Phase 1 (Feature Extraction)**  
   - All layers of ResNet50 were frozen  
   - Only a custom classification head was trained
4. **Phase 2 (Fine-tuning)**  
   - The top layers of ResNet50 were unfrozen  
   - The model was trained again with a very small learning rate
5. The final model was evaluated on the test dataset using accuracy and other classification metrics.
6. Grad-CAM was used to visualize which parts of the image the model focused on while making predictions.

---

## Results
- Baseline CNN accuracy was around **70%**
- ResNet50 after Phase 1 showed improved performance
- After fine-tuning (Phase 2), the accuracy increased further (around **80%+**)
- This clearly showed the advantage of transfer learning over training a model from scratch

---

## Model Evaluation
The model was evaluated using:
- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

The confusion matrix helped in understanding how well the model classified cats and dogs and where it made mistakes.

---

## Model Interpretability
Grad-CAM visualizations were generated to understand which regions of the image influenced the model’s prediction.  
This helped in interpreting the model instead of treating it like a black box.

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

## How to Run the Project
```bash
pip install -r requirements.txt
jupyter notebook
