# Bora-Demirkol-DSA-project

/* Calorie Burn Prediction Based on Exercise Types

## Motivation: 

When I first started working out, I struggled to understand how different exercises impacted my calorie burn. Most fitness apps and devices provided generic estimations that didn’t take my body type, age, or workout intensity into account. This often left me uncertain about which workouts were most effective for my goals.

Through this project, I aim to explore a more data-driven and personalized approach to calorie burn estimation. By analyzing factors like workout duration, heart rate, body temperature, and body composition, I want to create a model that can provide more accurate calorie burn predictions. This will not only help me optimize my own workouts but also assist others in making informed decisions about their fitness routines.

By leveraging data analysis, we can move beyond traditional estimations and create a more scientific approach to fitness tracking.

## Data Source:

1. Kaggle dataset on exercise and calorie burn it includes different parameters like ages, heights, weights, exercise duration, heart rate and body temperature.
2. Personal data from the apple watch (apple health)

## Exploratory Data Analysis (EDA):

Based on the initial EDA: 

Workout Duration and Calories Burned show a strong positive correlation.

![image](https://github.com/user-attachments/assets/e41706ed-bbe3-4a28-8cfd-eebb3e99f44c)

Heart Rate and Calories Burned also show a significant relationship, suggesting higher heart rate means more calorie burn.

![image](https://github.com/user-attachments/assets/ed20832d-84b4-4962-aa46-0457cdba0442)

Body Temperature and Calories Burned may have a non-linear relationship, as extreme temperatures might indicate overheating rather than increased calorie burn.

![image](https://github.com/user-attachments/assets/55c33582-02f7-440f-9930-4b8fa7b3521f)


## Feature Selection & Data Preprocessing:

Workout Type (Strength, Cardio, HIIT, etc.): Different types of workouts burn calories differently.

BMI (Body Mass Index): Provides insight into body composition.

Height and Weight: Used to calculate BMI and analyze the body composition. 

Age: Metabolism slows with age, impacting calorie burning. 

Workout Duration: Longer workouts generally burn more calories. 

Heart Rate: Higher heart rate indicates higher exertion levels.

Body Temperature: Higher temperatures might indicate more intense workouts. 

![image](https://github.com/user-attachments/assets/3496cbea-644c-47b6-8fcd-2049f52e17ab)


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
