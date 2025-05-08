# BiasOMZ
Project materials for DS 6015: DS Capstone as part of UVA School of Data Science Master's in Data Science. The goal of this project is to review the literature for ways to evaluate bias, then implement an evaluation on a model from Intel's [Open Model Zoo](https://github.com/openvinotoolkit/open_model_zoo/tree/master) for potential bias against protected characteristic(s). 

# How to use this repo

## How to use the "Clean_Preds" Notebook

-	The Clean_preds file contains the overall methodology for specifying a model, ingesting data, and transforming data.

### 1. Set up the model
-	The first part of the notebook allows the user to choose a model and have it automatically downloaded to the file directory (using the model_name variable).
-	It contains a github link that can be followed with additional guideance on the openvino api utilization for creating a model.
-	To set up the model the user should identify one of the Open Model Zoo models (such as the face-detection-0200) and update the variable name accordingly.
-	Once that is done all variables should automatically populate with each chunk providing outlines for what they do.

### 2. Running the Model
-	The second part of the juptyer notebook transforms the selected image dataset and transforms it to fit specifically in the face-detection-0200 model
-	The data must be in the format outlined in the notbook if continuing to use the face detection model that was selected.
-	If the face detection model is not chosen, reference the github repo of the open model zoo model selected.
-	For image data provide the directory containing the files under "os.listdir" to the image processing chunk.
-	Modify this chunk accordingly for any feature engineering or changes needed to an image dataset outside of the changes that are already defined.
-	The results_df contains the predictions that can than be fed into the Aequitas tool.
-	Note that this notebook is designed to work with both this dataset and the fairface dataset, while it does provide a framework to use open vino, changes may be needed in case the user wants to use either a different dataset or a different model

## How to Use Aequitas

This project provides a framework to assess fairness in face detection models using demographic attributes. Below is a step-by-step guide to running the analysis:

### 1. Set Up the Environment
Ensure all required Python packages are installed before starting. These include:

- `pandas`
- `seaborn`
- `matplotlib`
- `scikit-learn`
- `aequitas`
- `dataframe_image`

You can install them via `pip` or your environment manager of choice.

### 2. Prepare Your Data
You will need two datasets:
- **Model output** (e.g., `image_metadata.csv`) containing predicted detection confidences for each image.
- **FairFace training dataset** (e.g., `fairface_label_train.csv`) including demographic labels (`gender`, `race`, `age`).

### 3. Merge Predictions with Ground Truth
Load both datasets and merge them using the image file path as a key. This forms a unified dataset that combines model predictions and demographic labels.

### 4. Preprocess and Format Data
Standardize categorical columns by applying a defined order for `gender`, `race`, and `age`. This helps ensure consistency in summaries and plots.

### 5. Define Thresholds and Label Outcomes
Create new DataFrames for each confidence threshold (e.g., 95%, 90%, and 80%). Apply a binary label (`score`) based on whether the model's confidence meets or exceeds the threshold. Since all images contain a face, set `label_value = 1` throughout.

### 6. Summarize Detection Patterns
Run exploratory analysis to examine detection performance across demographic groups. This includes mean detection rates and undetected face counts by group.

### 7. Evaluate Fairness with Aequitas
Use [Aequitas](https://github.com/dssg/aequitas) to generate:

- Crosstabs for metrics like `FNR` (false negative rate)
- Bias disparity metrics like `FNR disparity`, `FOR disparity`, and `TPR disparity`

Reference groups used in the analysis are:
- Gender: **Male**
- Race: **White**
- Age: **20–29**

### 8. Compute AUC Scores
Generate bar plots showing AUC (Area Under the Curve), FNR, and FPR for each group. AUC measures how well the model separates confident detections from uncertain ones across demographics.

### 9. Export Results
Formatted tables and AUC plots are exported:
- Crosstabs and bias tables as `.html`
- AUC visualizations as `.png`

