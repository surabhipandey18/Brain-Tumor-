# Brain Tumor MRI Classification & Explainability (Grad-CAM Exploration)

## Abstract
Brain tumors are among the most aggressive and life-threatening neurological conditions. They account for nearly 85–90% of all primary Central Nervous System (CNS) tumors. Each year, approximately 11,700 people are diagnosed with a brain tumor, with a 5-year survival rate of about 34% for men and 36% for women.

Magnetic Resonance Imaging (MRI) is the most reliable technique for brain tumor detection; however, manual interpretation is time-consuming, requires trained radiologists, and is prone to human error due to the complexity of tumor shapes and locations. Automated tumor detection using Deep Learning offers a promising solution.

This project explores a binary tumor detection model (tumor vs. no tumor) and applies Grad-CAM to understand model explainability. The primary objective is to analyze the strengths and limitations of Grad-CAM when used on heterogeneous MRI datasets.

---

## Project Overview
The main objectives of this repository are:

- Train a binary classifier using a transfer learning architecture (ResNet50).
- Apply Grad-CAM to identify regions influencing classifier decisions.
- Analyze model biases, incorrect interpretations, and dataset limitations.
- Document findings to guide improved future approaches.

This work is exploratory, emphasizing understanding the failure modes and behavior of deep models on medical datasets.

---

## Dataset Information
This project uses the "Brain Tumor Classification (MRI) Dataset" contributed by:

- Navoneel Chakrabarty  
- Swati Kanchan  

Dataset Team:

- Sartaj Bhuvaji  
- Ankita Kadam  
- Prajakta Bhumkar  
- Sameer Dedge  

### Dataset Classes
The dataset includes four categories:

- Glioma Tumor  
- Meningioma Tumor  
- Pituitary Tumor  
- No Tumor

### Dataset Limitations
Key challenges identified during experimentation:

- Tumor and non-tumor classes come from different MRI modalities (T1, T1CE, T2).
- Differences in intensity and contrast lead to shortcut learning.
- Grad-CAM sometimes highlights irrelevant background areas.
- The classifier may rely on brightness and skull edges instead of tumor characteristics.

These limitations are central to the interpretability issues discussed in this project.

---

## Methods

### Model
A ResNet50-based transfer learning model was used for binary classification:

- Tumor  
- No Tumor

Standard preprocessing and image resizing techniques were applied.

### Explainability Using Grad-CAM
Grad-CAM was applied to the final convolutional layers to produce activation heatmaps.  
These visualizations were used to analyze whether the classifier focused on meaningful tumor regions.

### Observations
- Grad-CAM frequently highlighted background structures and high-intensity areas.
- Tumor regions were not reliably detected in saliency maps.
- Model performance depended heavily on modality differences rather than tumor morphology.
- Accuracy alone did not reflect true learning; interpretability revealed major biases.

---

## Key Learnings
- Deep models can achieve high accuracy while relying on non-clinical shortcuts.
- Grad-CAM is effective for discovering dataset biases.
- Reliable medical imaging models require consistent MRI preprocessing and modality alignment.
- Future models should incorporate tumor segmentation or modality-standardized datasets.

---

## Future Work
Potential improvements to enhance model performance and interpretability:

- Use datasets with consistent MRI sequences.
- Incorporate segmentation masks (e.g., BraTS or Figshare datasets).
- Apply segmentation-guided classification pipelines.
- Implement counterfactual tumor removal techniques.
- Use occlusion sensitivity for causal analysis.
- Explore radiomics feature extraction.

These directions can lead to more trustworthy and clinically relevant models.

---

## Contribution
Contributions, suggestions, and improvements are welcome.  
Please create an issue or submit a pull request.

---

## Repository
GitHub Link: https://github.com/surabhipandey18/Brain-Tumor-

---

## License
This project is for research and educational purposes only.  
Please credit the original dataset authors if using this dataset.
Dataset Link: https://www.kaggle.com/datasets/sartajbhuvaji/brain-tumor-classification-mri
