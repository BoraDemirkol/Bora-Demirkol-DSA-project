# Bora-Demirkol-DSA-project

/* Calorie Burn Prediction Based on Exercise Types

## Motivation: 

Accurately estimating calorie expenditure during exercise can help individuals optimize their workout plans and achieve their fitness goals. However, most fitness applications and devices use generalized calorie estimation formulas rather than personalized predictions. This project aims to develop a machine learning-based model that can provide more accurate calorie burn predictions based on different exercise types.

I personally work out four times a week, and when I first started training, I struggled to find the right program for myself. Most workout plans and fitness applications provide generic calorie burn estimations without considering individual factors such as weight, age, gender, or workout intensity. Because of this, I often found myself uncertain about which exercises were the most efficient for my specific goals.

This project is motivated by my own experience of trying to optimize my workouts and help others personalize their exercise routines by providing data-driven calorie burn predictions. The goal is to analyze how factors such as age, weight, gender, workout duration, and exercise type influence calorie burn and build a model that can offer customized insights for users.
## Data Source:

1. Kaggle dataset on exercise and calorie burn it includes different parameters like ages, heights, weights, exercise duration, heart rate and body temperature.
2. Personal data from the apple watch (apple health)

## Exploratory Data Analysis (EDA):

There is a linear reggression between calories and duration , heart_rate and calories also body temperature and calories. 
![image](https://github.com/user-attachments/assets/e41706ed-bbe3-4a28-8cfd-eebb3e99f44c)
![image](https://github.com/user-attachments/assets/ed20832d-84b4-4962-aa46-0457cdba0442)
![image](https://github.com/user-attachments/assets/55c33582-02f7-440f-9930-4b8fa7b3521f)


## Feature Selection & Data Preprocessing:

Height and Weight: Used to calculate BMI and analyze the body composition. 

Age: Metabolism slows with age, impacting calorie burning. 

Workout Duration: Longer workouts generally burn more calories. 

Heart Rate: Higher heart rate indicates higher exertion levels.

Body Temperature: Higher temperatures might indicate more intense workouts.

![image](https://github.com/user-attachments/assets/3496cbea-644c-47b6-8fcd-2049f52e17ab)


## Machine Learning Models:

Since I have not covered machine learning in class yet, I plan to first complete the initial data analysis and gain a better understanding of the dataset. 
Once I learn the necessary machine learning techniques, I will implement them later in the project.

## Findings (Expected Outcomes):


## This project aims to answer the following key questions:

- Which exercise type burns the most calories on average?
  
- How do weight, age, and gender affect calorie burn?

- Can we create a model predict calorie burn according to data
  
## Limitations:

- Measuring actual calorie burn requires laboratory-grade equipment.
  
- Personal data collection may have inaccuracies (e.g., fitness trackers may not be 100% accurate in calorie estimations).

## Future Work

- Include more exercise types, such as yoga, HIIT, and weight training.
  
- Improve accuracy by integrating heart rate and oxygen consumption (VO2 max) data.
  
- Develop a real-time prediction system as a mobile or web application.

In conclusion, this project aims to provide a more accurate and personalized approach to estimating calorie burn, helping individuals optimize their workout plans. */
