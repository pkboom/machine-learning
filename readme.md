# Regression

## Linear Regression

## Gradient Descent

# Optimization

## Least Square Method

# Bias & Variance

## Leave-One-Out Cross-Validation(LOOCV)

<image src='LOOCV.webp'>

## K-fold cross validation

Divide data by k.

e.g. 4-fold cross validation

## Regularization

A process that changes the result answer to be "simpler".

This is a form of regression, that constrains/regularizes or shrinks the coefficient estimates towards zero. In other words, this technique discourages learning a more complex or flexible model, so as to avoid the risk of overfitting.

### Ridge Regression

### Lasso Regression

# Classification

## Logistic Regression

Sigmoid function

## Softmax Regress

Multi-class classification

## Support Vector Machine(SVM)

Hyperplane

### Maximal Margin Classifier

<image src='maximal_margin_classifier.png'>

### Soft Margin Machine

<image src='soft_margin_machine.webp'>

## Decision Tree

예측을 위해 여러 region으로 stratifying or segmenting 하는 방법론

회귀와 분류 모두에서 사용 가능함

Pros:

- 모델에 대한 해석과 설명이 쉬움
- 인간의 의사 결정과 매우 비슷한 형태의 모델임
- 시각적으로 보여주기 편리하며, 비전문가도 쉽게 이해 가능

Cons:

- 다른 회귀, 분류 모델에 비해 예측 성능이 일반적으로 떨어짐
- 하지만 이는 많은 수의 결정 트리의 결과를 종합하는 Ensemble 학습(e.g., Bagging,
  Boosting)으로 보완 가능함

## Linear Discriminant Analysis
