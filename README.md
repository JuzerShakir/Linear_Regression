# Linear Regression

## Table of Contents
- [Description](#description)
- [Notations](#notations)
- [Definition](#definition)
- [Flowchart](#flowchart)
- [Univariate Linear Regression](#univariate-linear-regression)
    - [Definition](#definition-for-univariate-linear-regression)
    - [Formula](#formula-for-univariate-linear-regression)
    - [Cost Function](#cost-function-for-univariate-linear-regression)
    - [Gradient Descent](#gradient-descent-for-univariate-linear-regression)
- [Multivariate Linear Regression](#multivariate-linear-regression)
    - [Definition](#definition-for-multivariate-linear-regression)
    - [Formula](#formula-for-multivariate-linear-regression)
    - [Cost Function](#cost-function-for-multivariate-linear-regression)
    - [Gradeint Descent](#gradeint-descent-for-multivariate-linear-regression)
- [Feature Scaling and Mean Normalization](#feature-scaling-and-mean-normalization)


## Description
A Mathematical intuition and quick guide and understanding of how Linear Regression Algorithms works. Given links to other study materials in order to understand the concepts more concretly.

## Notations
- `m` 👉 Number of Training Examples.
- `x` 👉 "input" variable / features.
- `y` 👉 "ouput" variable / "target" variable.
- `n` 👉 Number of feature variable `(x)`
- `(x, y)` 👉 One training example.
- `x`<sub>i</sub> , `y`<sub>i</sub>  👉 i<sup>th</sup> training example.
- `x`<sub>i<sub>j</sub></sub> 👉 i<sup>th</sup> training example of the j<sup>th</sup> column / feature.

-----

## Definition
A linear equation that models a function such that if we give any `x` to it, it will predict a value `y` , where both `x and y` are input and output varaibles respectively. These are numerical and continous values.

It is the most simple and well known algorithm used in machine learning.

## Flowchart 

<p align = 'center'><img src = 'Formulas/Linear_Reg_Flowchart.png' width = '612', height = '425'></p>

<br>

The above Flowchart represents that we choose our training set, feed it to an algorithm, it will learn the patterns and will output a function called `Hypothesis function 'H(x)'`. We then give any `x` value to that function and it will output an estimated `y` value for it.

For historical reasons, this function `H(x)` is called `hypothesis function.`

-----

## Univariate Linear Regression
### Definition for Univariate Linear Regression
When you have one feature / variable `x` as an input to the function to predict `y`, we call this `Univariate Linear Regression` problem.

### Formula for Univariate Linear Regression

<p align='center'>H(x) = θ<sub>0</sub> + θ<sub>1</sub>x</p>

Other way of representing this formula as what we are familiar with:

<p align='center'>H(x) = b + mx</p>

> Where :
>- b = θ<sub>0</sub> 👉 y intercept
>- m = θ<sub>1</sub> 👉 slope
>- x = x 👉 feature / input variable

<p align = 'center'><img src = 'Formulas/Linear_model_representation.jpg'></p>
<p align = 'center'><a href = 'https://archive.cnx.org/contents/20986bfa-2c2a-47f1-a48a-786122b0c606@3/graphical-analysis-of-one-dimensional-motion'>Source</a></p>

<br>

> **Help** ✍🏼 
> - <a href = 'https://www.khanacademy.org/math/algebra/two-var-linear-equations/slope-intercept-form/v/slope-intercept-form'>Intuition behind linear equation.</a>
> - <a href = 'https://www.khanacademy.org/math/algebra/two-var-linear-equations/slope-intercept-form/e/slope-from-an-equation-in-slope-intercept-form'>Need to Practice?</a>


### Cost Function for Univariate Linear Regression
All that said, how do we figure out the best possible straight line to the data that we feed?

**This is where `Cost Function` will help us:**

The best fit line to our data will be where we have least distance between the `predicted 'y' value` and `trained 'y' value`.

#### Formula for Cost Function
<p align = 'center'><img src = 'Formulas/MSE.png'></p>

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
<p align = 'center'><img src = 'Formulas/MSE1.png'></p>

<br>
<br>

> **Help** ✍🏼 
> - <a href='https://youtu.be/0kns1gXLYg4'>Intuition behind Cost Function.</a>


### Gradient Descent for Univariate Linear Regression
So now we have our hypothesis function and we have a way of measuring how well it fits into the data. Now we need to estimate the parameters in the hypothesis function. That's where `Gradient Descent` comes in.<br>
`Gradient Descent` is used to minimize the cost function `J`, minimizing `J` is same as minimizing `MSE` to get best possible fit line to our data.

#### Formula for Gradient Descent
<p align = 'center'><img src = 'Formulas/Gradient_Descent.PNG'></p>

> Where :
>- `:=` 👉 Is the Assignment Operator
>- `α` 👉 is `Alpha`, it's the number which is called learning rate. If its too high it may fail to converge and if too low then descending will be slow.
>- 'θ<sub>j</sub>' 👉 Taking Gradient Descent of a feature or a column of a dataset.
> - ∂/(∂θ<sub>j</sub>) J(θ<sub>0</sub>,θ<sub>1</sub>) 👉 Taking partial derivative of `MSE` cost function.

<br>
<br>

> **Additional Resources** ✍🏼 
> - <a href='https://youtu.be/YovTqTY-PYY'>Intuition behind Gradient Descent.</a>
> - <a href='https://www.khanacademy.org/math/multivariable-calculus/multivariable-derivatives/partial-derivatives/v/partial-derivatives-introduction'>Partial Derivative.</a>

<br>
<br>

**Now Let's apply Gradient Descend to minmize our `MSE` function.**
<br>
In order to apply `Gradient Descent`, we need to figure out the partial derivative term.<br>
So let's solve partial derivative of cost function `J`.

<br>

<p align = 'center'><img src = 'Formulas/Solving_Partial_Derivative.PNG'></p>

<br>

Now let's plug these 2 values to our `Gradient Descent`:

<br>

<p align = 'center'><img src = 'Formulas/Final_Gradient_Descent.PNG'></p>

<br>

> **Note :** 🚩<br>
> - Cost Function for Linear Regression is always going to be Convex or Bowl Shaped Function, so this function doesn't have any local minimum but one global minimum, thus always converging to global minimum.
> - The above hypothesis function has 2 parameters, θ<sub>0</sub> & θ<sub>1</sub>, so Gradient Descent will run on each feature, hence here two times, one for feature and one for base `(y-intercept)`, to get minimum value of `j`. So if we have `n` features, Gradient Descent will run on all `n+1` features.

-----

## Multivariate Linear Regression

> **Linear Algebra** ✍🏼 
> - <a href='https://www.khanacademy.org/math/precalculus/vectors-precalc/modal/v/introduction-to-vectors-and-scalars'>Intro to Vectors & Scalars.</a>
> - <a href=  'https://www.khanacademy.org/math/precalculus/vectors-precalc/modal/a/vector-operations-review'>Combined Vector Operations.</a>
> - <a href=  'https://www.khanacademy.org/math/precalculus/precalc-matrices/modal/v/introduction-to-the-matrix'>Intro to Matrices.</a>
> - <a href=  'https://www.khanacademy.org/math/precalculus/precalc-matrices/modal/a/representing-systems-with-matrices'>Representing linear systems with matrices.</a>
> - <a href=  'https://www.khanacademy.org/math/precalculus/precalc-matrices/modal/v/matrix-addition-and-subtraction-1'>Add & subtract matrices.</a>
> - <a href=  'https://www.khanacademy.org/math/precalculus/precalc-matrices/modal/v/matrix-multiplication-intro'>Multipling matrices.</a>
> - <a href=  'https://www.khanacademy.org/math/precalculus/precalc-matrices/modal/v/identity-matrix'>Identity Matrix.</a>
> - <a href=  'https://www.khanacademy.org/math/precalculus/precalc-matrices/modal/a/properties-of-matrix-multiplication'>Properties of Matrix Multiplication.</a>
> - <a href=  'https://www.khanacademy.org/math/precalculus/precalc-matrices/modal/v/inverse-matrix-part-1'>Matrix Inverses.</a>
> - <a href=  'https://www.khanacademy.org/math/linear-algebra/matrix-transformations/matrix-transpose/v/linear-algebra-transpose-of-a-matrix'>Matrix Transpose.</a>


### Definition for Multivariate Linear Regression
Its same as `Univariate Linear Regression`, except it has more than one feature variable `(x)` to predict target variable `(y)`.

### Formula for Multivariate Linear Regression
Our hypothesis function for `n` = 4 :
<p align = 'center'><img src = 'Formulas/Multi_Hypo_Func.PNG'></p>

<br>

> Where :
>- θ<sub>0</sub> 👉 y intercept
> - And rest are features `x` to help predict `y` value.
>> **Intuition:**<br>
>>In order to develop an intuition about this function, let's imagine that this function represents price of a house `(y)` based on the features given `(x)`, then we can think of this function as:
>> - θ<sub>0</sub> as the basic price of a house.
>> - θ<sub>1</sub> as price/m<sup>2</sup>.
>> - x<sub>1</sub> as area of a house (m<sup>2</sup>).
>> - θ<sub>2</sub> as price/floor.
>> - x<sub>2</sub> as number of floors.
>> - etc _(You get the idea)_

<br>
<br>

Let's set all the parameters:
<p align='center'><b> θ<sub>0</sub>, θ<sub>1</sub>, θ<sub>2</sub>, θ<sub>3</sub>.......θ<sub>n</sub> = θ </b></p>
<br>
And Let's set all the features:
<p align='center'><b> x<sub>0</sub>, x<sub>1</sub>, x<sub>2</sub>, x<sub>3</sub>.......x<sub>n</sub> = x </b></p>
<br>

> Where :
>- θ 👉 will be `n+1` dimensional vector because we have θ<sub>0</sub> which is not a feature.
> - x<sub>0</sub> 👉 is added just for convenience so that we can take matrix multiplication of `θ` as θ<sup>T</sup> and `x` and we will set x<sub>0</sub> value to 1, so this doesn't change the values.
> - x 👉 will also be `n+1` dimensional vector.

<br>
<br>

### Cost Function for Multivariate Linear Regression

So, 
<p align='center'>J(θ<sub>0</sub>, θ<sub>1</sub>, θ<sub>2</sub>, θ<sub>3</sub>.......θ<sub>n</sub>) = J(θ)</p>
<br>
Where,
<p align = 'center'><img src = 'Formulas/Multi_Linear_Cost_Func.PNG'></p>

<br>
<br>

### Gradeint Descent for Multivariate Linear Regression

<p align = 'center'><img src = 'Formulas/Multi_Linear_Gradient_Descent.PNG'></p>

<br>
<br>

**Appling Gradient Descend to minmize our `MSE` function after solving partial derivative of J(θ), we get :**
<br>
<p align = 'center'><img src = 'Formulas/Final_Gradient_Descent_Multi_Linear.PNG'></p>

<br>
<br>

**For Example : If we had 2 features, this is how gradient descent would run on each parameter:**

<br>

<p align = 'center'><img src = 'Formulas/Param_Final_Gradient_Descent_Multi_Linear.PNG'></p>

<br>

------

### Feature Scaling and Mean Normalization

We can speed up `Gradient Descent` by having each of our input values in roughly the same range. This is because `0` will descend quickly on small ranges and slowly on large ranges. If we have large ranges, it will oscilate inefficiently down to optimum (minimum) when the variables are very uneven.

<br>

The way to prevent this is to modify the ranges of our input variables so that they are all roughly the same. Ideally between :
<p align = 'center'>-1  ≤  x<sub>i</sub>  ≤  1</p>
<p align = 'center'>OR</p>
<p align = 'center'>-0.5  ≤  x<sub>i</sub>  ≤  0.5</p>

<br>

These aren't exact requirements, we are only trying to speed things up. The goal is to get all input variables into roughly one of these ranges.<br>
This can make `Gradient Descent` run much faster and converge in a lot few iterations.

<br>

<br>Two techniques to help with this are `Feature Scaling` and `Mean Normalization`.</b>

- `Feature Scaling` involves diving the input values by the range (i.e max value - min value) of the input variable, resulting in a new values.
<p align = 'center'><img src = 'Formulas/Feature_Scaling.PNG'></p>

- `Mean Normalization` involves subtracting the average of a feature variable from the values of the feature, dividing by _range_ of values or by _standard deviation_, resulting in a new values.
<p align = 'center'><img src = 'Formulas/Mean_Normalization.PNG'></p>

> Where:
> - μ<sub>j</sub> 👉 Average of a Feature variable `j`.
> - s<sub>i</sub> 👉 Either `Range` or `Standard Deviation` of a Feature `j`.
