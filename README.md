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
| 𝐗 | training example maxtrix | X_train |
| 𝐲 |	training example targets	| y_train |
| 𝐱<sup>(𝑖)</sup>, 𝑦<sup>(𝑖)</sup> | 𝑖𝑡ℎ Training Example |	X[i], y[i] |
| m	| number of training examples	| m |
| n	| number of features in each example | n |
| 𝐰 | parameter: weight, |	w |
| 𝑏 | parameter: bias	| b |
| 𝑓𝐰,𝑏(𝐱<sup>(𝑖)</sup>) | The result of the model evaluation at  𝐱<sup>(𝑖)</sup> parameterized by  𝐰,𝑏 :  𝑓𝐰,𝑏(𝐱<sup>(𝑖)</sup>)=𝐰⋅𝐱<sup>(𝑖)</sup>+𝑏 | f_wb |
| ∂𝐽(𝐰,𝑏)/∂𝑤𝑗 |	the gradient or partial derivative of cost with respect to a parameter  𝑤𝑗 | dj_dw[j] |
| ∂𝐽(𝐰,𝑏)/∂𝑏 | the gradient or partial derivative of cost with respect to a parameter  𝑏 | 	dj_db |
