# Exploring Gender Prediction with Name Data

## Project Overview
This project aims to predict gender based on first names using machine learning models. The dataset includes names, gender labels, and associated statistics across several English-speaking countries. This analysis explores how name data can reveal trends in societal naming conventions and be used effectively for gender prediction.

## Dataset Information
- **Source**: Aggregated baby name data from government databases in the US, UK, Canada, and Australia.
- **Attributes**:
  - `Name`: First name (string)
  - `Gender`: Category M/F
  - `Count`: Frequency count of the name occurrence
  - `Probability`: Probability (not used for this analysis)

## Data Preprocessing
- Removed unnecessary columns (`Probability`, `length`) to simplify data.
- Converted gender to numerical form (0 = female, 1 = male) for compatibility with modeling.
- Filtered data by name length (2 to 15 characters) and removed special characters.
- Converted names to ASCII values and standardized by padding to uniform length.
- Split data for training (X) and target variables (Y).

## Models and Results

### Neural Networks
- **Custom NN**: Used a dense-layer network for initial prediction with 75.87% accuracy.
- **Keras NN**: Achieved a test accuracy of 79.6% using a dense layer and ReLU activation, trained with the Adam optimizer and sparse categorical cross-entropy loss.

### Logistic Regression
1. **First Approach**:
   - Basic logistic regression achieved 63% accuracy.
2. **Improved Approach**:
   - Added categorical features based on the last 1-3 letters of names.
   - Improved accuracy to **86%**.

### LightGBM
1. **First Approach**:
   - Basic LightGBM with GridSearchCV parameter tuning achieved **88% accuracy**.
2. **Second Approach**:
   - Categorical features based on the last 1-3 letters were included, achieving **85% accuracy**.

## Key Findings
- Custom neural networks and Keras-based models showed competitive accuracy for name-based gender prediction.
- Logistic Regression and LightGBM models revealed that using name suffix features significantly improved predictive performance.
- LightGBM achieved the highest accuracy at 88%, showing strong potential for practical application in gender prediction models.

## Conclusion
This project highlights the effectiveness of machine learning in gender prediction based on name data, with LightGBM and logistic regression methods offering robust results. Further refinement with more nuanced features (e.g., linguistic analysis of names) could enhance model accuracy.
