# Computer Vision Handwritten Recognition - Assignment 1

## Problem 1: Handwritten English Character Recognition Using Classical Vision & Machine Learning

This repository contains a comprehensive Jupyter notebook implementing a classical computer-vision-based recognition system for handwritten English letters (A-Z) using the EMNIST Letters dataset.

## Features

- **Low-Level Vision Processing**: Grayscale conversion, histogram equalization, Gaussian smoothing
- **Mid-Level Feature Extraction**: 
  - Edge detection (Sobel, Canny)
  - Texture descriptors (LBP - Local Binary Pattern)
  - Shape descriptors (HOG - Histogram of Oriented Gradients)
- **Machine Learning Models**:
  - k-Nearest Neighbors (k-NN)
  - Support Vector Machine (SVM)
  - Random Forest
  - Logistic Regression
- **Comprehensive Evaluation**: Accuracy, F1-score, confusion matrix, per-class analysis
- **Feature Combination Analysis**: Testing 7 different feature combinations

## Installation

1. Clone this repository:
```bash
git clone https://github.com/sanepr/computer_vision_handwritten_recognistion.git
cd computer_vision_handwritten_recognistion
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

## Usage

### Running the Jupyter Notebook

1. Start Jupyter Notebook:
```bash
jupyter notebook
```

2. Open `CV_assignment1_group_1.ipynb` in your browser

3. Run all cells sequentially to:
   - Load and explore the EMNIST Letters dataset
   - Apply preprocessing and feature extraction
   - Train multiple ML models
   - Evaluate performance with various metrics
   - Test on custom handwritten samples

### Exporting to HTML/PDF

To export the notebook with outputs:

```bash
# Export to HTML
jupyter nbconvert --to html --execute CV_assignment1_group_1.ipynb

# Export to PDF (requires additional dependencies)
jupyter nbconvert --to pdf --execute CV_assignment1_group_1.ipynb
```

## Project Structure

```
.
├── CV_assignment1_group_1.ipynb    # Main Jupyter notebook
├── requirements.txt                 # Python dependencies
├── README.md                        # This file
└── create_notebook.py              # Script to regenerate notebook
```

## Notebook Contents

1. **Import Required Libraries** - Setup and dependencies
2. **Data Acquisition** - Load EMNIST Letters dataset
3. **Data Preparation** - Preprocessing pipeline
4. **Feature Engineering** - Extract LBP, HOG, Edge features
5. **Model Building** - Train k-NN, SVM, Random Forest, Logistic Regression
6. **Validation Metrics** - Accuracy, F1-score, confusion matrix
7. **Model Inference & Evaluation** - Test on random samples
8. **Validation of Actual Test Input** - Test with custom images
9. **Analysis & Discussion** - Feature effectiveness and insights
10. **Individual Contributions** - Team member contributions

## Results

The notebook includes:
- Comprehensive performance comparison of 7 feature combinations
- 4 different machine learning models
- Detailed visualizations including:
  - Data distribution charts
  - Preprocessing effect comparisons
  - Feature visualizations
  - Model accuracy comparisons
  - Confusion matrices
  - Per-class accuracy analysis

## Key Findings

- HOG+LBP+Edge combination typically provides the best performance
- Random Forest and SVM show strong results across different features
- Feature engineering significantly impacts model performance
- Multiple evaluation metrics provide comprehensive model assessment

## Requirements

- Python 3.7+
- NumPy, Pandas, Matplotlib, Seaborn
- OpenCV, scikit-learn, scikit-image
- EMNIST dataset (automatically downloaded)

## Assignment Compliance

This notebook fulfills all requirements of the Computer Vision Assignment 1:
- ✅ All required libraries imported with comments
- ✅ Dataset loaded with statistics and visualizations
- ✅ 80-20 stratified split implemented
- ✅ Multiple preprocessing techniques applied
- ✅ Handcrafted features (LBP, HOG, Edge) extracted
- ✅ Feature normalization implemented
- ✅ Multiple classical ML models trained
- ✅ Comprehensive validation metrics computed
- ✅ Model inference on test images
- ✅ Custom test image validation
- ✅ Well-documented with clear presentation
- ✅ Clean, modular code with visualizations

## License

This project is for educational purposes as part of a Computer Vision course assignment.

## Authors

Team members and individual contributions are documented in the notebook's final section.
