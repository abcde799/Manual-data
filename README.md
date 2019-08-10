# Manual-data

This project takes a look at the used US manual transmission car market around the beginning of July 2019. The questions addressed are:

(I) Which cities have the most manual cars? and

(II) What are the top six best used manual car models in terms of value, and what are the top six cheapest models?

To address these questions the libraries numpy, pandas, and sci-kit learn were used. The relevant data was scraped from a popular car website using BeautifulSoup and the lxml parser. Further explanation of (I) and (II) is included in markdown cells in the relevant notebook.

## Contents:

In this repo are included the following contents:

-Three IPython notebooks:

  (i) 'used_manual_trans_car_market_july_2019': This is contains all the code for the main project which is addressing (I) and (II) above.
  
  (ii) 'saving_web_pages_locally': This contains code for saving webpages locally from the relevant website using BeautifulSoup.
  
  (iii) 'scrape_locally_saved_web_pages': This contains code for scraping locally saved webpages using the lxml parser, and putting all of the data into one big pandas dataframe.
  
  -One csv file, 'true_car_manual_transmission_07_2_2019': 
  This is the file which was ultimately made from scraping the relevant website. 
  
  ## Methods: Data preprocessing, standardization, regularized lasso regression, modes
  
  The technique used for (I) and (II) is measuring feature importance via ranking of lasso regression coefficients. The target variable is the car price, and the predictors (features) are age, mileage, and one hot encoded car model variables. This is done after preprocessing the data and standardizing it. The optimal lasso regularization parameter was obtained from a five fold cross validation conducted on a training set, and then the model was tested on a testing set. 
  
  Once the car models are ranked by their regression coefficients a ranked list is generated. This list is then intersected with the most commonly occurring car models (to avoid models which are too rare to be of interest), giving us what we sought to find. A decision tree regression is also run as an alternative way to measure feature importance, but not for the purpose of ranking. Lastly, some inspection of the residuals is given, which shows they are close to normally distributed. The final results are given at the very end of the 'used_manual_trans_car_market_july_2019' notebook.  



