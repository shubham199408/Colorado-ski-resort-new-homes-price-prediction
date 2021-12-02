# Colorado-ski-resort-new-homes-price-prediction in R


The Colorado ski resort property firm wants to build a model for estimating a house sale price based on the data collected. The corresponding pricing model will be used to evaluate initial selling prices for homes.

**EXPLORATORY DATA ANALYSIS:**

Exploratory analysis is often the initial step of data analysis. Here we get familiar with data, visualize the data in a number of forms, analyse relationships between the variables, look for outliers, patterns and trends in the data.

The very first step in EDA is to check the dimension of the input dataset and the type of variables.

![image](https://user-images.githubusercontent.com/95050679/144357669-8af22048-5d01-4b50-8757-86a080b0d5f1.png)

From above figure, we see that the data set contains 39 rows and 12 columns. We will deal with numerical variables and one of the variables is labeling variable, i.e., rty# which is used to identify each property.

Our second step in the EDA is to check if the given input data has any missing values before diving deep into the analysis.

![image](https://user-images.githubusercontent.com/95050679/144357728-5aa4e7be-016d-41c0-be15-86f655a11ad4.png)

From Figure above we can infer that there are no missing values in this data set.

Figure below shows summary on the quantity of zeros(q_zeros), percentage of zeros(p_zeros), quantity of infinite values (q_inf), percentage of infinite values(p_inf), quantity of NA(q_na) percentage of NA(p_na), data type (type), quantity of unique values (unique) for every column in the data set file. The reason for considering this output is that variables with lots of zeros, several missing values may not be useful for analysis and can cause a bias model.

![image](https://user-images.githubusercontent.com/95050679/144357826-3bb0493a-9d74-4766-ad56-36cce49e593a.png)

Let’s explore all the variables and get a good understanding of each data variable before buiding a model. We will look at the histogram which tells us about the shape of the distributions, box plot to see if there are any potential outliers and summary statistics for each of the numerical variables. 

Since rty# is a labeling attribute so we are not going to use it for any analysis.

**Univariate analysis:**

**1.Bedrooms**

For the variable bedrooms, we see that this distribution has a skewness to the right. We can state that by looking at the summary values of mean and median where mean (3.487) is greater than median (3.000) and also to the shape of the histogram and box plot as shown below.

![image](https://user-images.githubusercontent.com/95050679/144357971-6be4f683-9f50-4584-809b-b0724023247a.png)
![image](https://user-images.githubusercontent.com/95050679/144357973-479d0708-6924-4dc9-b49b-12d464c33dfd.png)
![image](https://user-images.githubusercontent.com/95050679/144357978-b9a5ea1b-60c8-4c68-b05a-5a89bbd4bfbd.png)

The minimum number of bedrooms is 2 and maximum is 6 and majority of the homes at Colorado ski resort have 3 or 4 bedrooms which sums upto 29 houses of 39.

**2.Bathrooms**

For the variable bathrooms, we sight that this distribution has a slight skewness to the right. We can state that by looking at the summary values of mean and median where mean (2.513) is slightly greater than median (2.000) but also to the shape of the histogram and box plot as shown below.

![image](https://user-images.githubusercontent.com/95050679/144358082-2af91d28-d7da-47ce-bd97-2ed3f07b5c06.png)
![image](https://user-images.githubusercontent.com/95050679/144358089-195e5d35-14ea-4df1-ad76-fd87015eb014.png)
![image](https://user-images.githubusercontent.com/95050679/144358093-af044988-648f-4e5c-8801-d31e34904a2a.png)
 
The minimum number of bathrooms is 1 and maximum is 4.75 and majority of the homes at Colorado ski resort have 2 or 3 bathrooms which sums upto 26 of 39 houses.

**3.Sq_ft**

Sq_ft decribes the size of the house measured in number of square feet. From Figure 8 and 9 we see that this distribution has a skewness to the right. We can state that by looking at the summary values of mean and median where mean (2004) is greater than median (1922).

![image](https://user-images.githubusercontent.com/95050679/144358156-7c605734-92b9-4e81-9b1d-3b2862f43021.png)
![image](https://user-images.githubusercontent.com/95050679/144358166-a4abf320-d6fc-411e-86a5-924d964ba5fb.png)
![image](https://user-images.githubusercontent.com/95050679/144358174-c57657e7-4f84-4494-ba52-66239f07f7b1.png)

The minimum number of sq_ft living is 968 sq_ft and maximum is 3875 with majority of houses between 1000-2500 sq ft which sums upto 30 of 39 houses.

**4.Downtown**

Downtown describes the miles from the property to the downtown resort area. We see that this distribution has a strong skewness to the right. We can state that by looking at the summary values of mean and median where mean (8.692) is greater than median (5.000) but also to the shape of the histogram and boxplot as shown below.

![image](https://user-images.githubusercontent.com/95050679/144358265-419c7512-1f75-456a-a3d1-711ac0634669.png)
![image](https://user-images.githubusercontent.com/95050679/144358274-bdf26a45-25dc-424a-9a19-2999e47c65d9.png)
![image](https://user-images.githubusercontent.com/95050679/144358280-3851222d-2fcc-44f2-a19a-36c2e52b32a3.png)

The minimum miles from the property to the downtown is zero which means that there are houses which are in the downtown area and maximum miles from a property to the downtown is  52. We can say that the majority of the houses are located in the downtown or within 10 miles of the downtown.

**5.Mountain**

Mountain describes the miles from the property to the base of the ski resort’s facing mountain. We see that this distribution has a strong skewness to the right. We can state that by looking at the summary values of mean and median where mean (9.667) is greater than median (7.000) but also to the shape of the histogram and boxplot as shown below

![image](https://user-images.githubusercontent.com/95050679/144358536-7a56dac0-db6a-42ed-9795-6487aae2b334.png)
![image](https://user-images.githubusercontent.com/95050679/144358544-b85eb38c-01fe-445c-931a-e01e930341cf.png)
![image](https://user-images.githubusercontent.com/95050679/144358557-a85f11cf-125f-486d-8684-f534bdf26159.png)

The minimum miles from the property to the base of the ski resort’s facing mountain is 1 and the maximum miles from the property to the base of the ski’s resort facing mountain is 48. Majority of the property are located within 10 miles of the base of the ski’s resort

**6.Lot size**

For the variable lot size, we see that this distribution has a strong skewness to the right. We can state that by looking at the summary values of mean and median where mean (2.597) is greater than median (0.340) but also to the shape of the histogram and boxplot as shown in Figure below.

![image](https://user-images.githubusercontent.com/95050679/144358735-3fd97156-83e0-4c05-b0dd-c7098107b447.png)
![image](https://user-images.githubusercontent.com/95050679/144358750-1186824a-4aef-442c-8541-7b53813203a3.png)
![image](https://user-images.githubusercontent.com/95050679/144358760-9f062d98-11ec-4960-9930-7860d1939016.png)

The minimum size of the property is 0.1 acres and mximum size of the property is 40 acres. Majority of the properties are below 3 acres.

**7.Garage**

Garage describes the number of cars that will fit into the garage and see that this distribution is slight left skewed . We can state that by looking at the summary values of mean and median where median (2.000) is greater than mean (1.564) but also to the shape of the histogram and boxplot as shown in Figure below.

![image](https://user-images.githubusercontent.com/95050679/144358911-6d211e6f-b5a9-4da5-a67a-d8948261e9de.png)
![image](https://user-images.githubusercontent.com/95050679/144358917-ab4a492f-0584-480c-bbd3-3c1b47943de1.png)
![image](https://user-images.githubusercontent.com/95050679/144358926-c9341e51-3fbc-4484-977c-5cf74fb5037f.png)

There are houses that has no garage and the highest number of cars that can fit into a garage is 4. Majority of the houses has a garage that can fit in 2 cars.

**8.Age**

Age variable decribes the age of the house at the time it was listed in years. We sight that this distribution has a skewness to the right. We can state that by looking at the summary values of mean and median where mean (19.46) is greater than median (16.0) but also to the shape of the histogram and boxplot as shown in Figure below

![image](https://user-images.githubusercontent.com/95050679/144359120-742e2813-32a0-447f-a002-d63719d4986a.png)
![image](https://user-images.githubusercontent.com/95050679/144359124-e717cecb-1221-433f-a15b-de8040380f6b.png)
![image](https://user-images.githubusercontent.com/95050679/144359137-dc6cccfd-58b2-43b9-953b-22f1212dc70b.png)

The minimum age of the house is 3 years and the oldest house is 80 years old at the time it was listed. Majority of the houses are 10-20 years old.

**9.On market**

On market variable describes the number of days the house was on the market before it was sold and we see that this distribution has a skewness to the right. We can state that by looking at the summary values of mean and median where mean (131) is greater than median (105) but also to the shape of the histogram and boxplot as shown in Figure below.

![image](https://user-images.githubusercontent.com/95050679/144359208-756161b3-a32d-4157-84e8-6797507bb14b.png)
![image](https://user-images.githubusercontent.com/95050679/144359212-5894162e-6435-4fcd-a25c-fb7701b1dfbb.png)
![image](https://user-images.githubusercontent.com/95050679/144359217-93b7e92e-2ea9-464b-b448-826ac695f5cb.png)

The minumim number of days the house was on the market before it was sold is 16 days and the maximum number of days the house was on the market before it was sold is 412 days. We can say that the majority of the houses have been for less than 150 days on the market.

**10.Selling price**

For the variable selling price, we see that this distribution has slight skewed to the right. We can state that by looking at the summary values of mean and median where mean (409.9) is slightly greater than median (400) but also to the shape of the histogram and boxplot as shown in figure below

![image](https://user-images.githubusercontent.com/95050679/144359293-ca5e013e-279f-4545-b510-24284ddeb87f.png)
![image](https://user-images.githubusercontent.com/95050679/144359297-18f99ea5-881e-4541-a089-18a790ed5b03.png)
![image](https://user-images.githubusercontent.com/95050679/144359307-a0ec8167-114a-4c7e-9ea0-cbdb8bdfd916.png)

The minimum selling price of the property is 315 (thousand $) and maximum is 545 (thousand $) with median of 400 (thousand $).

**11.List price**

List price variable describes the original asking price of the property ($1000). We sight that this distribution has skewness to the right. The summary values of mean and median shows that mean (420.4) is slightly greater than median (409.9) and this is also evident to the shape of the histogram and boxplot of list price as shown in figure below

![image](https://user-images.githubusercontent.com/95050679/144359394-d4523c0c-9f0f-4f87-b142-b7ceb4700a6f.png)
![image](https://user-images.githubusercontent.com/95050679/144359406-0bd26de8-83f1-49e8-aea7-02547d46e236.png)
![image](https://user-images.githubusercontent.com/95050679/144359415-b05ec9a5-9ab0-41fd-98b4-cf694af24587.png)

The minimum selling price of the property is 335 (thousand $) and maximum is 550 (thousand $) with median list price being 409(thousand $).


**Multivariate analysis:**

**Correlation**

A correlation matrix/heat map of the data set as shown in Figure below represents the pearson correlation coefficient value ranging between -1 and 1 that indicates the extent to which two variables are linearly related where -1 indicates perfect negative linear relationship, correlation of 0 indicates that two variables don’t have any linear relationship whatsoever and correlation coefficient of 1 mean two variables are perfectly positively linearly related.

![image](https://user-images.githubusercontent.com/95050679/144359492-d3f34d68-a6af-42a2-bd3e-38f96bfc413f.png)

We are more concerned in the correlation between selling price and the other variables. We see strong correlations between selling price and sq_ft, number of bathrooms and number of bedrooms (all indicate a shade of orange to red) and negative correlations with miles from mountain, miles from the downtown and age of the house at the time it was listed. We also want to look at the likely relationships between the predictor variables. 

Lets look at Figure below which shows the correlation table for this data set.

![image](https://user-images.githubusercontent.com/95050679/144359543-6bfe4f8e-429b-4040-993d-53d100043e06.png)

From the above correlation table we can infer the following correlation between the variables which are as follows:
•	We see that there is strong positive relationship between bathrooms and bedrooms with a correlation value of 0.72

•	There is also strong positive relation between sq_ft and bathrooms with a correlation value of 0.76

•	We can also infer that there is strong positive relationship of selling price with bedrooms, bathrooms and sq_ft

•	Another strong positive relationship is between Downtown and Mountain with a correlation coefficient value of 0.90

•	We can infer from the table that there is perfect linear relationship between list price and selling price which indicate that these two variables are almost same

•	Another strong relationship is between mountain and downtown with correlation coefficient value of 0.90


These relationships can also be observed visually with the scatterplot matrix as shown in Figure 26. It consisting of a collection of scatterplots for each variable-combination of ski dataset. Each of the scatterplot in the matrix pictures the relationship between a pair of variables which allows many relationships to be explored in just one diagram. If the data points make a straight line going from the left corner out to high x- and y-values, then the variables are said to have a positive correlation . If the data points goes from a high-value on the y-axis down to a high-value on the x-axis, the variables have a negative correlation.

![image](https://user-images.githubusercontent.com/95050679/144359690-e0317df2-2356-4f49-8cf9-bcbe7947d5eb.png)


Figure below shows the log transformation for all the variables for which the data distribution was very skewed to the left or right in order to normalize the data.

![image](https://user-images.githubusercontent.com/95050679/144359818-66bd2b90-fc31-401e-96a9-efa73d950d70.png)


**MODEL BUILDING**

Our goal is to construct a model to predict the selling price of new houses at a Colorado ski resort based on available data.We will build a model to predict the selling price of properties based on the given variables. Since we have multiple variables to predict the y value, we will be using multiple linear regression which is one of the core method for developing a model.

First of all we tried to look at the relative importance for selling price with respect to all the variables using 95% bootstrap confidence intervals which can be seen in below figure


![image](https://user-images.githubusercontent.com/95050679/144359873-1fb18151-c909-4834-9530-1b33d8bbf234.png)

From the figure above we can see that Bathroom and Square Feet have the highest relative importance(greatest influence on R^2 values) with respect to Selling Price as the dependent variable. On the other hand, we can see Garage, Onmarket, Age and Downtown have the least contribution towards the R^2 of a model where Selling price is the dependent variable. 


**Model Diagnosis and Selection**

**In this step we will be using three approaches – Manual approach, Step Regression, The Best-Subsets approach to best model**

**MANUAL APPROACH**

In order to select the best model, we will start by using all the variables for the initial model, which is model 1. 

**MODEL 1**

![image](https://user-images.githubusercontent.com/95050679/144360017-7391723d-6516-4e8f-9708-7621a3941d6c.png)

![image](https://user-images.githubusercontent.com/95050679/144360033-125a6a98-af72-45fa-9141-3b95746628fb.png)


After conducting the summary and model analysis for the model 1, we found out some of the findings which are as follows:

1) The p-values for all variables except Listprice is more than 0.05, which means that at the 95% significance level, those variables are not significant. 

2) The VIF values for Downtown, Listprice and Mountain are more than the selected threshold, 5. This means we can’t use these variables in the same model since it leads to a problem of multi-collinearity. 

3) Summary also provide R-squared and Adjusted R-squared value. R-squared indicates  the proportion of the variation in your dependent variable (Y) explained by your independent variables (X) for a linear regression model which can be interpreted as 0.9852 or 98.52 %.
 R-square will be increased simply by adding additional predictors to the model, thus adjusted R-Squared is used instead of R-squared for comparing models with more than one predictor variable.

We also realized that Listprice is highly correlated with Selling Price, hence we should not include that variable in the model, to avoid overfitting. Therefore, in the next model, we excluded listprice and ran the model. 

**MODEL 2**

For the model 2 we took all the variables except for the list price and perform the summary and analysis for the same

![image](https://user-images.githubusercontent.com/95050679/144360075-c5dc84db-c9ee-43b3-b038-f6696aa38e16.png)

![image](https://user-images.githubusercontent.com/95050679/144360088-fb5f551b-0cb3-4236-a3fa-c2c8a7cadf8d.png)

After conducting the summary and model analysis for the model 2, we found out some of the findings which are as follows:

•	The p-values for Bathroom, Downtown, Age and On Market variables are not significant at the 95% significance level. All the other variables are significant in this model.  

•	The VIF values for Downtown and Mountain are more than the selected threshold, 5. This means we can’t use these variables in the same model since it leads to a problem of multi-collinearity. 


•	The adjusted R-squared value was 0.8216 which can be interpreted as 82.16 percent, a considerable drop form the previous model because list price was overfitting the model and was giving very high R-squared values. 

From this model, we see that between Downtown and Mountain, we need to choose one variable to avoid multicollinearity. We removed Downtown variable from the previous model since Mountain had a higher significance when compared to Downtown. 


**MODEL 3**

![image](https://user-images.githubusercontent.com/95050679/144360123-26e58546-ced9-4782-a704-5d3b28155046.png)

![image](https://user-images.githubusercontent.com/95050679/144360132-43df29b3-61e1-4996-8bc4-e492c176c4fb.png)

After conducting the summary and model analysis for the model 3, we found out some of the findings which are as follows:

•	The p-values for Bathroom is not significant at the 95% significance level. All the other variables are significant in this model.  
•	The VIF values for all variables in this model are less than the selected threshold, 5. This means we can use these variables in the same model since it avoids the problem of multi-collinearity. 
•	The adjusted R-squared value was 0.8335, which is higher than the previous model, which is a good sign. 

Therefore, for the final model, we will remove Bathroom run the model.

**FINAL MODEL**

For the final model we removed bathroom variable from the model and ran the summary and analysis for the model

![image](https://user-images.githubusercontent.com/95050679/144360193-79c66401-dea5-4167-93a0-dc15bfffde9b.png)

![image](https://user-images.githubusercontent.com/95050679/144360205-7cea44c7-8725-4f7a-89bb-8e7f803eb0a1.png)

After conducting the summary and model analysis for the final model, we found out some of the findings which are as follows:

•	The p-values for all the variables are significant at the 95% significance level.  
•	The VIF values for all variables in this model are less than the selected threshold, 5. This means we can use these variables in the same model since it avoids the problem of multi-collinearity. 
•	The adjusted R-squared value was 0.8338, which is higher than the previous model.

Therefore our final model comprised of Bedroom, Bathroom, Sq_ft, Mountain, Lot size and garage.

Now, we used Stepwise regression method to find the best model for this dataset

**Model Diagnosis and Selection(Approach 2): Stepwise regression approach to Model Building**

![image](https://user-images.githubusercontent.com/95050679/144360254-7f6e6a52-bbf0-499a-a723-00a65e917b31.png)
![image](https://user-images.githubusercontent.com/95050679/144360261-8bb3d2b8-f325-42d0-aed1-2f752f4c7a1e.png)
![image](https://user-images.githubusercontent.com/95050679/144360267-b960e2ac-32d9-4289-989e-88fdfb6d34d4.png)


After doing the stepwise regression on the data set which can be seen in the figure above we found out following findings:
•	After running the summary for the model which we got from step regression method we got the best model with variable which are Bedrooms, Sq_Ft, Mountain, Lot size and garage which is same as the model we got from manual approach

•	Adjusted R-Squared value for the model is 0.8338 which can be interperated as 83.38% which suggests that 83.38% of the change in selling price is explained by changes in the independent variables used in the final model.

•	We can also see that the AIC is reducing as On Market, Age, Downtown and Bathrooms have been removed from the model. The model is best if the AIC score is low, which means this is a good sign. 

•	From this model, we can also see that all the variables are significant, having all p-values less than 0.05. 

•	The VIF for all the variables in the model is also less than 5, which suggests that there is no collinearity within the independent variables used in this model. 

Another technique which we use to find the best model for our dataset was The best-subsets Approach 

**Model Diagnosis and Selection(Method 3): The Best-subsets approach to Model Building**

![image](https://user-images.githubusercontent.com/95050679/144360334-db3ccba8-a7bb-43bb-8d8a-c4417e98ce84.png)

![image](https://user-images.githubusercontent.com/95050679/144360341-4ce92c7c-b0c2-4d58-956d-0b7d95fd928d.png)

After doing the Best-Subsets approach on the data, we found the same variables being used that we used for the manual and stepwise regression method. The R2 value is 83% when you use the variables Bedrooms, SqFt, Mountain, Lotsize and Garage. 


**MODEL VALIDATION:**

![image](https://user-images.githubusercontent.com/95050679/144360393-4c77af65-cf1d-43ff-90f3-abf7403eb768.png)

We have performed k-fold cross validation on the dataset. In this case, we have chosen k=5 for this case. 

From the output, we can see that for each fold, the R2 values range from 69.7% to 89.89%. This is consistent with the R2 we got with the STEP AIC or the manual or the best subset method. The average R2 is around 80% whereas the R2 we got for our final model was 83.38%. This shows that the model will be able to predict new data as well. The RMSE and MAE also is low, which is a good sign as well. 

Hence, the final model we choose is: 

Selling price= 263.06+21.83(Bedrooms)+0.04(Square Feet)-4.3(Mountain)+4.08(Lot Size)+13.657(Garage)

**MODEL ASSUMPTION TESTING:**

Since we got the same model using the three techniques, we go ahead with the Stepwise regression model. We will check the assumptions of multiple linear regression on this model. 

Assumptions Testing:

1. **Linearity**: From the scatter plot of selling price vs predictor varaibles we see that there is a linear relationship. Hence, the linearity assumption is not violated.

![image](https://user-images.githubusercontent.com/95050679/144360508-d0b3411b-0f0f-464c-b4b5-61706b7e102d.png)


**2. Independence of errors**: From the DW Test, we get the value of 1.80, which is very close to 2. The closer the value to 2, it means no auto-correlation. Since the p-value is 0.2249, which is more than 0.05, it is safe to say that there is no autocorrelation in the model. This assumption is not violated.

 ![image](https://user-images.githubusercontent.com/95050679/144360692-716801cd-8cd4-449d-83c5-154b06c5a6fb.png)


**3. Normality of errors:** The normal Q-Q plot and Histogram of residuals show a positive linear relationship and a normal distribution. This assumption is not violated.

![image](https://user-images.githubusercontent.com/95050679/144360719-3a3cb41a-2368-4540-a4d8-7aaecd707e19.png)
![image](https://user-images.githubusercontent.com/95050679/144360731-60daadb3-ec01-40a9-ab1a-14dbbc805f5c.png)


**4. Homoscedasticity:** From the residual vs. fitted plot, we can see that the errors are distributed randomly and there is no apparent pattern. This assumption is not violated. 

![image](https://user-images.githubusercontent.com/95050679/144360783-515a0c76-0c25-43c9-bd76-09c121fad199.png)

**
**5. Independent variables:** The residual vs. Independent variables plot shows no pattern and it is random and constant, the VIF was also less than 5. This indicates that the assumption has not been violated.  

![image](https://user-images.githubusercontent.com/95050679/144360856-0f87d59b-65ae-41ac-b5e2-f46379a2f161.png)
![image](https://user-images.githubusercontent.com/95050679/144360862-5e8fd9db-0d70-482b-b1ae-9107283855e4.png)
![image](https://user-images.githubusercontent.com/95050679/144360867-2068a48f-2dd9-4813-9ae3-70f61cc120be.png)
![image](https://user-images.githubusercontent.com/95050679/144360874-2c1917a4-d9ac-44e6-974e-69c110ceb06c.png)
![image](https://user-images.githubusercontent.com/95050679/144360882-6cdcf803-da52-438f-9c06-5238d1e4ed3d.png)

Therefore, none of the assumptions have been violated by this model. This is the final, validated model! 





**Major Findings**

•	No missing values in the dataset.
•	The houses in this sample data set range in price from $315,000 to $545,000 with median selling price of $400,000.
•	Many of the houses have three or four bedrooms, two or three baths, are in range 1000- 2500 square feet, and are within 10 miles of the downtown resort area and have a garage that can fit in two cars.
•	House selling price has strong positive correlation with bathrooms, sq_ft and bedrooms.
•	Achieved the same best model using all the three approaches (Manual, Step Regression & The Best Subsets)
•	83.38% of the change in selling price is explained by changes in the independent variables used in the final model
•	The best model’s predictor variables – bedrooms, Sq_ft, Mountain, Lot size and garage prove to have high significance with respect to Selling price.


**Recommendations:**

•	When collecting new data, additional variables can be collected for example facilities such as pool, basement,availability of credit (mortgage interest rates), HOA vs. no HOA, renovations, etc. These will certainly make the house price prediction at Colorado ski resort more accurate.

•	We should bear in mind that all models require to be revised regularly. House prices change over time, so the model to predict the house sale pricing should be updated to stay current and reflect these changes.

•	One should also take into consideration the Walk Score, Transit Score for determining the price of a house. For example: If a grocery store is nearby the house or a school is near the house, accessibility to the highways, the walk score will be high. A high walk score should reflect as a higher selling price because of the added convenience it offers to the tenant.


































