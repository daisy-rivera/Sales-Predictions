# Sales Predictions
## Making Sales Predictions Using Machine Learning 
**Daisy Rivera**: 
### Objective:
To help the retailer understand the properties of products and outlets that play crucial roles in increasing sales.
### Data:
[Link to original dataset](https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/) <br>
This dataset had a total of 8523 rows and 12 columns of information. There were a total 5 numeric columns and 7 categorical columns.

### Items that needed to be addressed: 
-  The data had 2 columns with missing items.
-  There was a column with inconsistent categories misspellings.
-  One of the columns was an Ordinal and had to changed to numerical.

### Preprocessing for Machine Learning Models
- Inconsistent categories were fixed
- Ordinal column was assigned numberic values
- Features and Target Values were assigned. In this case Item_Outlet_Sales was our Target.
- The data was split into a training and testing dataset using the default 75/25 split.
- Created a processor to include 2 Pipelines(one for categorical columns and one for numeric columns)
 - For categorical columns:
   - Addressed missing items using a constant SimpleImputer 
   - Converted categorical columns into numeric by using the OneHotEncoder
 - For numeric columns:
   - Addressed missing items usnig a mean SimpleImputer
   - Scaled all numeric columns
 
 ### Machine Learning Models
 - Created 2 Machine Learning models
   - Linear Regression Model
   - Decision Tree Model
   
 #### Average Item Sales by Type and Fat Content
![Capture](https://user-images.githubusercontent.com/122565297/224843606-a74eef3e-0c32-43ee-b561-9f9a0e70d174.PNG) 
- Comparing the sales by Item and their fat content, we can see that the sales of certain items are clearly influenced by whether they are low fat or regular. An observation I see is that items which tend to have high levels of sugars such as snacks, drinks and breakfast are the items that sell more low fat content.

### Item Outlet Sales by Outlet Type
![Capture2](https://user-images.githubusercontent.com/122565297/224844265-cc837f94-4593-40bf-8a87-d96bcef0915b.PNG)
- SupermarketType3 clearly has the most sales. It would be useful to understand more what the differences are between the different types of supermarket outlets to disect further why these outlets are selling more on average than its counterparts.

### Top 5 Most Important Features
![5_most_important](https://github.com/daisy-rivera/Sales-Predictions/assets/122565297/f922d1b4-f2d2-4396-bfc9-824ae85d84e8)
- These are the features that our model used the most.

### Top 3 Coefficients
![3_largest_coeffs](https://github.com/daisy-rivera/Sales-Predictions/assets/122565297/3858377f-b03b-4209-ab1b-eb077fc8c200)
- All of my coefficients were categorical items. The 3 largest coefficients I have are: OUtlet_Size_Medium, Outlet_Identifier_OUT019 and Outlet_Type_Supermarket Type3. Belonging to these categories will have the following changes to the target:
  - Outlet_Size_Medium : 33577528470196481 
  - Outlet_Identifier_OUT019 : 3137133190522628
  - Outlet_Type_Supermarket Type3 : (-3068332354615559.5)

### Shap Feature Summary (BAR)
![bar_shap_summary](https://github.com/daisy-rivera/Sales-Predictions/assets/122565297/c3c59cba-b196-4170-ad18-4c9d88a464a8)
- Comparing the feature importances to the shap values above, I show that I have the same exact Top 5 features only in different orders. The Item_MRP is the biggest contributor to the predictions by far. Also, the Outlet_Type_Supermarket Type1 is the 5th feature on both graphs.

### Shap Feature Summary (Dot)
![dot_shap_summary](https://github.com/daisy-rivera/Sales-Predictions/assets/122565297/3cb6a6f4-b6ff-4f27-98a2-2b74ce435dca)
- The Shap Summary above shows that our 3 most important features are Item_MRP, Outlet_Type_Supermarket Type3 and Outlet_Identifier_OUT010.
  - Item_MRP had the largest effect on the model's predictions. This is an integer feature so looking at the graph I can see that the higher the Item_MRP was, the more positively higher the predicted price was. The lower the Item_MRP was the more negatively lower the predicted sales were.
  - Outlet_Type_Supermarket Type3 was a categorical feature. Based on the graph above when this category was selected it had a high positive impact on the overall sales.
  - Outlet_Identifier_OUT010 was also a cetgorical feature. This feature however, had a negative impact on the overall sales the more it was selected.

### Local Explanations
![Local_Importance_Supermarket_Type3](https://github.com/daisy-rivera/Sales-Predictions/assets/122565297/f150851d-d603-498f-a5cb-67009d1e157b)
![Lime_SupermarketType3](https://github.com/daisy-rivera/Sales-Predictions/assets/122565297/dd61e15a-d369-4ddd-80d4-6d628c623b2d)
- The plots above show a single example of a random sales prediction. I chose to evaluate a random sample from Supermarket Type3 since this Supermarket has the highest average sales. We can see that this sample was impacted positively by the Outlet_Type_Supermarket Type3 however, the Item_MPR impacted the sale negatively. This random item happened to be a fruit and vegetable item which may be why it's price was low. This sale falls below the base value of 2154.

## Results
- Comparing both the Decision Tree and Linear Regression models, the Decision Tree Model performed better overall. I utilized various regression metrics to evaluate and compare both models and the Decision Tree model had better results predicting future sales prices.

### For further information
For any additional questions, please contact **daisy.dinny@hotmail.com**
