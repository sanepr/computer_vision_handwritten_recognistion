# Usage Guide for CV Assignment 1

## Quick Start

### 1. Setup Environment

```bash
# Install dependencies
pip install -r requirements.txt
```

### 2. Run the Notebook

```bash
# Start Jupyter
jupyter notebook

# Or use Jupyter Lab
jupyter lab
```

Then open `CV_assignment1_group_1.ipynb` in your browser.

### 3. Execute All Cells

Run cells sequentially from top to bottom. The notebook will:
- Automatically download the EMNIST dataset (first run only)
- Process approximately 15,000 training images
- Train 28 different model-feature combinations
- Generate comprehensive visualizations

**Expected Runtime**: 10-20 minutes on a standard laptop

## Exporting Your Work

### Export to HTML (Recommended)

```bash
# With outputs (run notebook first)
jupyter nbconvert --to html CV_assignment1_group_1.ipynb

# Execute and export in one step
jupyter nbconvert --to html --execute CV_assignment1_group_1.ipynb
```

### Export to PDF

```bash
# Option 1: Via HTML (easier)
jupyter nbconvert --to html --execute CV_assignment1_group_1.ipynb
# Then print to PDF from browser

# Option 2: Direct PDF (requires LaTeX)
jupyter nbconvert --to pdf --execute CV_assignment1_group_1.ipynb
```

### Using Google Colab

1. Upload `CV_assignment1_group_1.ipynb` to Google Colab
2. Install dependencies:
```python
!pip install emnist opencv-python scikit-image
```
3. Run all cells
4. Download as HTML/PDF from File → Download

## Customization Options

### 1. Adjust Sample Size

In the notebook, modify these values for faster/slower execution:

```python
SAMPLE_SIZE_TRAIN = 15000  # Reduce to 5000 for faster testing
SAMPLE_SIZE_TEST = 3000    # Reduce to 1000 for faster testing
```

### 2. Select Specific Models

Comment out models you don't want to train:

```python
models = {
    'k-NN': KNeighborsClassifier(n_neighbors=5, n_jobs=-1),
    'SVM': SVC(kernel='rbf', C=10, gamma='scale', random_state=42),
    # 'Random Forest': RandomForestClassifier(...),  # Commented out
    # 'Logistic Regression': LogisticRegression(...)  # Commented out
}
```

### 3. Choose Feature Combinations

Select specific features to test:

```python
feature_combinations = {
    'LBP': ['lbp'],
    'HOG': ['hog'],
    'HOG+LBP': ['hog', 'lbp'],
    # Add or remove combinations as needed
}
```

## Troubleshooting

### Issue: EMNIST Download Fails

**Solution**: Manually download dataset
```python
# The package will auto-download on first use
# If it fails, check internet connection or try:
import emnist
emnist.list_datasets()  # This triggers download
```

### Issue: Out of Memory

**Solution**: Reduce sample size
```python
SAMPLE_SIZE_TRAIN = 5000
SAMPLE_SIZE_TEST = 1000
```

### Issue: Long Training Time

**Solution**: Use fewer models or features
```python
# Train only on best feature combination
feature_combinations = {
    'HOG+LBP+Edge': ['hog', 'lbp', 'edge']
}

# Use only fast models
models = {
    'k-NN': KNeighborsClassifier(n_neighbors=5, n_jobs=-1),
    'Logistic Regression': LogisticRegression(max_iter=1000, n_jobs=-1)
}
```

### Issue: Matplotlib Display Issues

**Solution**: Add at the start of notebook
```python
%matplotlib inline
import matplotlib
matplotlib.use('Agg')  # For non-interactive backend
```

## Assignment Submission Checklist

Before submitting, ensure:

- [ ] All cells have been executed and show outputs
- [ ] No error messages in any cell
- [ ] All visualizations are displaying correctly
- [ ] Individual contributions section is filled out
- [ ] Notebook exported to HTML or PDF format
- [ ] File named correctly: `CV_assignment1_group_1.pdf` or `.html`
- [ ] Output file size is reasonable (< 50MB)

## Tips for Better Results

1. **Clean Outputs**: Remove any debugging print statements
2. **Add Comments**: Explain your reasoning in markdown cells
3. **Interpret Results**: Add observations about what the data shows
4. **Custom Testing**: Try creating your own test images for Part 8
5. **Discussion**: Expand the analysis section with your insights

## Performance Expectations

Typical results you should see:
- Overall accuracy: 75-85%
- Training time: 5-15 minutes total
- HOG+LBP+Edge: Usually best feature combination
- Random Forest/SVM: Usually best models

## Additional Features (Optional)

Want to go beyond? Try:

1. **Gabor Filters**:
```python
from skimage.filters import gabor
def extract_gabor_features(image):
    # Add Gabor filter implementation
    pass
```

2. **PCA for Dimensionality Reduction**:
```python
from sklearn.decomposition import PCA
pca = PCA(n_components=100)
features_pca = pca.fit_transform(features)
```

3. **Cross-Validation**:
```python
from sklearn.model_selection import cross_val_score
scores = cross_val_score(model, X, y, cv=5)
```

## Getting Help

- Check the inline comments in the notebook
- Review the README.md for project overview
- Consult the problem statement PDF
- Use the course discussion forum for questions

## License

This notebook is for educational purposes as part of a Computer Vision course assignment.
