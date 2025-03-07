# Feature scaling and Learning Rate (Multi-variable Linear Regression)
### Overview
This Jupyter [Notebook](https://github.com/tamunoWoks/feature_scaling_and_learning_rate_for_linear_regression_models/blob/main/feature_scaling_and_learning_rate.ipynb) explores the impact of feature scaling on machine learning models and how it affects the learning rate during training. Feature scaling is a crucial preprocessing step that ensures efficient convergence of optimization algorithms like gradient descent.
### Objectives
This notebook aims to:
- Explain the importance of feature scaling in machine learning.
- Compare different feature scaling techniques (Normalization vs. Standardization).
- Demonstrate the effect of unscaled vs. scaled features on gradient descent convergence.
- Visualize how learning rates interact with scaled/unscaled data.
- Provide practical insights into choosing an appropriate scaling method for ML models.
### Libraries Used:
- `numpy`
- `pandas`
- `matplotlib`
- `scikit-learn`
### Notation
General
|Notation	| Description	| Python (if applicable) |
|---------|-------------|------------------------|
| 𝑎 | scalar, non bold	| |
| 𝐚 |	vector, bold	| |
| 𝐀 |	matrix, bold capital	| |
| Regression	|	
| 𝐗 | training example maxtrix | `X_train` |
| 𝐲 |	training example targets	| `y_train` |
| 𝐱<sup>(𝑖)</sup>, 𝑦<sup>(𝑖)</sup> | 𝑖𝑡ℎ Training Example |	`X[i]`, `y[i]` |
| m	| number of training examples	| `m` |
| n	| number of features in each example | `n` |
| 𝐰 | parameter: weight, |	`w` |
| 𝑏 | parameter: bias	| `b` |
| 𝑓𝐰,𝑏(𝐱<sup>(𝑖)</sup>) | The result of the model evaluation at  𝐱<sup>(𝑖)</sup> parameterized by  𝐰,𝑏 :  𝑓𝐰,𝑏(𝐱<sup>(𝑖)</sup>)=𝐰⋅𝐱<sup>(𝑖)</sup>+𝑏 | `f_wb` |
| ∂𝐽(𝐰,𝑏)/∂𝑤𝑗 |	the gradient or partial derivative of cost with respect to a parameter  𝑤𝑗 | `dj_dw[j]` |
| ∂𝐽(𝐰,𝑏)/∂𝑏 | the gradient or partial derivative of cost with respect to a parameter  𝑏 | 	`dj_db` |
### Problem Statement
We will use the motivating example of housing price prediction. The training data set contains many examples with 4 features (size, bedrooms, floors and age) shown in the table below. Note, the Size feature is in sqft while earlier labs utilized 1000 sqft.  

We would like to build a linear regression model using these values so we can then predict the price for other houses - say, a house with 1200 sqft, 3 bedrooms, 1 floor, 40 years old.
### Dataset:
| Size (sqft) |	Number of Bedrooms	| Number of floors	| Age of Home	| Price (1000s dollars) |
|-------------|---------------------|-------------------|-------------|-----------------------|
| 952	| 2	| 1	| 65 | 271.5 |
| 1244	| 3	| 2	| 64	| 232 |
| 1947	| 3	| 2	| 17	| 509.8 |
| ...	| ...	| ...	| ...	| ... |
### Contents
- **Introduction to Feature Scaling**
  - Why is feature scaling important?
  - Common scaling methods: Min-Max Scaling, Standardization, and Robust Scaling.
- **Mathematical Background**
  - How scaling affects gradient descent updates.
  - Theoretical explanation of learning rate sensitivity.
- **Implementation in Python**
  - Loading a sample dataset.
  - Applying different scaling techniques using scikit-learn.
- **Impact on Gradient Descent**
  - Training a simple linear model with unscaled vs. scaled features.
  - Visualizing the loss function behavior over epochs.
- **Best Practices and Recommendations**
  - When to use normalization vs. standardization.
  - Handling categorical features alongside scaling.
  - Choosing an optimal learning rate for different datasets.
### Requirements
To run this notebook, ensure you have Python installed along with the required libraries:
```
pip install numpy pandas matplotlib scikit-learn jupyterlab
```
Then, launch Jupyter Notebook with:
```
jupyter notebook feature_scaling_and_learning_rate.ipynb
```
