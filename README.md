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

<p align = 'center'><img src = 'Linear_Reg_Flowchart.png' width = '612', height = '425'></p>

<br>

The above Flowchart represents that we choose our training set, feed it to an algorithm, it will learn the patterns and will output a function called `Hypothesis function 'H(x)'`. We then give any `x` value to that function and it will output an estimated `y` value for it.

For historical reasons, this function `H(x)` is called `hypothesis function.`


### Univariate Linear Regression
#### Definition
When you have one feature / variable `x` as an input to the function to predict `y`, we call this `Univariate Linear Regression` problem.
