# cassava-leaf-disease-classification
Comparison of traditional machine learning and deep learning models for cassava leaf disease classification.

## 1. Project Overview

This project compares traditional machine learning and deep learning approaches for classifying cassava leaf diseases from images. The goal is to investigate how effectively different models identify cassava diseases and support early disease detection in agriculture.

The project uses a labelled image dataset containing five classes:

* **CBB** — Cassava Bacterial Blight
* **CBSD** — Cassava Brown Streak Disease
* **CGM** — Cassava Green Mottle
* **CMD** — Cassava Mosaic Disease
* **Healthy** — Healthy cassava leaves

The project evaluates 17 experiments involving traditional machine learning, custom convolutional neural networks (CNNs), and transfer-learning models.

## 2. Dataset

The dataset contains 21,397 labelled cassava leaf images from the Kaggle Cassava Leaf Disease Classification dataset.

**Source:** [Kaggle — Cassava Leaf Disease Classification](https://www.kaggle.com/competitions/cassava-leaf-disease-classification/data)

The images are processed at a resolution of 224 × 224 pixels. The dataset is divided into training, validation, and test sets using a consistent stratified split to support fair model comparisons.

The dataset is not included in this repository because of its size. Download it from Kaggle and configure the notebook to use the dataset location in your environment.

## 3. Models and Experiments

The experiments compare two main approaches.

### Traditional Machine Learning

* Logistic Regression
* Random Forest
* HistGradientBoosting, including hyperparameter tuning

Traditional models use handcrafted image features.

### Deep Learning

* Custom Convolutional Neural Network (CNN)
* MobileNetV2 transfer learning
* EfficientNetB0 transfer learning

The experiments investigate model architectures, hyperparameters, and training strategies. TensorBoard is used to monitor training and validation performance.

## 4. Best Model Results

The best recorded model was EfficientNetB0 without class weights.

| Metric         | Test result |
| -------------- | ----------: |
| Accuracy       |      82.21% |
| Macro F1-score |      0.6915 |
| Macro ROC-AUC  |      0.9446 |

The best tuned traditional model, HistGradientBoosting, achieved approximately 57.45% test accuracy and a macro F1-score of 0.4162.

These results suggest that transfer learning performed better than the tested traditional machine learning approach on this dataset. However, the macro F1-score indicates that performance across all five classes still requires improvement.

## 5. Repository Structure

```text
cassava-leaf-disease-classification/
├── README.md
├── requirements.txt
├── .gitignore
└── notebooks/
    └── cassava_classification.ipynb
```

The notebook contains the data preparation, feature extraction, model training, evaluation, and experiment analysis.

## 6. Requirements

The project uses Python and the libraries listed in `requirements.txt`, including:

* NumPy and pandas
* Matplotlib and seaborn
* scikit-learn
* TensorFlow and TensorBoard
* Pillow, SciPy, tqdm, and joblib

Install the dependencies in a compatible Python environment:

```bash
pip install -r requirements.txt
```

Check package and Python version compatibility if you encounter installation errors.

## 7. How to Run the Project

1. Clone or download this repository.
2. Download the dataset from the Kaggle competition page.
3. Extract the dataset and update the dataset path in the notebook.
4. Install the required dependencies, or open the notebook in Google Colab and install compatible versions.
5. Run the notebook cells in order to prepare the data, train the models, and evaluate their performance.
6. Review the experiment results, evaluation metrics, and TensorBoard training curves.

Training time and memory requirements depend on the hardware used. A GPU is recommended for deep learning experiments.

## 8. Experiment Tracking and Evaluation

The project evaluates models using classification metrics, including accuracy, macro F1-score, and macro ROC-AUC. Training and validation curves are monitored to assess learning behaviour and possible overfitting.

The same data split is maintained across experiments to improve the fairness and reproducibility of comparisons.

## 9. Limitations and Future Improvements

* Improve classification performance for underperforming disease classes.
* Investigate class imbalance and additional data augmentation strategies.
* Evaluate models on cassava leaf images collected under different field conditions.
* Explore model deployment for practical agricultural use.
* Assess inference speed and model size for resource-constrained devices.

## 10. Reproducibility

The notebook and dependency list are provided to support reproducibility. Results may vary with hardware, library versions, random seeds, and training settings.

The dataset and large generated artifacts are excluded from this repository.

## 11. Author

**Rachel Toronga**

African Leadership University

GitHub repository: git clone https://github.com/Rachel-png-coder/cassava-leaf-disease-classification.git
