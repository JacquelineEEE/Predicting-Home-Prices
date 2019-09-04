# Predicting Home Prices

This project allowed an opportunity to utilize a `linear regression model` to predict home prices.

### Process:

**1. Data Research:**

Reading through the [data dictionary](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt) and understanding what was available in the dataset.

Brief data summary:

| The What | Details|
|:---------| :-------------------|
| 2930 unique observations | each is an individual house in Ames, Iowa from 2006 - 2010 |
| 82 variables | 23 nominal, 23 ordinal, 14 discrete, 20 continuous variables |


**2. Cleaning and EDA:**

1. `Finding and replacing null values` in both the train and test datasets, and making decisions about what to do. Many of the null values existed because the property did not have the specific feature (ie: pool). In that case, nulls were replaced with zeros.

[Null Values](./images/null_values.png)

**3. Feature Engineering:**

1. `Numerizing` some of the ordinal variables.

[Ordinal Variables](./images/ordinal_mapped.png)

2. Creating `dummy variables`.

3. Creating `buckets` to categorize certain continuous variables.

4. Converting the y-value to `natural log of y` to get a more normal distribution and decrease variance of the y-values (and therefore decreasing the variance of the coefficients).


**4. Feature Selection:**

Any feature having a `correlation >= .30` was selected as a feature for the model. The model had a `total of 26 features`.

**5. Feature Visualizations:**

Used visualizations to compare the features to the original y-values and the natural log of y-values. This, in addition to the distribution being more normal, was a determining factor in my using the natural log of y for the model.

[Overall Quality](./images/overall_qual.png)

[Gr Living Area](./images/gr_living_area.png)


**6. Modeling, and Comparing Coefficients and Loss Functions:**

Attempted:
1. `Linear Regression`
2. `Lasso CV`
3. `Ridge CV`

All train and test accuracy scores very close:
1. LR train: `.878`; LR test: `.8878`
2. Lasso train: `.878`; Lasso test: `.8885`
3. Ridge train: `.878`; Ridge test: `.8878`

There was slightly less variance in the lasso coefficient range than the ridge range, so chose lasso.

**7. Model Visualizations:**

Comparing the predictions to actual values, and looking at the residuals.
[Lasso Visualizations](./images/lasso_viz.png)
