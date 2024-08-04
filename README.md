# lux-dsea_week1

This project provides a simple way to download datasets from Kaggle competitions and save them as CSV files. The data downloaded was used to answer the following questions using both python and SQL.
1. Find all records where the weather was exactly clear.
2. Find the number of times the wind speed was exactly 4 km/hr.
3. Check if there are any NULL values present in the dataset.
4. Rename the column "Weather" to "Weather_Condition."
5. What is the mean visibility of the dataset?
6. Find the number of records where the wind speed is greater than 24 km/hr and visibility is equal to 25 km.
7. What is the mean value of each column for each weather condition?
8. Find all instances where the weather is clear and the relative humidity is greater than 50, or visibility is above 40.
9. Find the number of weather conditions that include snow.

You can find the colab notebook used for this [here](https://colab.research.google.com/drive/1l97Nbkc255k7GMZ8OE5A_djXI9wzw57h?usp=sharing).

The dataset used for this project can be found on[Kaggle](https://www.kaggle.com/datasets/ayushmi77al/weather-data-set-for-beginners).


## Steps:

1. **Install Kaggle API:**

   ``` Python
   !pip install kaggle
   ```
2. **Set up Kaggle Credentials:**
   - Create a directory for your Kaggle API token:
   ``` Python
   ! mkdir ~/.kaggle
   ```

   - Upload your `kaggle.json` file (obtained from your Kaggle account settings) to Colab.
   - Copy the file to the created directory:
   ``` Python
   !cp kaggle.json ~/.kaggle/
   ```
  
   -  Set the correct file permissions:
  ``` Python
  !chmod 600 ~/.kaggle/kaggle.json
  ```
  
3. **Download Dataset:**
     
  ``` Python
! kaggle datasets download ayushmi77al/weather-data-set-for-beginners
  ```
  
4. **Extract Files:**
   - Our downloaded data is compressed so we need to extract it:
  ``` Python
!unzip /content/weather-data-set-for-beginners.zip
  ```
  
5. **Save as CSV:**
   - After answering the questions on python, we now save the data as a CSV:
  ``` Python
data.to_csv('my_data.csv', index=False)
  ```
  
6. **Download CSV:**
   - Download the CSV file to my local machine:
   ``` Python
   from google.colab import files
   files.download('my_data.csv')
   ```
