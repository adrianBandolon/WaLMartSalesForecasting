# WalMart Sales Forecasting

# Project Description:

For this project we were provided with historical sales data for 45 Walmart stores located in different regions. Each store contains many departments. The goal is to predict the future weekly sales for each department in each store based on the historical data.

**Data Source:** Only `train.csv` from **[Kaggle](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting)** was used for this project.

**Preprocessing:** 
-*Singular value decomposition* was performed on the training data using the `preprocess.svd` function that was used in the **[Walmart_Sample_Code.html](https://piazza.com/class_profile/get_resource/jky28ddlhmu2r8/jl33k19o30k5gi)**.

- The `forecast` library was used to build the models. The models used were the Naive (`naive`), Seasonal Naive (`snaive`) and the Time Series Linear Regression (`tslm`). To keep the process simple, SVD was used on the training data used in all the models.

- Aside from the model building functions and `preprocess.svd` function, the code from`mymain.R` comes from the code Josh Loyal provided (**[Example_Code_Project2_Josh.html](https://piazza.com/class_profile/get_resource/jky28ddlhmu2r8/jnqq1kbkbx6yy)**). 

- Below is the WMAE summary table for the three models:

