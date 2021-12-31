# Forecasting Video Game Sales
Continuing the project that I did previously (https://github.com/ryansxiong/Video_Game_Sales_ds_proj) and creating a model to forecast the data's sales.

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

