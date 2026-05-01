# Cardiomegaly-Detection

# Cardiomegaly Detection Using Deep Learning

This project uses deep learning to detect cardiomegaly, or heart enlargement, from chest X-ray images. The goal is to explore how convolutional neural networks and transfer learning models can support early disease detection while also identifying limitations related to class imbalance, model interpretability, and real-world clinical deployment.

The final deployment allows a physician to upload a chest X-ray and enter basic patient information. The system then generates a cardiomegaly prediction along with an EMR-friendly clinical note, helping reduce documentation burden while supporting clinical decision-making.

## Dataset

- Source: NIH Chest X-ray Dataset
- Focus: Chest X-ray images labeled for cardiomegaly
- Target Variable: Cardiomegaly vs. No Cardiomegaly
- Data Type: Medical imaging data
- Key Challenge: Class imbalance and limited clinical context

## Models Used

1. Baseline CNN  
   - Used as an initial benchmark model
   - Helped evaluate basic image classification performance

2. ResNet50  
   - Transfer learning model used to improve feature extraction
   - Selected for stronger performance on medical image classification tasks

## Evaluation Metrics

The model was evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix

Recall was especially important because false negatives in healthcare can represent missed disease cases. A higher recall means the model is better at identifying true cardiomegaly cases, even if it may increase false positives.

## Key Findings

- ResNet50 achieved stronger performance than the baseline CNN.
- The model showed higher recall than precision, meaning it was better at detecting actual cardiomegaly cases but had some risk of false positives.
- False positives may lead to unnecessary follow-up testing, but false negatives are more clinically concerning because they may delay diagnosis.
- Grad-CAM visualizations helped evaluate whether the model focused on clinically relevant chest regions.
- Class imbalance affected model performance and highlighted the importance of careful evaluation beyond accuracy.

## Deployment

The project includes a Streamlit deployment designed to resemble a simplified EMR workflow.

The physician can:

- Enter patient symptoms and history
- Upload a chest X-ray image
- Receive a cardiomegaly prediction
- Generate an EMR-ready clinical note

This connects the machine learning model to a realistic healthcare workflow, where AI acts as a support tool rather than a replacement for physicians.

## How to Reproduce Results

1. Clone the repository
2. Install required libraries
3. Prepare the chest X-ray dataset
4. Run the training notebook
5. Evaluate model performance
6. Launch the Streamlit app
