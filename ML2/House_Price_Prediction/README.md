# House-Price-Prediction IIITB December 2019
A US-based housing company named Surprise Housing has decided to enter the Australian market. The company uses data analytics to purchase houses at a price below their actual values and flip them on at a higher price. For the same purpose, the company has collected a data set from the sale of houses in Australia. The data is provided in the CSV file below.

 

The company is looking at prospective properties to buy to enter the market. You are required to build a regression model using regularisation in order to predict the actual value of the prospective properties and decide whether to invest in them or not.

 

The company wants to know:

Which variables are significant in predicting the price of a house, and

#### Suggestions for Surprise Housing is to keep a check on these predictors affecting the price of the house.

#### The higher values of positive coeeficients suggest a high sale value.

#### Some of those features are:-
 |  Feature  |  Description  |
 |  ---  |  ---  |
 |  GrLivArea  |  Above grade (ground) living area square feet  |
 |  OverallQual  |  Rates the overall material and finish of the house  |
 |  OverallCond  |  Rates the overall condition of the house  |
 |  TotalBsmtSF  |  Total square feet of basement area  |
 |  GarageArea   |Size of garage in square feet  |
        
#### The higher values of negative coeeficients suggest a decrease in sale value.

#### Some of those features are:-
   |  Feature  |  Description  |
   |  ---  |  ---  |
   |  PropAge  |  Age of the property at the time of seeling  |
   |KitchenQual_TA	| Kitchen status looks to be Typical/Average
   |KitchenAbvGr	| Kitchen is above grade
   |  MSSubClass  |  Identifies the type of dwelling involved in the sale  |
    

#### When the market value of the property is lower than the Predicted Sale Price, its the time to buy.



How well those variables describe the price of a house.

 ### These are the final features that should be selected for predicting the price of house

### Hence the equation:
    
####    Log(Y) = C + 0.125(x1) + 0.112(x2) +  0.050(x3) + 0.042(x4) + 0.035(x5) + 0.034(x6) + 0.024(x7) +  0.015(x8) + 0.014(x9) + 0.010(x10)
####                + 0.010(x11) + 0.005(x12) - 0.007(x13) - 0.007(x14) - 0.008(x15) - 0.095(x16) + Error term(RSS + alpha * (sum of absolute value of coefficients)




Also, determine the optimal value of lambda for ridge and lasso regression.

For Lasso : alpha = 0.01
The R2 score for train and test 
Train: 0.8854624158407248
Test: 0.8894603158029369
RMSE : 0.12573595366706633

For Ridge : alpha = 2
The R2 score for train and test 
Train: 0.9364594823911133
Test: 0.9077597079466575
RMSE : 0.1148578559506103

Assignment Part-II

Question 1

What is the optimal value of alpha for ridge and lasso regression? What will be the changes in the model if you choose double the value of alpha for both ridge and lasso? What will be the most important predictor variables after the change is implemented?

Solution: In the case of ridge regression: - When we plot the curve between negative mean absolute error and alpha, we see that as the value of alpha increase from 0 the error term decrease and the train error is showing increasing trend when value of alpha increases. when the value of alpha is 2 the test error is minimum so we decided to go with value of alpha equal to 2 for our ridge regression. 

For lasso regression I have decided to keep very small value that is 0.01, when we increase the value of alpha the model try to penalize more and try to make most of the coefficient value zero. Initially it came as 0.4 in negative mean absolute error and alpha. 
When we double the value of alpha for our ridge regression no, we will take the value of alpha equal to 10 the model will apply more penalty on the curve and try to make the model more generalized that is making model simpler and no thinking to fit every data of the data set. from the graph we can see that when alpha is 10, we get more error for both test and train. 
Similarly, when we increase the value of alpha for lasso, we try to penalize more our model and more coefficient of the variable will reduced to zero, when we increase the value of our r2 square also decreases. 
The most important variable after the changes has been implemented for ridge regression are as follows: - 
1. MSZoning_FV 
2. MSZoning_RL 
3. Neighborhood_Crawfor 
4. MSZoning_RH 
5. MSZoning_RM 
6. SaleCondition_Partial 
7. Neighborhood_StoneBr 
8. GrLivArea 
9. SaleCondition_Normal 
10. Exterior1st_BrkFace 

The most important variable after the changes has been implemented for lasso regression are as follows: - 
1. GrLivArea 
2. OverallQual 
3. OverallCond 
4. TotalBsmtSF 
5. BsmtFinSF1 
6. GarageArea 
7. Fireplaces
8. LotArea 
9. LotArea 1
10. LotFrontage


Question 2

You have determined the optimal value of lambda for ridge and lasso regression during the assignment. Now, which one will you choose to apply and why?

Solution: It is important to regularize coefficients and improve the prediction accuracy also with the decrease in variance, and making the model interpretably. 
Ridge regression, uses a tuning parameter called lambda as the penalty is square of magnitude of coefficients which is identified by cross validation. Residual sum or squares should be small by using the penalty. The penalty is lambda times sum of squares of the coefficients, hence the coefficients that have greater values gets penalized. As we increase the value of lambda the variance in model is dropped and bias remains constant. Ridge regression includes all variables in final model unlike Lasso Regression. 
Lasso regression, uses a tuning parameter called lambda as the penalty is absolute value of magnitude of coefficients which is identified by cross validation. As the lambda value increases Lasso shrinks the coefficient towards zero and it make the variables exactly equal to 0. Lasso also does variable selection. 
When lambda value is small it performs simple linear regression and as lambda value increases, shrinkage takes place and variables with 0 value are neglected by the model.
 

Question 3

After building the model, you realised that the five most important predictor variables in the lasso model are not available in the incoming data. You will now have to create another model excluding the five most important predictor variables. Which are the five most important predictor variables now?

 Solution: 
Those 5 most important predictor variables that will be excluded are: - 
1. GrLivArea 
2. OverallQual 
3. OverallCond 
4. TotalBsmtSF 
5. GarageArea


Question 4

How can you make sure that a model is robust and generalisable? What are the implications of the same for the accuracy of the model and why?

 Solutions:
The model should be as simple as possible, though its accuracy will decrease but it will be more robust and generalisable. It can be also understood using the Bias-Variance trade-off. The simpler the model the more the bias but less variance and more generalizable. Its implication in terms of accuracy is that a robust and generalisable model will perform equally well on both training and test data i.e., the accuracy does not change much for training and test data. 
Bias: Bias is error in model, when the model is weak to learn from the data. High bias means model is unable to learn details in the data. Model performs poor on training and testing data. 
Variance: Variance is error in model, when model tries to over learn from the data. High variance means model performs exceptionally well on training data as it has very well trained on this of data but performs very poor on testing data as it was unseen data for the model. It is important to have balance in Bias and Variance to avoid overfitting and under-fitting of data.


# Business Goal 

You are required to model the price of houses with the available independent variables. This model will then be used by the management to understand how exactly the prices vary with the variables. They can accordingly manipulate the strategy of the firm and concentrate on areas that will yield high returns. Further, the model will be a good way for management to understand the pricing dynamics of a new market.
Ridge and Lasso Regeression
