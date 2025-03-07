# Feature scaling and Learning Rate (Multi-variable Linear Regression)
### Goals
In this notebook you will:
- Utilize the multiple variables routines developed in our previous projects
- Run Gradient Descent on a data set with multiple features
- Explore the impact of the learning rate alpha on gradient descent
- Improve performance of gradient descent by feature scaling using z-score normalization
### Tools
We will utilize the functions developed in the last notebook as well as `matplotlib` and `NumPy`.
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
