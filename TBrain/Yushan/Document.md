# Documents for how the script modify



* [Results of different version](#Results)
* [Modifications and Ideas of data manipulating](#Ideas)

--------------------------



## Results

* V1: TBrain_Yushan_linear_reg_745.ipynb,  TBrain_Yushan_lasso_816.ipynb, TBrain_Yushan_lgbm_1723.ipynb
  
  * Use all features
  
  * Didn't generate new features
  
  * Didn't use one hot encode
  
  * Didn't deal with outlier
  
  * User linear regression -> have negative price
  
    
  
* V2: TBrain_Yushan_lgbm_1987.ipynb

  * Exclude outliers
  * With basic feature engineers [5/5 modification]
  * change categorical variable list -> exclude include txn_floor, etc





## Ideas

* 5/5 modification 
  * remove outliers
  * change categorical variable
  * feature modification



* Pending

  need to revamp the logic of impute the missing value 

  predict the total_price based on groups

  interesting finding: can groups data based on columns from 12:end and label them as new group

  

  feature creation (pending)

  - 建物面積 容積率
  - 看為何有些建物landing area, building area一樣 -> 同個建物？！

  model stacking

  give label of each groups and predict by groups