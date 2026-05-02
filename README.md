# Cardiomegaly Detection Using Deep Learning

This project uses deep learning to detect cardiomegaly, or heart enlargement, from chest X-ray images. The goal is to explore how convolutional neural networks and transfer learning models can support early disease detection while also identifying limitations related to class imbalance, model interpretability, and real-world clinical deployment.

The final deployment allows a physician to upload a chest X-ray and enter basic patient information. The system then generates a cardiomegaly prediction along with an EMR-friendly clinical note, helping reduce documentation burden while supporting clinical decision-making.

## Dataset

- Source: NIH Chest X-ray Dataset
- Focus: Chest X-ray images labeled for cardiomegaly
- Target Variable: Cardiomegaly vs. No Cardiomegaly
- Data Type: Medical imaging data
- Key Challenge: Class imbalance and limited clinical context

  <img width="1173" height="593" alt="download" src="https://github.com/user-attachments/assets/a20c27c2-054d-4211-a29b-519dd0c0b597" />


## Models Used

1. Baseline CNN  
   - Used as an initial benchmark model
   - Helped evaluate basic image classification performance

2. ResNet50  
   - Transfer learning model used to improve feature extraction
   - Selected for stronger performance on medical image classification tasks
   
3. EfficientNetB0  
   - Lightweight and efficient transfer learning model  
   - Uses compound scaling to balance network depth, width, and resolution  
   - Provided a strong performance-to-efficiency trade-off  
   - Useful for deployment scenarios where computational resources are limited  

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

## Conclusions

This project demonstrates the potential of AI-assisted cardiomegaly detection while also showing the limitations of applying machine learning in healthcare. Although the model can support early detection, its predictions must be interpreted with clinical judgment, especially due to issues such as false positives, class imbalance, and limited patient context.

## Future Work

Improve dataset balance
Add more demographic fairness analysis
Incorporate clinical text or patient history
Improve Grad-CAM explainability
Test the model on external datasets
Expand the EMR-style deployment interface

## Citations

   Fawcett, T. (2006). An introduction to ROC analysis. Pattern Recognition Letters, 27(8), 861–874. https://doi.org/10.1016/j.patrec.2005.10.010] 

   LeCun, Y., Bottou, L, Bengio, Y., & Haffner, P. (1998). Gradient-based learning applied to document recognition. Proceedings of the IEEE, 86(11), 2278–2324. https://doi.org/10.1109/5.726791

   Litjens, G., Kooi, T., Bejnordi, B. E., Setio, A. A. A., Ciompi, F., Ghafoorian, M., … Sánchez, C. I. (2017). A survey on deep learning in medical image analysis. Medical Image Analysis, 42, 60–88. https://doi.org/10.1016/j.media.2017.07.005

   Rahimanshu. (2021). Cardiomegaly disease prediction using CNN [Dataset]. Kaggle. https://www.kaggle.com/datasets/rahimanshu/cardiomegaly-disease-prediction-using-cnn

   Simonyan, K., & Zisserman, A. (2015). Very deep convolutional networks for large-scale image recognition (arXiv:1409.1556). https://doi.org/10.48550/arXiv.1409.1556

   TensorFlow Developers. (2015). TensorFlow: Large-scale machine learning on heterogeneous systems. https://www.tensorflow.org/
