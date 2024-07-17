Describe the process you would use to analyze and curate it for use in training a computer vision model to predict sex of a butterfly. For the purposes of this task, assume it is sufficiently large to do so, but please document any concerns or assumptions.
# Setup
Create a reproducible working environment using venv or conda. Keep track of the package dependencies and update the requirement list as need
# Assumptions
1. This dataset contains only the training split. This analysis assumes that the training set is sufficiently large and will use the provided training split to create separate sets for training, testing, and validation for model training.
2. This analysis will focus solely on using the image data for model training. Other supporting categorical features in the metadata will not be taken into consideration.
3. This is analysis assumes all species and subspecies are well represented and the subspecies are well-balanced around the sex attribute. 
4. This analysis will focus on data curation exclusively and will cover less details regarding hyperparameter tuning, model selection, model improvements, etc.
# Data Prep

## Loading
Make sure that data can be loaded successfully from Hugging Face. Consider making the data locally available into a `ImageFolder`
## Cleaning
1. Check for missing values in key training features such as `Image` and `Sex`.
2. Check for duplications to avoid bias and ensure that each observation is uniquely identified.
3. Clean mislabeled attribute values and ensure that each attribute contains only the allowed values specified in the metadata or schema. For example, in the `Sex` feature, convert "Female" values to "female."
4. Encode the target variable `Sex` into numerical values and encode other categorical features as needed.
5. Wrap these cleaning operations into a function to ensure reproducibility.
## Create Splits
Apply the data cleaning functions to the original dataset, split dataset into training, testing, and validating sets. 
## Feature Engineering
1. Class Balance: To prevent bias, it is important to have a balanced training set. We will explore different resampling strategies and evaluate their effectiveness using cross-validation.
2. Standardization: Ensure that the RGB channel values are standardized to be within the range of `[0, 1]`.
3. Data Augmentation: To prevent overfitting and to build a robust model, we will implement data augmentation techniques such as flipping, rotation, and zooming (Depending on the library you are using, it may be possible to include this step within your neural network model just like additional layers)
4. Wrap these steps into a function to ensure reproducibility.

# Model Training & Evaluation

Perform stratified cross-validation to find the best model that generalize. 
Evaluate the model prediction result on validation split. 
