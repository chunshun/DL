# A related task is dimensionality reduction, in which the goal is to simplify the data without losing too much information.
1. feature extraction
2. 

One important parameter of online learning systems is how fast theyshould adapt to changing data: this is called the learning rate


#instance-based learning vs  model-based learning:
instance-based learning: the system learns the examples by heart, then
generalizes to new cases using a similarity measure(生成模型？)

Another way to generalize from a set of examples is to build a model of these examples,
then use that model to make predictions. This is called model-based learning(训练模型？)


数据与方法：

## **Regularization reduces the risk of overfitting**

Constraining a model to make it simpler and reduce the risk of overfitting is called
**_regularization_.**

The amount of regularization to apply during learning can be controlled by a _**hyperparameter**_.
A hyperparameter is a parameter of a learning algorithm (not of the
model).it must be set prior to training and remains constant during training.Tuning hyperparameters is an important part of building a Machine Learning system

**overfitting:**    
* To simplify the model by selecting one with fewer parameters
(e.g.a linear model rather than a high-degree polynomial model), by reducing the number of attributes in the training data or by constraining the model
* To gather more training data
* To reduce the noise in the training data (e.g., fix data errors
and remove outliers)

**underfitting:**   
*  Selecting a more powerful model, with more parameters
* Feeding better features to the learning algorithm (feature engineering)
*  Reducing the constraints on the model (e.g., reducing the regularization hyperparameter)

tricks:
* It is common to use 80% of the data for training and hold out 20% for testing.

## **cross-validation:**  
 the training set is split into complementary subsets, and each model is trained against a different combination of these subsets and validated against the remaining parts. Once the model type and hyperparameters have been selected, a final model is trained using these hyperparameters on the full training set,and the generalized error is measured on the test set.
           


## pipeline:
A sequence of data processing components is called a data pipeline.
    
## RMSE(L2) vs MSE(L1)    
_The higher the norm index, the more it focuses on large values and neglects small  ones. This is why the RMSE is more sensitive to outliers than the MAE.But when outliers are exponentially rare (like in a bell-shaped curve), the RMSE performs
very well and is generally preferred._

##OneHotEncoder
Scikit-Learn provides a OneHotEncoder encoder to convert integer categorical values into one-hot vectors.

## Feature Scaling
One of the most important transformations you need to apply to your data is feature scaling
There are two common ways to get all attributes to have the same scale: min-max scaling and standardization.

* Min-max scaling (many people call this normalization) is quite simple: values are shifted and rescaled so that they end up ranging from 0 to 1. We do this by subtracting the min value and dividing by the max minus the min. Scikit-Learn provides a transformer called MinMaxScaler for this. It has a feature_range hyperparameter that lets you change the range if you don’t want 0–1 for some reason.

* Standardization is quite different: first it subtracts the mean value (so standardized values always have a zero mean), and then it divides by the variance so that the resulting distribution has unit variance

        As with all the transformations, it is important to fit the scalers to
        the training data only, not to the full dataset (including the test set).
        Only then can you use them to transform the training set and the
        test set (and new data).

**DecisionTreeRegressor**
This is a powerful model, capable of finding complex nonlinear relationships in the data