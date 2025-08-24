# City-311-Insights-Challenge
<img width="642" height="135" alt="image" src="https://github.com/user-attachments/assets/3dd5a123-cae0-4e00-a02c-35e2295a6f04" />
<img width="1848" height="620" alt="image" src="https://github.com/user-attachments/assets/5b14d39a-8584-4e6a-8e0d-ffeab36f7c7e" />

## Overview
 This project focuses on analyzing 311 service request data to uncover insights and patterns that can help improve city services and urban planning. The goal is to extract meaningful insights, such as identifying high-frequency complaint types, spatial and temporal trends, and potential correlations with external factors like demographics or infrastructure.
## Update
This project won the 1st price in the hackerthon. 
 <img width="1900" height="1375" alt="hackerthon award" src="https://github.com/user-attachments/assets/acc31461-8ced-4c1e-916a-b566a0c3bb13" />


## Project Description
The City-311-Insights-Challenge aims to leverage data science techniques to process and analyze 311 service request datasets. 
## Time series analysis
It predicts future call volumes using multiple tree-based ML models: **XGB regressor, Random Forest, Catboost regressor, LightGBM and Linear Regressor**. 
Before choosin a model, in order to understand the dataset, EDA is done. To capture the important seasonal features, seasonal patterns and periodogram were used. To recognize the relation between the features, correlation matrix were calculated. 
<img width="1485" height="735" alt="image" src="https://github.com/user-attachments/assets/0ec911b5-b7de-4e44-99cd-6315c515658b" />
<img width="716" height="624" alt="image" src="https://github.com/user-attachments/assets/a17920b8-97c3-427a-80a1-bdc2dde305de" />

The best performing model is selected using MSE, R-MSE and MAPE score, and later optimized using data optimization methods, such as log-transformation and winsorization, and feature selection using **time importance**.
<img width="1043" height="563" alt="image" src="https://github.com/user-attachments/assets/a9bd5150-73ff-49d4-867e-b20045a1f39e" />

## Anomaly Detection 
Detecting anomaly is performed using statistical methods to filter out the irregular months. The top 10% anomaly values are replaced using the mean scores of normal months, balancing the dataset. Later, the model is retrained using the adjusted dataset, improving the final performace by 10%. 
<img width="1566" height="512" alt="image" src="https://github.com/user-attachments/assets/3b2a8025-6469-499d-b0d1-c522af3bf859" />

# Data visualziation 
More detailed data visualization is performed on Power BI dashboard. This helps recognize additional points which we failed to cover in the notebook. For example, irregularities in data entry such as the closing date being earlier than the opening date. 
<img width="1219" height="728" alt="Screenshot 2025-08-21 144926" src="https://github.com/user-attachments/assets/a722ff5e-4b0b-4d10-bfb7-9a1ed1792bed" />




## Repository Structure
- **/data**: Due to the large size, the datasets are not uploaded here. 
- **submission.ipynb**: Jupyter notebooks with exploratory data analysis, visualizations, and model development.
- **submission.csv**
- **anomalies.csv** 
- **requirements.txt**
- **documentation.txt**
- **dashboard.pbix** : The file is too large, please check it [here](https://drive.google.com/file/d/1LhC9c2qH8AR0-mKx39i3FPPYD9uBgP8X/view?usp=sharing)
- [**Video demo**](https://drive.google.com/file/d/14U43gzWZZ6PYs7vOT1VAhWfcVDHBRuI3/view?usp=sharing)

## Getting Started
### Prerequisites
- Python 3.10
- Libraries:(install via `requirements.txt`)
- Jupyter Notebook (optional, for running `.ipynb` files)

### Installation

   ```bash
   git clone https://github.com/chaw-thiri/City-311-Insights-Challenge.git
   cd City-311-Insights-Challenge

   # set up environment
   python -m venv .venv
   source .venv/bin/activate # On Windows, use `.venv\Scripts\activate`
   # install dependencies     
   pip install -r requirements.txt
   jupyter notebook submission.ipynb
    
   ```
### Useful links
Link for data retrieval : [https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9/about_data](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9/about_data) 
   
