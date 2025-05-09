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

Since I have not covered machine learning in class yet, I plan to first complete the initial data analysis and gain a better understanding of the dataset. 

Once I learn the necessary machine learning techniques, I will implement them later in the project. 

Additionally, I plan to develop an interactive web-based tool using Gradio, which will allow users to input their workout details (e.g., duration, heart rate, body temperature) and receive a real-time estimated calorie burn prediction from the trained model.

This will help demonstrate the practical use of machine learning in fitness applications and allow for user feedback to improve the model further.

## Findings (Expected Outcomes):

## This project aims to answer the following key questions:

- Which exercise type burns the most calories on average?
  
- How do weight, age, and gender affect calorie burn?

- Can we develop a model that accurately predicts calorie burn based on workout data?
   
## Limitations:

- Measuring actual calorie burn requires laboratory-grade equipment.
  
- Personal data collection may have inaccuracies (e.g., fitness trackers may not be 100% accurate in calorie estimations).

## Future Work

- Include more exercise types, such as yoga, HIIT, and weight training.
  
- Improve accuracy by integrating heart rate and oxygen consumption (VO2 max) data.
  
- Develop a real-time prediction system as a mobile or web application.

In conclusion, this project aims to provide a more accurate and personalized approach to estimating calorie burn, helping individuals optimize their workout plans. */
