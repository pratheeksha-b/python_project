# python_project-Tech Workforce Mental Health and Burnout
This analysis explores a dataset of 150,000 records focused on mental health and burnout among tech professionals across eight distinct roles. For your data analytics project, the key insights can be categorized into behavioral trends, organizational impacts, and predictive modeling performance.

1. Key Drivers of Burnout
The sources identify specific factors that directly influence burnout scores and levels:
Stress as the Primary Predictor: There is a strong positive correlation (0.75) between stress_level and burnout_score.
Random Forest feature importance analysis also identifies stress_level as one of the most critical contributors to burnout.
<img width="547" height="552" alt="image" src="https://github.com/user-attachments/assets/67860d71-6598-425b-af17-ee53108d8493" />
Work-Life Balance: This variable has the strongest inverse relationship with burnout (-0.49), suggesting that as work-life balance improves, burnout scores significantly decrease.
Impact of Professional Support: Employees who have undergone therapy show a significantly lower average burnout score (1.78) compared to those who have not (2.22). Similarly, high manager support is linked to lower levels of stress, anxiety, depression, and burnout.

2. Behavioral & Lifestyle Insights
The data reveals how daily habits and social factors correlate with mental health:
Social Support: A high social_support_score is strongly linked to reduced anxiety (-0.489 correlation) and lower depression scores.<img width="567" height="433" alt="image" src="https://github.com/user-attachments/assets/5241d844-4f02-4834-ab97-68b36575ddf0" />
Sleep and Screen Time: sleep_hours negatively correlates with stress (-0.267), while increased screen time shows a positive correlation with anxiety scores (0.17).
<img width="567" height="455" alt="image" src="https://github.com/user-attachments/assets/2e5f3039-d9bc-4637-a075-44dcb1f4a2a5" />
Physical Activity: Engaging in physical activity is shown to reduce depression scores; those exercising 7 days a week have a mean depression score of 2.82 compared to 3.24 for those with 0 days. <img width="567" height="455" alt="image" src="https://github.com/user-attachments/assets/d53be6be-1004-4f05-bdf3-50ef5f9acbb9" />
Manager support: <img width="554" height="475" alt="image" src="https://github.com/user-attachments/assets/1c487adf-9ea7-4fdf-9198-0031d44f896f" />


3. Job Roles and Productivity
Burnout by Role: Frontend Developers were found to have the highest average burnout score (2.126).
Work-Life Balance: Product Managers were identified as having the worst work-life balance among the tech roles studied. <img width="584" height="561" alt="image" src="https://github.com/user-attachments/assets/db5014d8-7145-4583-8b33-6a799867af4e" />
Inefficiency and Satisfaction: There is a negligible correlation between work hours and job satisfaction across all roles. However, data suggests that employees with the highest work hours (Q4) tend to have slightly lower job satisfaction (5.48) compared to those in the lowest quartile (Q1: 5.51). <img width="565" height="444" alt="image" src="https://github.com/user-attachments/assets/324c95a7-05ab-46fa-b155-a395de1167ad" />
Deadlines: Missing deadlines has a small but negative correlation with job satisfaction (-0.0046).

4. Machine Learning Model Insights
The project successfully implemented two predictive models:
Burnout Score Prediction: A Random Forest Regressor achieved an R² score of approximately 0.83, indicating it can explain 83% of the variance in burnout scores based on the provided features.
Burnout Level Classification: A Logistic Regression pipeline (including StandardScaler and OneHotEncoder) achieved a near-perfect accuracy score of 0.999 for classifying burnout levels into Low, Moderate, or High.

5. Organizational Factors
Company Size: The data suggests that company size (Startup, MNC, Mid-size, Large) has minimal impact on average stress levels, with all categories averaging around 5.78.
              stress_level by 
company_size	
Large	        5.791370
MNC	          5.779742
Mid-size	    5.783807
Startup	      5.786760

Work Mode: There are only marginal differences in work-life balance and burnout scores between Remote, Hybrid, and Onsite workers. However, Hybrid and Remote workers showed a slightly higher percentage of individuals with "high screen time but low stress" (approx. 24%) compared to onsite workers (23.7%). <img width="565" height="472" alt="image" src="https://github.com/user-attachments/assets/a1415aec-d428-4a06-be97-dbd82585a037" />



By utilizing K-Means clustering, the study segmented 150,000 tech professionals into three distinct groups based on their mental health metrics and burnout levels

1. Identified Employee Segments (Clusters)
<img width="563" height="427" alt="image" src="https://github.com/user-attachments/assets/8c45c05b-cbae-456a-ada7-2018753150ee" />

The most critical insight is the categorization of employees into three behavioral segments, each representing a different level of psychological well-being:
Cluster 2: The Moderate-Risk Majority (46.3%): This is the largest group in the dataset. These employees experience moderate levels of stress (6.25), anxiety (5.03), and depression (3.61). Notably, this group reports the lowest job satisfaction (5.26), suggesting that even without reaching peak burnout levels, their engagement and happiness at work are significantly impacted.
Cluster 0: The Low-Risk Segment (41.4%): This group is characterized by the highest job satisfaction (5.81) and the lowest scores across all negative mental health indicators, including a burnout score of only 1.32.
Cluster 1: The High-Burnout Segment (12.3%): While this is the smallest group, it is the most critical for intervention. These employees report the highest levels of stress (7.54), anxiety (5.70), and depression (4.39), leading to a high mean burnout score of 4.26.
<img width="534" height="427" alt="image" src="https://github.com/user-attachments/assets/a9cdd8b7-7c98-4cdd-8eae-c2335a44341d" />
<img width="567" height="427" alt="image" src="https://github.com/user-attachments/assets/0c347b98-1bd3-43f0-b782-d8035f09248d" />

2. Relationship Between Mental Health and Job Satisfaction
The data demonstrates a clear inverse relationship between burnout and job satisfaction. As stress, anxiety, and depression scores increase, job satisfaction tends to decrease. Interestingly, Cluster 1 (the high-burnout group) has slightly higher job satisfaction (5.37) than Cluster 2 (the moderate group), which could indicate that employees in the most high-pressure roles might still find some fulfillment or value in their work despite the extreme stress.

3. Demographic Consistency
A surprising insight is that demographics and experience levels are almost identical across all three clusters. The average age (approximately 38) and average years of experience (approximately 5) do not significantly differ between those at low risk and those at high risk for burnout. This suggests that burnout in the tech industry is driven more by work environment, job roles, or individual circumstances rather than age or tenure.
          Average age and  experience_years
for cluster		
0	      37.993321	  5.058065
1	      37.903482	  5.063237
2	      38.086204	  5.050102

4. Predictive Modeling Performance
The technical analysis also highlights the high predictability of employee burnout categories:
Logistic Regression: This model achieved a remarkably high accuracy score of 99.94% in classifying employees into their respective clusters.
PCA (Principal Component Analysis): Using 29 components, the model was able to explain over 91% of the total variance in the dataset. Reducing the data to just 2 principal components still allowed for a visual distinction between the three clusters, as shown in the scatter plot
<img width="559" height="413" alt="image" src="https://github.com/user-attachments/assets/c8b2397b-5c75-4672-b782-53238370e06a" />

