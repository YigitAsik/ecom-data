# E-Commerce Order Cancellation Prediction

You can find the data from the following Kaggle link:

[E-Commerce Data](https://www.kaggle.com/datasets/carrie1/ecommerce-data)

### Order Cancellation Prediction

To think in terms of business problems, I thought it would be beneficial to the business to predict order cancellation by allowing the periodic calculations to take cancellation into account. Rather than classes, probabilities should be more important here to have a some sort of *expected subtraction* for each period (e.g., monthly).

In the "order-cancellation-preds.ipynb", I start off by invoice-level predictions with stacked classifier to set the baseline. If one wants to take this part any further, it's possible to:
- On top of target encoding, it's possible to count encode the countries as well.
- Creating interactions between binned variables with target encoding may boost the signal, specially early in a tree. It's very common practice, but takes away from interpretability.
- I wrapped things into functions in general but there are still some parts that could have been functionalized.
- Decorators can be used to log the changes in the dataframes (I ran with recurring print statements).

*TODO:*
- Add customer-level variables on top of invoice-level to see how much of a room there is to go.