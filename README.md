## Assignment_SCM
SE20UARI160,SE20UARI146,SE20UARI141,SE20UARI112,SE20UARI095,SE20UARI020

# Data Preprocessing
Steps taken:
1)Checked for null values and filled using forward fill(ffill)  
2)Looked at the correlation matrix and dropped base_price  
3)Removed store_id column due to high multicollinearity (high VIF)  

# Model Building
Steps taken:  
1)The data was split into training and test sets with a 80-20 split. The features were scaled using StandardScaler.  
2)Hyperparameter tuning done on KNearestRegressor:  
   .A loop is used to test different numbers of neighbors (from 1 to 199) to find the optimal number for      the KNN regression model.  
   .For each number of neighbors, the KNN model is trained, and RMSE (Root Mean Squared Error) and R-         squared (R^2) scores are calculated on the test set.  
   .17 Neighbours gave minimum RMSE  
   .Another loop tests different values of the power parameter (p) for the KNN model (from 1 to 4). This      helps identify the optimal value for the Minkowski distance metric used in KNN.  
   .Similar to the previous step, RMSE and R^2 scores are calculated for each value of p, and plots are       generated.  
   .p=1 gave minimum RMSE  
  
The final model used KNeighborsRegressor with n_neighbors=17 and p=1.  
The final RMSE on test set was 38.84. The final R^2 on test set was 0.56.  

# Issues Faced
Data Preprocessing: It's important to handle missing data appropriately. 

