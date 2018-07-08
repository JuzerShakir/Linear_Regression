# Machine Learning Algorithms

## Table of Contents

- [Description](#description)
- [Notations](#notations)
- [Linear Regression](#linear_regression)

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

#### Cost Function
All that said, how do we figure out the best possible straight line to the data that we feed?

**This is where `Cost Function` will help us:**

The best fit line to our data will be where we have least distance between the `predicted 'y' value` and `trained 'y' value`.

##### Formula :
<p align = 'center'><img src = 'Images/MSE.PNG'></p>

> Where :
>- h(x<sub>i</sub>) 👉 hypothesis function
>- y<sub>i</sub> 👉 actual values of `y`
>- 1/m 👉 gives Mean of Squared Errors
>- 1/2 👉 Mean is halved as a convenience for the computation of the `Gradient Descent`.


The above formula represnts this:<br>
Find me the best fit line to the data so that the `squared errors` between `predicted values` and `actual values` of training set times `1/2m` is minimized.
<br>
<br>
This cost function is also called as `Squared Error Function` or `Mean Squared Error`.
<br>
<br>
🙋‍ Why do we take squares of the error's?<br>
The `MSE` function is commonly used and is a rasonable choice and works well for most Regression problems.
<br>
<br>
Let's subsititute `MSE` function to function `J` :
<p align = 'center'><img src = 'Images/MSE1.PNG'></p>