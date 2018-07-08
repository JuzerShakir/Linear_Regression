# Machine Learning Algorithms

## Table of Contents

- [Description](#description)
- [Notations](#notations)
- [Linear Regression](#linear-regression)

## Description
A quick guide and understanding of how famous Machine Learning Algorithms work. Also given links to other study materials in order to understand the concepts more concretly.

## Notations
- `m` 👉 Number of Training Examples.
- `x` 👉 "input" variable / features.
- `y` 👉 "ouput" variable / "target" variable.
- `(x, y)` 👉 One training example.
- `x`<sub>i</sub> , `y`<sub>i</sub>  👉 i<sup>th</sup> training example.
- `x`<sub>i<sub>j</sub></sub> 👉 i<sup>th</sup> training example of the j<sup>th</sup> column / feature.

-----

## Linear Regression
### Definition
A linear equation that models a function such that if we give any `x` to it, it will predict a value `y` , where both `x and y` are input and output varaibles respectively. These are numerical and continous values.

It is the most simple and well known algorithm used in machine learning.

### Flowchart 

<p align = 'center'><img src = 'Images/Linear_Reg_Flowchart.png' width = '612', height = '425'></p>

<br>

The above Flowchart represents that we choose our training set, feed it to an algorithm, it will learn the patterns and will output a function called `Hypothesis function 'H(x)'`. We then give any `x` value to that function and it will output an estimated `y` value for it.

For historical reasons, this function `H(x)` is called `hypothesis function.`


### Univariate Linear Regression
#### Definition
When you have one feature / variable `x` as an input to the function to predict `y`, we call this `Univariate Linear Regression` problem.

#### Formula

<p align='center'>H(x) = θ<sub>0</sub> + θ<sub>1</sub>x</p>

Other way of representing this formula as what we are familiar with:

<p align='center'>H(x) = b + mx</p>

> Where :
>- b = θ<sub>0</sub> 👉 y intercept
>- m = θ<sub>1</sub> 👉 slope
>- x = x 👉 feature / input variable

<p align = 'center'><img src = 'Images/Linear_model_representation.jpg'></p>
<p align = 'center'><a href = 'https://archive.cnx.org/contents/20986bfa-2c2a-47f1-a48a-786122b0c606@3/graphical-analysis-of-one-dimensional-motion'>Source</a></p>

<br>

> **Help** 🚩
> - <a href = 'https://www.khanacademy.org/math/algebra/two-var-linear-equations/slope-intercept-form/v/slope-intercept-form'>Intuition behind linear equation.</a>
> - <a href = 'https://www.khanacademy.org/math/algebra/two-var-linear-equations/slope-intercept-form/e/slope-from-an-equation-in-slope-intercept-form'>Need to Practice?</a>

-----

#### Cost Function
All that said, how do we figure out the best possible straight line to the data that we feed?

**This is where `Cost Function` will help us:**

The best fit line to our data will be where we have least distance between the `predicted 'y' value` and `trained 'y' value`.

##### Formula :
<p align = 'center'><img src = 'Images/MSE.png'></p>

> Where :
>- h(x<sub>i</sub>) 👉 hypothesis function
>- y<sub>i</sub> 👉 actual values of `y`
>- 1/m 👉 gives Mean of Squared Errors
>- 1/2 👉 Mean is halved as a convenience for the computation of the `Gradient Descent`.


The above formula takes the sum of the distances between <i>`predicted values` and `actual values` of training set, sqaure it, take the average and multiply it by `1/2`.</i>
<br>
<br>
This cost function is also called as `Squared Error Function` or `Mean Squared Error`.
<br>
<br>
🙋‍ Why do we take squares of the error's?<br>
The `MSE` function is commonly used and is a reasonable choice and works well for most Regression problems.
<br>
<br>
Let's subsititute `MSE` function to function `J` :
<p align = 'center'><img src = 'Images/MSE1.png'></p>

<br>
<br>

> **Help** 🚩
> - <a href='https://youtu.be/0kns1gXLYg4'>Intuition behind Cost Function.</a>

-----

#### Gradient Descent
So now we have our hypothesis function and we have a way of measuring how well it fits into the data. Now we need to estimate the parameters in the hypothesis function. That's where `Gradient Descent` comes in.<br>
`Gradient Descent` is used to minimize the cost function `J`, minimizing `J` is same as minimizing `MSE` to get best possible fit line to our data.

##### Formula :
<p align = 'center'><img src = 'Images/Gradient_Descent.PNG'></p>

> Where :
>- `:=` 👉 Is the Assignment Operator
>- `α` 👉 is `Alpha`, it's the number which is called learning rate. If its too high it may fail to converge and if too low then descending will be slow.
>- 'θ<sub>j</sub>' 👉 Taking Gradient Descent of a feature or a column of a dataset.
> - ∂/(∂θ<sub>j</sub>) J(θ<sub>0</sub>,θ<sub>1</sub>) 👉 Taking partial derivative of `MSE` cost function.

<br>
<br>

> **Additional Resources** 🚩
> - <a href='https://youtu.be/YovTqTY-PYY'>Intuition behind Gradient Descent.</a>
> - <a href='https://www.khanacademy.org/math/multivariable-calculus/multivariable-derivatives/partial-derivatives/v/partial-derivatives-introduction'>Partial Derivative.</a>

<br>
<br>

**Now Let's apply Gradient Descend to minmize our `MSE` function.**
<br>
In order to apply `Gradient Descent`, we need to figure out the partial derivative term.<br>
So let's solve partial derivative of cost function `J`.

<br>

<p align = 'center'><img src = 'Images/Solving_Partial_Derivative.PNG'></p>

<br>

Now let's plug these 2 values to our `Gradient Descent`:

<br>

<p align = 'center'><img src = 'Images/Final_Gradient_Descent.PNG'></p>

<br>

> **Note :** 🚩<br>
> - Cost Function for Linear Regression is always going to be Convex or Bowl Shaped Function, so this function doesn't have any local minimum but one global minimum, thus always converging to global minimum.
> - The above hypothesis function has 2 parameters, θ<sub>0</sub> & θ<sub>1</sub>, so Gradient Descent will run on each feature, hence here two times for two features to get minimum value of `j`. So if we have `n` features, Gradient Descent will run on all `n` features.