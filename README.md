# E-Commerce Data

You can find the data and some explanation from the following Kaggle link:
[E-Commerce Data](https://www.kaggle.com/datasets/carrie1/ecommerce-data)

### Order Cancellation Prediction

To think in terms of business problems, I thought it would be beneficial to the business to predict order cancellation by allowing the periodic calculations to take cancellation into account. Rather than classes, probabilities should be more important here to have a some sort of *expected subtraction* for each period (e.g., monthly). Hence, one should check the calibration of the model.

In the "order-cancellation-preds.ipynb", I start off by invoice-level predictions to set the baseline. After that, I add customer-level variables to show how much of an improvement there can be, which is quite considerable. I make use of expanding-window CV, proper for cross-validation, and StackedClassifier (includes 5 models) to make final  predictions on the unseen data. If one wants to take this any further, it's possible to:
- On top of target encoding, it's possible to count encode the countries as well.
- Creating interactions between binned variables with target encoding may boost the signal, specially early in a tree. It's very common practice, but takes away from interpretability.
- It's possible to add more variables. Those customer-level time-aware features can be richened by adding which stock groups were included in the last order, or last 30 days etc. In addition to last 30 days, there can be last 7 days, last 15 days features as well.
- Regularization of final estimator or different final_estimator can be used.
- I wrapped things into functions in general but there are still some parts that could have been functionalized.
- Decorators can be used to log the changes in the dataframes (I ran with recurring print statements).