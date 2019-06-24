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
  * TBrain_Yushan_lgbm_2080.ipynb [5/6 modification]

* V3: TBrain_Yushan_lgbm_2677.ipynb

  * 5/11 modification

  * 5/12 modification (TBrain_Yushan_lgbm_2600.ipynb)

    







## Ideas

* 5/5 modification 
  * remove outliers
  * change categorical variable
  * feature modification

* 5/6 modification

  * treat txn_floor as categorical variable and replace missing value with "None"
  * group data (assumption they might in the same building then predict)

* 5/11 

  * Feature explanations
    * house with less floor tend to be more expensive -> it's not apartment
    * building type = 0 & 4  are more expensive
    * building_complete_dt bigger -> more expensive
    * land_area small expensive
    * lat small -> expensive
    * I 類別於該房屋方圓 X 公尺點位數 -> 越小越貴
    * 該房屋與最近的 X 類別之距離 -> 越小越貴
  * Add features: # of counts of each numbers
  * take log1p for target and then change back
  * missing value method changes

* 5/12

  * inverse feature
  * add square terms
  * add interaction term (comment out)




* 6/24
  * check whether having the index will contribute better housing price
    * only need to check "\_index_50$" since for "\_index_500$" most index only has 1 variation

    

* Pending

  feature selection, kmeans

  need to revamp the logic of impute the missing value 

  predict the total_price based on groups

  interesting finding: can groups data based on columns from 12:end and label them as new group

  add square term

  feature creation (pending)

  - 建物面積 容積率
  - 看為何有些建物landing area, building area一樣 -> 同個建物？！

  model stacking

  give label of each groups and predict by groups