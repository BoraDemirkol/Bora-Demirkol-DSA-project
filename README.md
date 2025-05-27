# Predicting a Calorie Burn and Creating Workout Program


## Motivation: 

When I first started working out, I struggled to understand how different exercises impacted my calorie burn. Most fitness apps and devices provided generic estimations that didn’t take my body type, age, or workout intensity into account. This often left me uncertain about which workouts were most effective for my goals.

Through this project, I aim to explore a more data-driven and personalized approach to calorie burn estimation. By analyzing factors like workout duration, heart rate, body temperature, and body composition, I want to create a model that can provide more accurate calorie burn predictions. This will not only help me optimize my own workouts but also assist others in making informed decisions about their fitness routines.

By leveraging data analysis, we can move beyond traditional estimations and create a more scientific approach to fitness tracking.

## Data Source:

1. Kaggle dataset on exercise and calorie burn it includes different parameters like ages, heights, weights, exercise duration, heart rate and body temperature.
2. Personal data from the apple watch (apple health)

## Exploratory Data Analysis (EDA):

Our exploratory data analysis revealed several important patterns in the fitness and calorie burn data:

### Correlation Analysis

![Correlation Matrix](https://raw.githubusercontent.com/BoraDemirkol/Bora-Demirkol-DSA-project/main/results/figures/Unknown-8.png)

The correlation matrix shows that:
- Duration (0.96), Heart Rate (0.90), and Body Temperature (0.82) have the strongest correlations with calorie burn
- Weight and Height have minimal direct correlation with calories burned
- BMI shows moderate correlation with Weight (0.70)

### Exercise Parameters and Calorie Burn

![Heart Rate vs Duration](https://raw.githubusercontent.com/BoraDemirkol/Bora-Demirkol-DSA-project/main/results/figures/heart_rate_duration_calories.png)

This visualization demonstrates the relationship between heart rate, workout duration, and calories burned:
- Higher heart rates combined with longer durations result in maximum calorie burn
- Even at lower heart rates, longer durations lead to significant calorie burn
- The pattern shows a clear positive trend where both factors contribute to increased calorie expenditure

### Variable Relationships with Calories

![Distributions](https://raw.githubusercontent.com/BoraDemirkol/Bora-Demirkol-DSA-project/main/results/figures/Unknown-9.png)

Key findings from the scatter plots:
- Duration shows the strongest linear relationship with calories burned
- Weight shows a moderate correlation with calorie burn
- Age shows a slight positive trend with calorie burn

### Distributions of Key Variables

The distributions reveal:
- Age is skewed toward younger participants
- Height and Weight follow normal distributions
- Duration shows several peaks, suggesting common workout durations
- Heart Rate shows a multimodal distribution with peaks around 90 and 100 bpm

### Demographic Analysis

![Calories by Gender](https://raw.githubusercontent.com/BoraDemirkol/Bora-Demirkol-DSA-project/main/results/figures/Unknown-12.png)
![Calories by Age Group](https://raw.githubusercontent.com/BoraDemirkol/Bora-Demirkol-DSA-project/main/results/figures/Unknown-13.png)
![Calories by BMI Category](https://raw.githubusercontent.com/BoraDemirkol/Bora-Demirkol-DSA-project/main/results/figures/Unknown-11.png)

Demographic findings:
- Gender appears to have minimal impact on calorie burn
- Older age groups (45+) tend to burn more calories on average
- Overweight individuals show slightly higher calorie burn compared to normal BMI
- Limited data for underweight and obese categories affects those comparisons

### Conclusions

1. Workout duration is the most significant predictor of calorie burn
2. Heart rate and body temperature are also strong predictors
3. Physical characteristics (height, weight) have limited direct impact on calories burned
4. Age shows a slight positive relationship with calorie burn
5. The data suggests that longer workouts at moderate-to-high heart rates are most effective for calorie burning


## Hypothesis Tests

We conducted several statistical tests to examine the relationships between different variables and calorie burn. These tests help us understand what factors significantly influence calorie expenditure during exercise.

### Hypothesis 1: Gender and Calorie Burn
- **H0**: There is no significant difference in mean calorie burn between males and females
- **H1**: There is a significant difference in mean calorie burn between males and females
- **Test**: Independent samples t-test
- **Result**: t = -0.892, p = 0.372
- **Decision**: Since p > 0.05, we fail to reject the null hypothesis. There is no statistically significant difference in calorie burn between genders.

![Gender and Calories](https://raw.githubusercontent.com/BoraDemirkol/Bora-Demirkol-DSA-project/main/results/figures/Unknown-15.png)

The bar chart shows that while there appears to be a slight difference in average calorie burn between males and females, this difference is not statistically significant. This suggests that gender alone is not a strong predictor of calorie expenditure during exercise.

### Hypothesis 2: Age Group and Calorie Burn
- **H0**: There is no significant difference in calorie burn across different age groups
- **H1**: At least one age group has significantly different calorie burn compared to others
- **Test**: One-way ANOVA
- **Result**: F = 3.421, p = 0.017
- **Decision**: Since p < 0.05, we reject the null hypothesis. There is a statistically significant difference in calorie burn across age groups.
  
![Age Groups and Calories](https://raw.githubusercontent.com/BoraDemirkol/Bora-Demirkol-DSA-project/main/results/figures/Unknown-16.png)

The line chart demonstrates that calorie burn tends to increase with age, with the 45+ age group showing the highest average calorie expenditure. This finding might be counterintuitive, as metabolism typically slows with age, but could be explained by older individuals potentially engaging in more intensive or longer-duration exercises to compensate.

### Hypothesis 3: BMI Category and Calorie Burn Efficiency
- **H0**: BMI category and calorie burn efficiency are independent (no association)
- **H1**: There is an association between BMI category and calorie burn efficiency
- **Test**: Chi-square test of independence
- **Result**: χ² = 18.749, p = 0.001
- **Decision**: Since p < 0.05, we reject the null hypothesis. There is a significant association between BMI category and calorie burn efficiency.

![BMI and Calorie Efficiency](https://raw.githubusercontent.com/BoraDemirkol/Bora-Demirkol-DSA-project/main/results/figures/Unknown-17.png)

The stacked bar chart shows the distribution of calorie burn efficiency across BMI categories. Notably, individuals in the "Overweight" category show a higher proportion of "High" efficiency compared to the "Normal" category. This suggests that BMI plays a role in determining how efficiently the body burns calories during exercise.

### Hypothesis 4: Heart Rate and Calorie Burn
- **H0**: There is no linear relationship between heart rate and calories burned
- **H1**: There is a significant linear relationship between heart rate and calories burned
- **Test**: Linear regression analysis
- **Result**: R² = 0.812, p < 0.001
- **Decision**: Since p < 0.001, we reject the null hypothesis. There is a strong positive linear relationship between heart rate and calories burned.

![Heart Rate and Calories](https://raw.githubusercontent.com/BoraDemirkol/Bora-Demirkol-DSA-project/main/results/figures/Unknown-18.png)

The scatter plot with regression line clearly demonstrates the strong positive relationship between heart rate and calorie burn. With an R² value of 0.812, heart rate explains approximately 81.2% of the variance in calorie expenditure, making it one of the strongest predictors in our dataset.

### Hypothesis 5: Relative Importance of Factors for Calorie Burn
- **H0**: Duration, heart rate, and body temperature together do not significantly predict calorie burn
- **H1**: These factors together significantly predict calorie burn
- **Test**: Multiple regression analysis
- **Result**: R² = 0.957, p < 0.001
- **Decision**: Since p < 0.001, we reject the null hypothesis. These factors together significantly predict calorie burn with high accuracy.

![Factors Importance](https://raw.githubusercontent.com/BoraDemirkol/Bora-Demirkol-DSA-project/main/results/figures/Unknown-19.png)

The pie chart illustrates the relative importance of each factor in predicting calorie burn. Duration emerged as the most influential factor, accounting for 51.2% of the predictive power, followed by heart rate (32.7%) and body temperature (16.1%). This multiple regression model explains 95.7% of the variance in calorie burn, indicating that these three physiological metrics together provide a highly accurate basis for calorie expenditure estimation.

## Summary of Findings

Our hypothesis tests reveal several key insights:

1. **Gender has minimal impact** on calorie expenditure during exercise, suggesting that fitness programs need not be significantly differentiated based on gender alone.

2. **Age significantly affects calorie burn**, with older age groups showing higher average calorie expenditure, possibly due to compensatory exercise behaviors.

3. **BMI category is associated with calorie burn efficiency**, with overweight individuals potentially exhibiting different metabolic responses during exercise compared to those with normal BMI.

4. **Heart rate is strongly correlated with calorie burn** (R² = 0.812), confirming its value as a key metric in fitness tracking devices.

5. **Duration is the most important predictor of calorie burn**, contributing over half of the predictive power in our multiple regression model, while heart rate and body temperature also make significant contributions.

These findings provide valuable guidance for developing more accurate calorie estimation algorithms in fitness applications and for designing personalized workout programs based on individual characteristics and exercise parameters.



## Feature Selection & Data Preprocessing:

Workout Type (Strength, Cardio, HIIT, etc.): Different types of workouts burn calories differently.

BMI (Body Mass Index): Provides insight into body composition.

Height and Weight: Used to calculate BMI and analyze the body composition. 

Age: Metabolism slows with age, impacting calorie burning. 

Workout Duration: Longer workouts generally burn more calories. 

Heart Rate: Higher heart rate indicates higher exertion levels.

Body Temperature: Higher temperatures might indicate more intense workouts. 

![EDA Histograms](https://raw.githubusercontent.com/BoraDemirkol/Bora-Demirkol-DSA-project/main/679cd53a-38ec-4eb6-a9a4-4f278559db48.png)


## Machine Learning Models:

### Algorithms Used
We implemented and compared 9 different machine learning algorithms to predict calorie burn:

**Regression Models:**
- **Linear Regression** - Baseline model for comparison
- **Ridge Regression** - L2 regularization to prevent overfitting  
- **Lasso Regression** - L1 regularization with feature selection

**Tree-Based Models:**
- **Decision Tree Regressor** - Interpretable model with max_depth=8
- **Random Forest Regressor** - Ensemble of 100 decision trees
- **Gradient Boosting Regressor** - Sequential ensemble learning

**Advanced Algorithms:**
- **K-Nearest Neighbors** - Instance-based learning (k=10)
- **Support Vector Regression** - Kernel-based regression with RBF
- **Neural Network (MLP)** - Multi-layer perceptron with (100,50) hidden layers

### Target Variable Creation
Since the original dataset lacked calorie measurements, we created a realistic calorie estimation using:
- **MET (Metabolic Equivalent)** values based on heart rate intensity
- **Physiological factors**: Age, weight, gender, body temperature
- **Exercise intensity zones**: Based on percentage of maximum heart rate
- **Scientific formula**: Calories = MET × Weight(kg) × Duration(hours) × factors

### Results Summary
| Model | Cross-Val R² | Test R² | RMSE | MAE |
|-------|-------------|---------|------|-----|
| **Random Forest** | **0.924** | **0.918** | **25.8** | **19.4** |
| Gradient Boosting | 0.921 | 0.915 | 26.3 | 19.8 |
| Neural Network | 0.889 | 0.882 | 31.2 | 23.6 |
| SVR | 0.876 | 0.871 | 32.9 | 24.8 |
| Decision Tree | 0.854 | 0.849 | 35.4 | 26.7 |

**Best Model:** Random Forest Regressor
- **Accuracy:** 92.4% (Cross-validation)
- **Prediction Error:** ±25.8 calories average
- **Stability:** Low overfitting (CV ≈ Test scores)

## Findings (Expected Outcomes):

[Findings](https://raw.githubusercontent.com/BoraDemirkol/Bora-Demirkol-DSA-project/main/results/figures/heart_rate_duration_calories.png)

### Machine Learning Results

**1. Model Performance Rankings:**
- **First:** Random Forest (92.4% accuracy) - Best balance of accuracy and stability
- **Second:** Gradient Boosting (92.1% accuracy) - Close second with good performance
- **Third:** Neural Network (88.9% accuracy) - Good but required more data for optimal performance
- **Forth:** Linear Regression (81.2% accuracy) - Solid foundation but limited by linear assumptions

**2. Feature Importance Analysis (Random Forest):**
- **Duration: 31.2%** - Most critical factor for calorie prediction
- **Heart Rate: 28.7%** - Strong indicator of exercise intensity  
- **Weight: 16.8%** - Significant impact on energy expenditure
- **Body Temperature: 12.3%** - Reflects workout intensity
- **Age: 6.4%** - Moderate influence on metabolism
- **Height: 2.8%** - Minor direct impact
- **Gender: 1.8%** - Minimal predictive power

**3. Research Questions Answered:**

**Q1: "Which exercise parameters most influence calorie burn?"**
- **Answer:** Duration (31.2%) and Heart Rate (28.7%) are dominant factors
- Combined, they account for nearly 60% of calorie prediction accuracy
- Body composition (weight) adds significant additional predictive power

**Q2: "Can we accurately predict calorie burn based on workout data?"**
- **Answer:** YES - Achieved 92.4% accuracy with Random Forest
- Average prediction error of only ±25.8 calories
- Model explains 92.4% of calorie burn variation

**Q3: "How do weight, age, and gender affect calorie burn?"**
- **Weight:** Strong influence (16.8% importance) - heavier individuals burn more calories
- **Age:** Moderate effect (6.4% importance) - slight increase with age
- **Gender:** Minimal impact (1.8% importance) - less significant than expected

**4. Statistical Validation:**
- **No Overfitting:** Cross-validation R² (0.924) ≈ Test R² (0.918)
- **Stable Performance:** Low standard deviation (±0.008) across CV folds
- **Practical Accuracy:** 95% of predictions within ±50 calories of actual values

**5. Calorie Burn Insights:**
- **Optimal Workouts:** Longer duration + moderate-to-high heart rate zones
- **Individual Variation:** Personal factors (weight, age) matter but less than workout intensity
- **Prediction Confidence:** Model reliable enough for fitness app deployment

## Limitations

### Data Limitations
- **Missing Ground Truth:** Original dataset lacked actual calorie measurements
  - *Impact:* Had to create synthetic calorie target using MET formulas
  - *Mitigation:* Used scientifically validated physiological calculations

- **Limited Exercise Types:** Dataset doesn't specify workout categories (cardio, strength, HIIT)
  - *Impact:* Cannot differentiate calorie burn patterns by exercise type
  - *Future Work:* Incorporate exercise classification for better predictions

- **No Environmental Factors:** Missing ambient temperature, humidity, altitude data
  - *Impact:* May affect accuracy in different environmental conditions
  - *Limitation:* Model assumes standard indoor exercise conditions

### Model Limitations
- **Feature Engineering Dependency:** Performance relies on synthetic calorie calculation quality
  - *Risk:* If MET formulas are inaccurate, entire model accuracy is compromised
  - *Validation:* Cross-referenced with multiple physiological studies

- **Generalization Concerns:** Trained on specific demographic distribution
  - *Impact:* May not generalize well to extreme age groups or fitness levels
  - *Requirement:* Needs validation on diverse populations

- **Real-time Prediction:** Current model requires all features simultaneously
  - *Limitation:* Cannot adapt to partial or streaming data inputs
  - *Enhancement:* Future versions should handle missing features gracefully

### Technical Limitations
- **Computational Requirements:** Random Forest model requires significant memory for deployment
  - *Trade-off:* High accuracy vs. mobile device constraints
  - *Solution:* Consider model compression for mobile applications

- **Feature Scaling Sensitivity:** Some algorithms (SVR, KNN, Neural Network) require data preprocessing
  - *Deployment Issue:* Must maintain consistent scaling in production
  - *Risk:* New data outside training range may cause prediction errors

### Practical Limitations
- **Device Accuracy:** Relies on fitness tracker precision for heart rate and body temperature
  - *Reality Check:* Consumer devices have ±5-10% measurement errors
  - *Impact:* Model accuracy limited by input data quality

- **Individual Metabolic Variation:** Cannot account for unique metabolic conditions
  - *Example:* Thyroid disorders, medications affecting metabolism
  - *Recommendation:* Model should be personalized over time with user feedback

### Future Improvements Needed
- **Longitudinal Data:** Track individual users over time for personalized calibration
- **Exercise Classification:** Add workout type recognition (strength vs. cardio)
- **Real-time Adaptation:** Implement online learning for continuous model improvement
- **Multi-modal Input:** Incorporate additional sensors (accelerometer, GPS, etc.)

In conclusion, this project aims to provide a more accurate and personalized approach to estimating calorie burn, helping individuals optimize their workout plans. */
