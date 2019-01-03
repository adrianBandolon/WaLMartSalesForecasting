# WalMart Sales Forecasting

# Project Description:

For this project we were provided with historical sales data for 45 Walmart stores located in different regions. Each store contains many departments. The goal is to predict the future weekly sales for each department in each store based on the historical data.

We were asked to predict the weekly sales for each department in each store for the next two months, starting from 2011-03 to 2012-10 (20 months in total).

The evaluation procedure is formulated to be similar to backtesting in stock trading systems where you can only use information avaiable until that month---you cannot look into the future, when predicting the sales of a month.

**Files in this repository:**

- `trainTestSplitter.R`- this will split `train.csv` to 10 folds to be used for training and testing the models. This is courtesy of Josh Loyal. **[(Example_Code_Project2_Josh.html)](https://piazza.com/class_profile/get_resource/jky28ddlhmu2r8/jnqq1kbkbx6yy)**
- `evaluationCode.R`- this runs all the 10 folds of each model.
- `mymain.R`- contains the models being used and all preprocessing performed on the data.

**Data Source:** Only `train.csv` from **[Kaggle](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting)** was used for this project.

**Preprocessing:** 

- *Singular value decomposition* was performed on the training data using the `preprocess.svd` function that was used in the **[Walmart_Sample_Code.html](https://piazza.com/class_profile/get_resource/jky28ddlhmu2r8/jl33k19o30k5gi)**.

- The `forecast` library was used to build the models. The models used were the Naive (`naive`), Seasonal Naive (`snaive`) and the Time Series Linear Regression (`tslm`). To keep the process simple, SVD was used on the training data used in all the models.

- Aside from the model building functions and `preprocess.svd` function, the code from`mymain.R` comes from the code Josh Loyal provided (**[Example_Code_Project2_Josh.html](https://piazza.com/class_profile/get_resource/jky28ddlhmu2r8/jnqq1kbkbx6yy)**). 

**Models Used:**

- I first started out with the simplest model, the naive (`naive`) model from the `forecast` library. This model had an average 10 fold *Weighted Mean Absolute Error __(WMAE)__* of around __2777.38__.

- The second model used the seasonal naive (`snaive`) model. This had an average 10 fold WMAE of around 1833.43.

- The third model used was the time-series linear (`tslm`) model. Seasonal and long term trends were accounted for in this model. This had an average 10 fold WMAE of around 1614.61.

**Output:**

- `mymain.R` will output WMAE (*Weighted Mean Absolute Error*) for each fold--10 total folds, for each model. 
