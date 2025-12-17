# Student Instructions for Assignment Submission

## ⚠️ IMPORTANT: What You Need to Do

This repository contains a **complete implementation** of the Computer Vision Assignment 1. However, before submitting, you MUST complete the following steps:

## Required Steps Before Submission

### 1. Update Individual Contributions (MANDATORY)

Open `CV_assignment1_group_1.ipynb` and go to **Section 10: Individual Student Contributions**.

Replace the template with your actual team information:

```markdown
**Student 1 (Name: John Doe, ID: 12345)**:
- Data acquisition and preprocessing implementation
- LBP and HOG feature extraction
- Model training for k-NN and SVM
- 33.3% contribution

**Student 2 (Name: Jane Smith, ID: 67890)**:
- Edge detection implementation
- Random Forest and Logistic Regression training
- Confusion matrix and metrics visualization
- 33.3% contribution

**Student 3 (Name: Bob Wilson, ID: 13579)**:
- Custom test image creation and validation
- Analysis and discussion sections
- Final report compilation and documentation
- 33.4% contribution
```

⚠️ **WARNING**: Not filling this section will result in **0 marks** according to the assignment guidelines!

### 2. Execute the Notebook

Run all cells to generate outputs:

```bash
# Install dependencies first
pip install -r requirements.txt

# Start Jupyter
jupyter notebook CV_assignment1_group_1.ipynb
```

Then:
1. Click **Kernel → Restart & Run All**
2. Wait 10-20 minutes for all cells to execute
3. Verify all outputs are displayed correctly
4. Check that all visualizations appear

### 3. Verify Outputs

Ensure:
- [ ] All code cells have executed without errors
- [ ] All visualizations are displaying
- [ ] No error messages in any cell
- [ ] Dataset statistics are shown
- [ ] Model results are displayed
- [ ] Confusion matrix is visible
- [ ] All charts and plots are rendered

### 4. Export to HTML/PDF

#### Option A: Export to HTML (Recommended)
```bash
jupyter nbconvert --to html CV_assignment1_group_1.ipynb
```
This creates `CV_assignment1_group_1.html` with all outputs.

#### Option B: Export to PDF
```bash
# Method 1: Via HTML (easier)
jupyter nbconvert --to html CV_assignment1_group_1.ipynb
# Then open HTML in browser and print to PDF

# Method 2: Direct PDF (requires LaTeX)
jupyter nbconvert --to pdf CV_assignment1_group_1.ipynb
```

### 5. Rename File According to Convention

Rename the exported file to match the required naming convention:

```
CV_assignment1_group_<GROUP_NUMBER>_problemstatement1.html
# or
CV_assignment1_group_<GROUP_NUMBER>_problemstatement1.pdf
```

Example: `CV_assignment1_group_5_problemstatement1.pdf`

### 6. Submission Checklist

Before submitting, verify:

- [ ] ✅ Individual contributions section is completed with real names and IDs
- [ ] ✅ All cells have been executed (no empty outputs)
- [ ] ✅ All visualizations are displaying correctly
- [ ] ✅ No error messages in any cell
- [ ] ✅ File is exported to HTML or PDF with outputs visible
- [ ] ✅ File is renamed according to naming convention
- [ ] ✅ File size is reasonable (< 50MB)
- [ ] ✅ All code is properly commented and documented

## Optional Customizations

### Adjust Sample Size for Faster Execution

If the notebook takes too long, you can reduce the sample size:

In the "Sample subset" code cell, change:
```python
SAMPLE_SIZE_TRAIN = 5000   # Reduced from 15000
SAMPLE_SIZE_TEST = 1000    # Reduced from 3000
```

### Test with Your Own Handwritten Sample

Instead of synthetic letters, add your own handwritten test image:

```python
# Load your custom image
from PIL import Image
custom_image = np.array(Image.open('my_letter.jpg').convert('L'))
custom_image = cv2.resize(custom_image, (28, 28))

# Then run prediction code
```

### Add More Feature Combinations

You can add additional features:
```python
feature_combinations = {
    'LBP': ['lbp'],
    'HOG': ['hog'],
    'Edge': ['edge'],
    'All': ['lbp', 'hog', 'edge', 'pixel'],  # Add pixel features
    # Add your own combinations
}
```

## Common Issues and Solutions

### Issue 1: EMNIST Dataset Not Downloading
**Solution**: Check internet connection or manually download
```python
import emnist
emnist.list_datasets()  # This triggers download
```

### Issue 2: Out of Memory
**Solution**: Reduce sample size or close other applications
```python
SAMPLE_SIZE_TRAIN = 5000
SAMPLE_SIZE_TEST = 1000
```

### Issue 3: Long Training Time
**Solution**: Use fewer models or simpler features
```python
# Train only fast models
models = {
    'k-NN': KNeighborsClassifier(n_neighbors=5, n_jobs=-1),
    'Logistic Regression': LogisticRegression(max_iter=1000, n_jobs=-1)
}
```

### Issue 4: Matplotlib Plots Not Showing
**Solution**: Add at notebook start
```python
%matplotlib inline
```

### Issue 5: PDF Export Fails
**Solution**: Export to HTML instead, then print to PDF from browser

## Using Google Colab (Alternative)

If you prefer Google Colab:

1. Upload `CV_assignment1_group_1.ipynb` to Google Drive
2. Open with Google Colab
3. Install dependencies:
```python
!pip install emnist opencv-python scikit-image
```
4. Run all cells
5. Download as HTML: **File → Download → Download .ipynb**, then convert locally
6. Or download as PDF: **File → Print → Save as PDF**

## Grading Rubric Reminder

| Criteria | Points | What to Check |
|----------|--------|---------------|
| Import Libraries | 0.5 | All imports work, versions shown |
| Data Acquisition | 0.5 | Dataset loads, statistics displayed |
| Data Preparation | 1.0 | Preprocessing applied, visualized |
| Feature Engineering | 2.5 | Multiple features extracted, compared |
| Model Building | 1.5 | All models trained, results shown |
| Validation Metrics | 0.5 | Accuracy, F1-score displayed |
| Model Inference | 1.0 | 5 test images shown with predictions |
| Test Input | 1.5 | Custom image tested, justified |
| Documentation | 1.0 | Well-commented, clear presentation |

## Final Reminders

⚠️ **CRITICAL**:
1. **Do NOT plagiarize** - This is a template, customize with your own insights
2. **Fill individual contributions** - Required for any marks
3. **Submit with outputs** - Execute all cells before exporting
4. **Follow naming convention** - Use proper file name format
5. **Check deadline** - No late submissions accepted

## Questions?

- Review `USAGE_GUIDE.md` for detailed instructions
- Check `README.md` for project overview
- See `IMPLEMENTATION_SUMMARY.md` for technical details
- Use course discussion forum for questions

---

## Quick Submission Workflow

```bash
# 1. Update Section 10 with team info
# 2. Install dependencies
pip install -r requirements.txt

# 3. Execute notebook
jupyter notebook CV_assignment1_group_1.ipynb
# Click: Kernel → Restart & Run All

# 4. Export to HTML
jupyter nbconvert --to html CV_assignment1_group_1.ipynb

# 5. Rename file
mv CV_assignment1_group_1.html CV_assignment1_group_X_problemstatement1.html

# 6. Submit!
```

**Good luck with your submission! 🎓**
