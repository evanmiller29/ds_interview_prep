---
type: slides
---

# Linear Regression

Notes: Text at the end of a slide prefixed like this will be displayed as
speaker notes on the side. Slides can be separated with a divider: ---.

---

# Basics

- Fits an equation that satisfies y = mx + c using OLS

---

# Assumptions required for LR

[See here for more detail](https://towardsdatascience.com/assumptions-of-linear-regression-5d87c347140)

1. Linear relationship between the y and the Xs
2. Error distribution of the residuals are normally distributed and independent from one another
3. Minimal multicollinearity between predictors
4. Homoscedascity the variance around the regression line for all values of the prediction variable

Notes: Some more notes go here

---

# Logistic regression - binary case

[See here for more detail](https://towardsdatascience.com/logistic-regression-explained-9ee73cede081)

Classifies data into either 0/1 or multi class.

To do this we need to define a threshold and if the predicted value exceeds threshold then we call it that class.

1. Inputs are converted to log odds
2. Which are then passed through the sigmoid function to push values to either 0 or 1

A logistic regression produces a logistic curve which limits values between 0 and 1.
the sigmoid function always takes the max and minimum (1/0) and fits a curve to it.

By computing the sigmoid function of X (that is the weighted sum of the input features), we get a probability between 0 and 1.

Sigmoid formula = siggmoid(x) =  1/1+e^-x

Logistic regression is similar to a linear regression, but the curve is constructed using the natural logarithm of the "odds" of the target variable rather than the probability. 
Moreover, the predictors do not have to be normally distributed or have equal variance in each group.

---

# Logistic regression - multiclass case

[See here for more detail](https://www.experfy.com/blog/the-logistic-regression-algorithm/)

Out of the box it only does binary prediction, but with a small amount of work you can get it to predict multiclass. This can be done by:

## One-versus-all (OvA)

Train 10 binary classifiers, one for each class. When predicting the class find the model with the highest score

## One-versus-one (OvO)

You build classifiers for each combination of classes. So if you had a 10 label classification model you would build models for (0, 1), (0, 2) etc.
If you have N classes then you would need to train NxN(N-1)/2 classifiers. 

This might sound like a bad idea, but since you are only considering 2 classes at a time you can reduce the dataset massively when working with big datasets.
Sklearn generally uses OvA for most algorithms, but does OvO for SVMs

---
