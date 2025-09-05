#  **California HousePrice Prediction**

![GitHub](https://img.shields.io/badge/GitHub-Repo-black?logo=github&style=for-the-badge)

------------------------------------------------------------------------------------------

## The Problem

- Realm of Real Estate is highly dependent on estimation of property prices , both property owners and real estate agents are required to have a good estimation for getting the best deal for the property they own or the property they wanna buy.
- In this problem we deal with creating a robust machine learning model for house prices prediction for California with a satisfactory precision.

--------------------------------------------------------------------------------------------

## Understanding The Data

- You can download the dataset from Kaggle
[Housing Data](https://www.kaggle.com/datasets/camnugent/california-housing-prices)
- Import the data
  
  ```python
  import pandas as pd
  
  def load_housing_data(housing_path=HOUSING_PATH): #Path to your dataset
      csv_path = os.path.join(housing_path, "housing.csv")
      return pd.read_csv(csv_path)
  ```
- Load and Eyeball the data
  
  ```python
  df = load_housing_data()
  df.head()
  ```

| longitude | latitude | housing_median_age | total_rooms | total_bedrooms | population | households | median_income | median_house_value | ocean_proximity |
|-----------|----------|---------------------|-------------|----------------|------------|------------|----------------|---------------------|-----------------|
| -122.23   | 37.88    | 41.0                | 880.0       | 129.0          | 322.0      | 126.0      | 8.3252         | 452600.0            | NEAR BAY        |
| -122.22   | 37.86    | 21.0                | 7099.0      | 1106.0         | 2401.0     | 1138.0     | 8.3014         | 358500.0            | NEAR BAY        |
| -122.24   | 37.85    | 52.0                | 1467.0      | 190.0          | 496.0      | 177.0      | 7.2574         | 352100.0            | NEAR BAY        |
| -122.25   | 37.85    | 52.0                | 1274.0      | 235.0          | 558.0      | 219.0      | 5.6431         | 341300.0            | NEAR BAY        |
| -122.25   | 37.85    | 52.0                | 1627.0      | 280.0          | 565.0      | 259.0      | 3.8462         | 342200.0            | NEAR BAY        |

- To get detailed info about the data we can do
  
  ```python
  df.info()
  ```

**Shape:** `20640 rows × 10 columns`  
**Memory Usage:** ~1.6 MB  


| # | Column              | Non-Null Count | Dtype   | Description |
|---|---------------------|----------------|---------|-------------|
| 0 | longitude           | 20640 non-null | float64 | Geographic coordinate (West is negative) |
| 1 | latitude            | 20640 non-null | float64 | Geographic coordinate (North is positive) |
| 2 | housing_median_age  | 20640 non-null | float64 | Median age of houses in the block |
| 3 | total_rooms         | 20640 non-null | float64 | Total number of rooms in the block |
| 4 | total_bedrooms      | 20433 non-null | float64 | Total number of bedrooms in the block |
| 5 | population          | 20640 non-null | float64 | Population in the block |
| 6 | households          | 20640 non-null | float64 | Number of households in the block |
| 7 | median_income       | 20640 non-null | float64 | Median income of households (scaled) |
| 8 | median_house_value  | 20640 non-null | float64 | Median house value (target variable) |
| 9 | ocean_proximity     | 20640 non-null | object  | Proximity to ocean (categorical feature) |

