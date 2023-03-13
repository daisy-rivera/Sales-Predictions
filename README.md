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

###Item Outlet Sales by Outlet Type
![Capture2](https://user-images.githubusercontent.com/122565297/224844265-cc837f94-4593-40bf-8a87-d96bcef0915b.PNG)
- SupermarketType3 clearly has the most sales. It would be useful to understand more what the differences are between the different types of supermarket outlets to disect further why these outlets are selling more than the others.

## Results
- Comparing both the Decision Tree and Linear Regression models, the Decision Tree Model performed better overall. I utilized various regression metrics to evaluate and compare both models and the Decision Tree model had better results

### For further information
For any additional questions, please contact **daisy.dinny@hotmail.com**
