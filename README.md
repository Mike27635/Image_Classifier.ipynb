# Image Classifier using Transfer Learning

## Project Overview

This project demonstrates image classification using **Transfer Learning** with a pre-trained **Vision Transformer (ViT)** model from Hugging Face. If the ViT model cannot be downloaded, the notebook automatically falls back to a pre-trained **ResNet18** model from PyTorch.

The model is trained on a small custom dataset of five image categories and achieves high classification accuracy while requiring minimal training time.

---

## Model Architecture

The project uses transfer learning by loading a pre-trained model and replacing only its final classification layer.

### Primary Model
- Vision Transformer (ViT)
- Model: `google/vit-base-patch16-224`
- Downloaded from Hugging Face Hub

### Fallback Model
- ResNet18
- Pre-trained on ImageNet using Torchvision

### Fine-Tuning

Only the final classification layer is trained, while the remaining pre-trained layers remain frozen. This significantly reduces training time and computational cost.

---

## Training Configuration

- **Optimizer:** Adam
- **Learning Rate:** 2e-5
- **Loss Function:** CrossEntropyLoss
- **Learning Rate Scheduler:** ReduceLROnPlateau
- **Epochs:** 10
- **Batch Size:** 16
- **Target Validation Accuracy:** 85%+

---

## Results

The model achieved excellent performance using transfer learning.

- **Best Validation Accuracy:** 98%
- **Training Time:** Approximately 20–30 seconds per epoch on a T4 GPU
- **Average Confidence Score:** Displayed after prediction
- **Prediction Summary Table:** Displays true labels, predicted labels, confidence scores, and prediction status.

---

## Visualizations

The notebook generates:

- **training_curves.png**
  - Training & Validation Accuracy
  - Training & Validation Loss

- **predictions.png**
  - Predictions on unseen images
  - Confidence scores
  - Probability distributions for each class

---

## Key Concepts Demonstrated

- Transfer Learning
- Fine-Tuning
- Vision Transformer (ViT)
- ResNet18
- Hugging Face Hub
- Image Classification
- Model Evaluation
- Confidence Score Analysis

---

## Additional Features

To improve model evaluation, the project includes:

- Average Confidence Score across predictions
- Prediction Summary Table showing:
  - True Label
  - Predicted Label
  - Confidence (%)
  - Prediction Status

---

## Technologies Used

- Python
- PyTorch
- Torchvision
- Transformers (Hugging Face)
- NumPy
- Pandas
- Matplotlib
- Google Colab

---

## How to Run

1. Open `image_classifier.ipynb` in Google Colab.
2. Set the runtime to **T4 GPU**.
3. (Optional) Add your Hugging Face token to Colab Secrets as **HF_TOKEN**.
4. Run all notebook cells from top to bottom.
5. The notebook will:
   - Generate the dataset
   - Train the model
   - Evaluate performance
   - Display prediction results
   - Generate training and prediction visualizations

---

## Project Summary

This project demonstrates how transfer learning can achieve high image classification accuracy using a relatively small dataset. By leveraging pre-trained Vision Transformer and ResNet18 models, the classifier learns efficiently while requiring minimal computational resources. The addition of confidence score analysis and a prediction summary table provides a clearer understanding of the model's performance on unseen images.
