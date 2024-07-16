# Metabolic Health Risk Calculator

## Overview
The concept of having 3 out of 5 Metabolic Syndrome risk factors is a widely accepted criterion for diagnosing Metabolic Syndrome. Metabolic Syndrome is a cluster of conditions that occur together, increasing the risk of heart disease, stroke, and type 2 diabetes. The five risk factors include increased waist circumference, elevated triglycerides, reduced HDL cholesterol, elevated blood pressure, and elevated fasting glucose. In the Metabolic Syndrome algorithm BMI is not considered an independent risk factor.

This health risk calculator considers BMI status as a strong independent risk variable in conjunction with other well-established Metabolic Syndrome variables. The evidence supporting BMI as an independent health risk factor is extensive and robust. Elevated BMI is associated with a wide range of adverse health outcomes, including cardiovascular disease, type 2 diabetes, certain cancers, respiratory conditions, musculoskeletal disorders, and increased mortality. These associations are supported by both epidemiological data and biological mechanisms. Therefore, incorporating BMI as a significant variable in health risk assessments is well-justified.

Inclusion of BMI helps identify individuals at higher risk for developing cardiovascular diseases and type 2 diabetes. Currently, the diagnosis of Metabolic Syndrome is binary: if an individual has 3 or more of the 5 risk factors, they are diagnosed with Metabolic Syndrome. If they have fewer than 3 of the 5 risk factors, they are not diagnosed with Metabolic Syndrome. I have replaced this binary system with a risk score comprised of a scale from 0 to 18 with associated categorization. This enhances the prognostic value of the metrics regarding an individual developing serious health conditions, such as cardiovascular diseases (heart attack, stroke), type 2 diabetes, non-alcoholic fatty liver disease, and chronic kidney disease).

Additionally, inclusion of BMI in this algorithm contributes to proper calculations for younger individuals with high BMI status with none to minimal (other than positive Waist Circumference values) additional positive values. Without incorporating BMI status into calculations there is no acknowledgment of the high likelihood of additional risk factors developing over time. This is not statistically sound logic. In reality, younger individuals who maintain elevated BMI status do develop positive risk factors as a function of BMI status and associated physiology. Thus, the risk exists but is not currently acknowledged by the binary Metabolic Syndrome model.

The algorithm employed utilizes weighted scores for various metabolic risk factors to calculate an overall health risk score. Each positive risk factor contributes to the total score based on its severity.

## Algorithm
- **BMI Score**:
  - BMI >= 25 and Waist Circumference > 35 inches: +1 point
  - BMI >= 30 and Waist Circumference > 35 inches: +2 points
  - BMI >= 35 and Waist Circumference > 35 inches: +3 points
  - BMI >= 40 and Waist Circumference > 35 inches: +4 points

- **Waist Circumference Score for Males**:
  - Waist Circumference > 40 and <= 45 inches: +2 points
  - Waist Circumference > 45 and <= 50 inches: +3 points
  - Waist Circumference > 50 inches: +4 points

- **Waist Circumference Score for Females**:
  - Waist Circumference > 35 and <= 40 inches: +2 points
  - Waist Circumference > 40 and <= 45 inches: +3 points
  - Waist Circumference > 45 inches: +4 points

- **Triglycerides Score**:
  - Triglycerides >= 150 and < 250 mg/dL: +2 points
  - Triglycerides >= 250 and < 350 mg/dL: +3 points
  - Triglycerides >= 350 mg/dL: +4 points

- **Fasting Blood Glucose Score**:
  - Fasting Blood Glucose > 100 mg/dL: +1 point
  - Fasting Blood Glucose > 125 mg/dL: +2 points
  - Fasting Blood Glucose > 200 mg/dL: +4 points

- **HDL Cholesterol Score**:
  - For males: HDL < 40 mg/dL: +2 points
  - For females: HDL < 35 mg/dL: +2 points

- **High Blood Pressure Score**:
  - High Blood Pressure (diagnosed or being treated): +3 points

The total health risk score is calculated by summing the points from all these categories. This weighted scoring system allows for a nuanced assessment of metabolic health, where the presence and severity of each risk factor are taken into account to provide an overall risk evaluation. The algorithm ensures that higher risk factors contribute more significantly to the total score.

## User Input
This code block prompts the user to input specific health metrics and calculates an overall health risk score based on these inputs. The program starts by asking the user to enter their age, gender, BMI, waist circumference, triglyceride levels, fasting blood glucose levels, HDL cholesterol levels, and whether they have been diagnosed with or are being treated for high blood pressure (by entering 1 if they have or 0 if they have not).

Once the user provides these inputs, the program calculates individual scores for each category using previously defined functions. It calculates the BMI score based on the user's BMI and waist circumference, the waist score based on gender and waist circumference, and similarly calculates scores for triglycerides, fasting blood glucose, HDL cholesterol, and high blood pressure.

After calculating these individual component scores, the program sums them to generate a total health risk score. The program then prints out the individual scores for each category, providing detailed feedback on how each factor contributed to the overall score. If the total score is zero, it informs the user that no risk factors were flagged. Otherwise, it categorizes the total score into a risk category (low, moderate, high, or very high) and displays this information to the user. 
