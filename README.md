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
