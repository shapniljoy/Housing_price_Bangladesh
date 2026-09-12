# Bangladesh Housing Price Prediction

## 🎯 Aim of the Project
The primary goal of this project is to accurately predict housing prices in Bangladesh based on various property features such as location, number of bedrooms and bathrooms, floor area, and property type. By building a robust predictive model, this project aims to empower buyers, sellers, and real estate professionals to make data-driven, informed decisions in the Bangladeshi real estate market.

## 📊 Process and Methodology

The project follows a structured, step-by-step methodology, with each phase documented in its respective Jupyter Notebook. Here is the detailed breakdown of the workflow:

### 1. Data Gathering & Cleaning
- **` (1) Data_Gathering.ipynb`**: The initial phase involves collecting raw housing data for Bangladesh.
- **` (2) Data_Cleaning.ipynb`**: The raw data (`house_price_bd.csv`) is cleaned to handle formatting issues, remove duplicates, and correct data entry errors, resulting in a cleaner dataset (`house_price_cleaned.csv`).

### 2. Feature Engineering & Exploratory Data Analysis (EDA)
- **` (3) Feature_Engineering.ipynb`**: New meaningful features are derived from the existing data to improve the predictive power of the models, saving the intermediate output as `feature_engineered.csv`.
- **` (4) EDA-1.ipynb`**: Initial exploratory data analysis is conducted to understand data distributions, correlations, and underlying patterns.

### 3. Data Preprocessing (Outliers & Missing Values)
- **` (5) Outliers.ipynb`**: Statistical methods are applied to detect and handle outliers in the dataset, ensuring robust model training.
- **` (6) EDA-2 & Missing_Imputations.ipynb`**: A deeper dive into the data structure, followed by advanced imputation techniques to handle missing values accurately. The processed data is stored as `final_data.csv`.

### 4. Feature Selection
- **` (7) Feature Selection.ipynb`**: Techniques are applied to select the most relevant and important features for the prediction task, reducing dimensionality and preventing overfitting.

### 5. Modeling & Evaluation
- **` (8) Model Selection.ipynb`**: Various baseline machine learning models are evaluated to identify the most promising algorithms for this specific dataset.
- **` (9) Gradient_Boosting.ipynb` & `(10) XGboost.ipynb`**: Ensemble methods are trained and fine-tuned to capture complex non-linear relationships.
- **` (11) SVR.ipynb`**: Support Vector Regression is trained and optimized. It ultimately proved to be the most effective algorithm and was exported as the final production model (`SVR_model.pkl`).

### 6. Finalization
- **` Final.ipynb`**: A consolidated notebook that brings together the best practices, the final dataset pipeline, and the final model inference steps.

## 💡 Key Insights from EDA
During the Exploratory Data Analysis phases, several interesting patterns emerged about the Bangladeshi housing market:
- **Standard Layouts**: There is a clear market standard; **78%** of the listed houses feature exactly **3 bedrooms**, and **63%** have **3 bathrooms**. The most common overall configuration is a 3-bed, 3-bath property.
- **Geographic Concentration**: The overwhelming majority of the listings are concentrated in **Dhaka** and **Chattogram**. Within Dhaka, **Mirpur** holds the highest number of available residential properties.
- **Pricing Disparities**: Location plays a massive role in property valuation. **Dhaka** exhibits a higher median price than all other regions combined. On the other end of the spectrum, **Gazipur** holds the lowest median housing price.
- **Distribution Traits**: Important features like *Floor Area* and *Price* are heavily right-skewed with extreme values (e.g., luxury or commercial flats), necessitating log transformations for robust model training. Furthermore, high-rise buildings exhibit a non-linear relationship between total price and price-per-square-foot compared to lower-level floors.

## 🏆 Predictive Modeling Results
After evaluating multiple algorithms (including Random Forest, Gradient Boosting, and XGBoost), **Support Vector Regression (SVR)** using a polynomial kernel was selected as the final model through hyperparameter tuning with Optuna. 

The final SVR model achieved the following performance metrics on the test set:
- **R² Score**: `0.8919` (~89.2% of the variance in housing prices is successfully explained by the model)
- **Mean Absolute Error (MAE)**: `0.1416`
- **Mean Squared Error (MSE)**: `0.0529`


