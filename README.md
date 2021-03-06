# Video Game Sales Estimator
Continuing the project that I did previously https://github.com/ryansxiong/Video_Game_Sales_ds_proj and creating a model to forecast the data's sales.

## Codes and Resources Used
* **Python Version**: 3.8
* **Packages**: Pandas, Numpy, Matplotlib, Seaborn, scikit learn
* **Visual Tools**: Matplotlib, Seaborn
* **Link to data**: https://www.kaggle.com/gregorut/videogamesales
* **Resources**: https://www.kaggle.com/serigne/stacked-regressions-top-4-on-leaderboard | https://www.youtube.com/watch?v=7O4dpR9QMIM

## Data Cleaning
Below you will find the changes that I made to transform the data to make it ready for modelling. 
_* The full code can be found in the folder labeled **Create VG Sales Modelling.ipynb**_

* Dropped Developer Column

<img width="965" alt="Screen Shot 2021-12-31 at 1 17 04 PM" src="https://user-images.githubusercontent.com/91089401/147839186-ec7fcbe9-9192-436e-93b0-4a20ba3e6816.png">

* Made a scatter plot to check for any outliers

<img width="1036" alt="Screen Shot 2021-12-31 at 1 21 11 PM" src="https://user-images.githubusercontent.com/91089401/147839251-945a43f6-0354-4fc0-9969-0d72d6653525.png">

* I saw that there was 1 outlier and decided to drop it from the dataset. (New scatter plot without the outlier)

<img width="1098" alt="Screen Shot 2021-12-31 at 1 24 38 PM" src="https://user-images.githubusercontent.com/91089401/147839333-83dd4ef8-e32b-44bc-ab78-50449d6cd224.png">

* Finding any missing/null values in the dataset.

<img width="1098" alt="Screen Shot 2021-12-31 at 1 31 42 PM" src="https://user-images.githubusercontent.com/91089401/147839406-59a4ef25-d4d9-415b-8f91-3b487bbe0b48.png">

* Since I do not want to fill over 50% of my data with the mode, I decided to take only the data from the year 2000 to 2020.

<img width="1098" alt="Screen Shot 2021-12-31 at 1 34 46 PM" src="https://user-images.githubusercontent.com/91089401/147839436-8712d533-8072-440b-bb2c-3ed9f49a3ccc.png">

* Rechecking the ratio of missing values in the dataset. Filtering the year did help lower the amount of missing values.

<img width="1091" alt="Screen Shot 2021-12-31 at 1 36 12 PM" src="https://user-images.githubusercontent.com/91089401/147839456-46a29676-fb5e-43bb-8166-b7df9e26f7f5.png">

* I dropped all the null values in the Critic Score column. This step got rid of most of the of the null values.

<img width="1102" alt="Screen Shot 2021-12-31 at 1 40 24 PM" src="https://user-images.githubusercontent.com/91089401/147839516-d1a722fa-8b37-4e55-a4c3-f84c94d549da.png">

* Since all the remaining missing values are low enough, I can now fill in the rest with the mode. For the User_score column, I took care of the 'tbd' value and changed it to none. Finally, I rechecked the data to see if all the missing values were taken care of. 

<img width="1114" alt="Screen Shot 2021-12-31 at 2 04 16 PM" src="https://user-images.githubusercontent.com/91089401/147839903-32d780bf-64c7-49b4-8b20-55e543e9cd84.png">

* Getting dummies for the columns Platform, Genre, and rating. I excluded Name and Publisher from the model since there were too many categories. 

<img width="1102" alt="Screen Shot 2021-12-31 at 1 59 14 PM" src="https://user-images.githubusercontent.com/91089401/147839836-66d4f37e-c325-4461-9467-ca022ea1c80b.png">

* The last step was to drop all the columns I did not want in my model. After all the data cleaning, my new dataset for the model's shape went from (16719, 15) to (7886, 41).

<img width="1103" alt="Screen Shot 2021-12-31 at 2 02 46 PM" src="https://user-images.githubusercontent.com/91089401/147839909-6e48f7a8-7621-4660-b579-889650ae7459.png">

## Modelling
Now that I have cleaned my data, I can now create a model. Below you will find all the different models that I have tested. For the cross validation scoring, I used the negative mean absolute error (NMAE).

* First, I need to define my variables. I then established my train test split to use for my models. 

<img width="1107" alt="Screen Shot 2021-12-31 at 2 14 12 PM" src="https://user-images.githubusercontent.com/91089401/147840069-b7488e56-7fc5-471b-abc9-abba0b308210.png">

* Before I test my models, I transformed the data using the log function (this applies log(1 + x) to all elements of the column) to evenly distribute the data. 

<img width="1105" alt="Screen Shot 2021-12-31 at 2 15 48 PM" src="https://user-images.githubusercontent.com/91089401/147840085-9d71d7f2-d296-4d37-82ff-744c214b6e36.png">

* Linear Regression

<img width="1097" alt="Screen Shot 2021-12-31 at 2 31 58 PM" src="https://user-images.githubusercontent.com/91089401/147840349-10c66e8a-c9a9-4554-8e82-3ab43fe5eea5.png">

* Lasso

<img width="1097" alt="Screen Shot 2021-12-31 at 2 33 38 PM" src="https://user-images.githubusercontent.com/91089401/147840368-395f0cbb-a4c1-4ee2-83e7-b390dfbc10aa.png">

* Random Forest Regression 

<img width="1096" alt="Screen Shot 2021-12-31 at 2 34 54 PM" src="https://user-images.githubusercontent.com/91089401/147840386-04180399-4a54-4e29-951b-266ea452686d.png">

* Gradient Boosting Regressor

<img width="1099" alt="Screen Shot 2021-12-31 at 2 50 57 PM" src="https://user-images.githubusercontent.com/91089401/147840631-b393a128-38ac-4fdc-9381-5dda7858f710.png">

**Tuning Models with GridSearchCV**

* Lasso with gridsearchCV
 
<img width="1104" alt="Screen Shot 2021-12-31 at 2 53 39 PM" src="https://user-images.githubusercontent.com/91089401/147840664-4779f446-affb-43a7-9404-d44aed66d507.png">

* Random Forest Regressor with gridsearchCV

<img width="1103" alt="Screen Shot 2021-12-31 at 2 55 56 PM" src="https://user-images.githubusercontent.com/91089401/147840688-c4353acf-a454-4828-978f-9c03f658de7f.png">

* Gradient Boosting Regressor with gridsearchCV. I tried two different parameters to see if I could improve the model.

<img width="1103" alt="Screen Shot 2021-12-31 at 2 57 20 PM" src="https://user-images.githubusercontent.com/91089401/147840710-13e977a0-9533-44ee-9ded-80439e49b3ea.png">

* Testing ensembles

<img width="998" alt="Screen Shot 2021-12-31 at 6 10 53 PM" src="https://user-images.githubusercontent.com/91089401/147842663-b397a837-df09-43f1-8ec7-151d97d6e395.png">

## Results
After testing seven different models, I found that the one with the best cross validation score was the Gradient Boosting Regressor with gridsearchCV. The average score (NMAE) for this model was -0.1791. This model could be useful as an extra input for estimates that reflect their project budget.
