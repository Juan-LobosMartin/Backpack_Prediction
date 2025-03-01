# Analysis of Backpack Price Prediction Challenge: Evidence of Randomly Generated Data 

Kaggle Playground Series - Season 5, Episode 2
[Walter Reade and Elizabeth Park. Backpack Prediction Challenge, 2025. Kaggle.]( https://kaggle.com/competitions/playground-series-s5e2)

**Executive Summary:**

This report details an investigation into the "Backpack Prediction Challenge" dataset, aimed at predicting backpack prices using various features. Analysis revealed a significant anomaly: backpack prices appear to be randomly distributed, with no discernible correlation to provided features (brand, material, size, style, color, compartments, weight capacity, waterproof, laptop compartment). Despite employing multiple regression models (linear regression, XGBoost, KNN), consistent Root Mean Squared Error (RMSE) values around 39 were observed, indicating a lack of predictive power. This aligns with the dataset creator's confirmation that the data was generated using a simple random process, rendering it unsuitable for meaningful predictive modeling.
![Price Vs Weight](Fig/All_Price_Weight.png)
*Figure 1: Price Vs Weight (hue= Brands) [^1]*

[^1]:All the backpacks in a scatter figure of Price Vs Weight Capacity, with hue representing the Brands.


**1. Introduction:**

The "Backpack Prediction Challenge" presented a dataset with 300,000 training and 200,000 test entries, featuring categorical, boolean, and numerical attributes of backpacks. The objective was to predict the 'Price' variable using these features.

**2. Data Exploration and Initial Observations:**

* **Price Distribution:** Initial exploration revealed a limited price range (15-150) with an unusual uniformity across categories like 'Size' (small, medium, large). Violin plots confirmed a consistent price distribution across these categories.
![Price Vs Weight](Fig/Violin_Price_sice.png)

* **Feature Analysis:** Scatter plots of 'Price' against numerical features (Compartments, Weight Capacity) and categorical features (Brand, Material, Color) showed a uniform, scattered distribution, suggesting no clear relationships.

* **Histogram Analysis:** Histograms of 'Price' segmented by boolean features (Waterproof, Laptop Compartment) also demonstrated a lack of distinct patterns.

**3. Model Evaluation and Results:**

* Multiple regression models were implemented:
    * Linear Regression: RMSE = 38.94273
    * XGBoost Regression: RMSE = 38.92103
    * KNN Regression: RMSE = 38.94863
* All models produced similar, high RMSE values, approximately 39.
* Given the price range of 135, an RMSE of 39 indicates that the model's error is roughly half of the entire possible price range, effectively rendering the predictions meaningless.
* The best score on the competition was 38.80756, indicating that everyone was having the same problem.

**4. Visual Evidence:**

* Scatter plots of 'Price' vs. 'Weight Capacity' (segmented by Brand, Material, Color) showed a uniform distribution across the entire price range, lacking any discernible clusters or trends.
* Histograms of price vs the boolean values showed very similar distributions.

**5. Interpretation and Conclusion:**

* The consistent, high RMSE values across various models, combined with the uniform distribution of 'Price' across all features, strongly suggests that the data is randomly generated.
* This conclusion is supported by the dataset creator's confirmation that the data was produced using a simple random generation process.
* Therefore, the dataset is not suitable for predictive modeling.
* The data set is not usefull for predictive analysis.
* It is important that data sets are generated with real world relationships in mind.

**6. Recommendations:**

* For future challenges, ensure that datasets are generated or curated to reflect real-world relationships and dependencies.
* When encountering unexpected results, thoroughly investigate the data generation process.
* When a competition is made, it is important to test the data set before the competition, to guarantee that the data set has valid relationships.
