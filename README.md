This project is 100% done by the author to learn linear regression model workflow from creation to evaluation and adjustments and prediction. 
This project revolves around a student performance datatset which can be obtained here : https://www.kaggle.com/datasets/haseebindata/student-performance-predictions

Kaggle link to see all processes in detail : https://www.kaggle.com/code/micro20/student-performance-cleaning-eda-ml-study/notebook

In this project, data cleaning is done which involve checking on duplicated records, handling features with null values and standardization of values in some of the features.

Then, linear regression and XGBoost model are used as base model for final grade prediction (numerical scor), in which later resulted in linear regression model selection due to result on RMSE,
MAE and MAPE. Subsequently, as the features provided weak signals for prediction and RMSE result showed near 9 (which is assumed bad for grade scoring),
outlier tratement, log target 'y' feature, median fill null values on 'FinalGrade' target and feature interaction engineering were applied. 
These steps helped identified and corrected a little on the predictions. However, the predictions were still around a small range between 78-81 likely due to weak predictors signal and coefficients.

Therefore, in the EDA for feature study and visualization section, only median filled null 'FinalGrade' values were used. 
In this section, the author performed a more targeted EDA and visualizations on the features for potential final grade outcome.



***Studies topics***
1. How daily study hours and attendance rate affect student performance (two features in tandem on final grade).
2. How parental support influence grade improvements / declination using (final grade vs previous grade).
3. How online classes influence grade improvements / declination using (final grade vs previous grade).
4. How extracurricular actvities affect highest performing and lowest performing students.
5. Other general graphs (distribution of final grade by gender, distribution of final grade by study hours and attendance rate,
   consistency of features for students who scored A and not A -> bigger radialaxis means similarity in student behaviours.

***Limitations of this Project***
1. The model's predictions possibly did not have strong enough coefficients / features were weak / not large enough (near 900 records after cleaning).
2. Intitial plan was to have model train from non-null values, and predict null final grades. However, since the evaluation metrics showed inappropriate results,
   and predictions ended with a small range, EDA was done on original final grade with median-filled NA values instead.
3. The number of records for this dataset is limited to near 900 records after data cleaning and transformation. Therefore, the EDA results may not be as evident.

***Lesson Learned from this Project***
1. Linear regression model predicts continuous scale feature like temperature, price, sales while logistic regression model predicts categorical feature like yes/no, fraud/not fraud.
2. .agg() can be used to use multiple aggregation functions like sum, min and max together.
3. .melt() can convert wide tabular formats to long format which then can be used for graphs.
   (convert multiple columns, into one column holding column names as value, and the column holding those column values in another column)
4. Using .add_vrect() and .add_hline() to emphasize trends on graphs.
