# BiasOMZ
Project materials for DS 6015: DS Capstone as part of UVA School of Data Science Master's in Data Science. The goal of this project is to review the literature for ways to evaluate bias, then implement an evaluation on a model from Intel's [Open Model Zoo](https://github.com/openvinotoolkit/open_model_zoo/tree/master) for potential bias against protected characteristic(s). 

# How to use this repo

## Clean preds
-	The Clean_preds file contains the overall methodology for specifying a model, ingesting data, and transforming data.
-	The first part of the notebook allows the user to choose a model and have it automatically downloaded to the file directory (using the model_name variable)
-	The second part of the juptyer notebook transforms the selected image dataset and transforms it to fit specifically in the face-detection-0200 model
-	Note that this notebook is designed to work with both this dataset and the fairface dataset, while it does provide a framework to use open vino, changes may be needed in case the user wants to use either a different dataset or a different model
