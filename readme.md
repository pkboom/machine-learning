# Regression

## Linear Regression

## Gradient Descent

# Optimization

## Least Square Method

# Bias & Variance

## Leave-One-Out Cross-Validation(LOOCV)

<image width='500' src='LOOCV.webp'>

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

<image width='500' src='maximal_margin_classifier.png'>

### Soft Margin Machine

<image width='500' src='soft_margin_machine.webp'>

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

# Ensemble Learning

<image width='500' src='bagging.png'>

<image width='500' src='boosting.png'>

여러 개의 모델을 학습시켜, 다양한 예측 결과들을 이용하는 방법론

## Bagging

### Bootstrap

### Out-of-Bag Error Estimation

### Random Forests

Bagged tree 사이의 상관관계를 없애 성능을 향상시킨 알고리즘

## Boosting

배깅과 마찬가지로, 다양한 알고리즘과 회귀와 분류 문제에 모두 적용 가능

결정 트리를 사용한 부스팅 알고리즘

1. AdaBoost
2. Gradient Boosting(GBM)
3. XGBoost
4. Light GBM
