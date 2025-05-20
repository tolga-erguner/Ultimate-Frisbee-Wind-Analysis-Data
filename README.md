### **Project Description**

This project aims to analyze how wind speed affects turnover rates in Ultimate Frisbee, using the DC Breeze team’s performance in the 2022–2024 UFA seasons. Turnovers—losing possession of the disc—are critical moments in a match, and wind conditions are often considered a major factor in their occurrence.

### **How Wind Affects Ultimate Frisbee**

Ultimate Frisbee is a fast-paced sport where teams advance the disc by passing it among players. Since the disc is lightweight, wind conditions significantly impact gameplay in several ways:

- **Throwing Accuracy**: Strong winds make it difficult to throw precise passes, especially for longer throws (hucks) and high-release passes.
- **Catching Difficulty**: Crosswinds and gusty conditions can cause the disc to move unpredictably, leading to more drops.
- **Strategy Adjustments**: Teams may change their playstyle based on wind direction—favoring short passes in strong winds or using the wind to their advantage for deep throws.

### **Data Collection Plan**

To conduct this analysis, I collected two main datasets:

**1. Turnover Rates from UFA (Ultimate Frisbee Association)**  
Source: https://watchufa.com/stats/team-game-stats  
Data: Turnover rates of the DC Breeze team throughout the last three seasons.

**Fields Extracted:**
- Date of the match
- Total turnovers
- Opponent

**2. Wind Speed Data**  
Source: Visual Crossing – https://www.visualcrossing.com  
Data: Wind speed at the specific city location and date of each match.

### **Motivation**

In Ultimate Frisbee, wind can drastically affect the game due to the light weight and flight sensitivity of the disc. Wind can:
- Make throws less accurate
- Increase drop rates
- Force teams to adopt more conservative strategies

By understanding this relationship, teams can make better decisions when planning tactics for windy conditions.

### **Exploratory Data Analysis**

1. Descriptive statistics for turnover distribution and wind conditions
2. Box plots: Turnover counts by wind speed categories (e.g., calm, moderate, strong)
3. Scatter plot: Wind speed vs. turnover rate
4. Pearson correlation coefficient

![Image](https://github.com/user-attachments/assets/bc9a2ff0-3d02-49dc-bc30-652eee300802)



![Image 2](https://github.com/user-attachments/assets/3f498f9a-eafe-45da-8514-b2ef823afce5)




![Image 1](https://github.com/user-attachments/assets/37aa279d-cc60-46a1-8828-6f0bf7ee1f85)



### **Hypothesis Testing**

- **Null Hypothesis (H₀):** Wind speed has no effect on turnover rates.
- **Alternative Hypothesis (H₁):** Higher wind speed leads to higher turnover rates.

**Test Methods:**
- **Pearson Correlation**  
  - `r = 0.60`, `p = 2.23e-05`  
  - Suggests a **moderate positive correlation** that is statistically significant

- **Two-sample T-Test**  
  - Compared calm conditions vs windy/very windy
  - `t = -2.38`, `p = 0.0324`  
  - Indicates a **significant difference** in turnover averages between wind levels

These findings confirm a meaningful relationship between wind speed and turnover frequency, supporting the project's hypothesis.

### **Machine Learning Models**

To move beyond correlation, we attempted **predictive modeling** using turnover counts as the target, and wind speed along with percentage-based performance metrics as features.

#### 3 Models Trained:

- **Linear Regression**
  - R² Score: -0.97
  - MSE: 30.77  
  - ➤ Failed to model the relationship due to non-linearity of the datasets.

<img width="720" alt="Screenshot 2025-05-20 at 21 45 35" src="https://github.com/user-attachments/assets/88823295-1f14-4a8d-97be-60bd7543738b" />


- **Decision Tree Regressor**
  - R² Score: 0.69
  - MSE: 4.89  
  - ➤ Captured branching relationships, handled thresholds better.
 
  <img width="720" alt="Screenshot 2025-05-20 at 21 45 41" src="https://github.com/user-attachments/assets/fe67813c-9709-4ab9-89c9-2bf30c57c2f3" />


- **Random Forest Regressor**
  - R² Score: 0.76
  - MSE: 3.89  
  - ➤ Best performing model, robust to noise, and more generalized.


<img width="720" alt="Screenshot 2025-05-20 at 21 45 50" src="https://github.com/user-attachments/assets/33c1ad36-fa6b-4d96-a5de-9e2d35c63b82" />

#### 🔍 Why Tree-based Models Worked Better

Linear regression assumes a **consistent, linear relationship** between features and target. However, in Ultimate Frisbee:

- Turnovers **don't increase smoothly** with wind speed.
- Players often adapt to mild/moderate wind, showing little to no performance drop.
- But **after a certain threshold**, wind can cause a sharp rise in errors.

Tree-based models like **Decision Trees** and **Random Forests** excel in this type of **nonlinear, rule-based environment**. They can effectively split data based on feature thresholds—such as "if wind > 30 m/s"—making them ideal for this kind of sports performance data.



### **Limitations & Considerations**

- The analysis is limited to the 2022–2024 seasons of DC Breeze and may not generalize to all teams or locations.
- Wind speed is derived from city-level weather data and may not reflect actual stadium conditions.
- Turnover types (forced vs. unforced) are not distinguished due to data limitations.

### **Tools & Libraries**

- Python 3.9
- pandas, numpy
- matplotlib, seaborn, scikit-learn
- scipy (for statistical tests)
- requests (API calls)
- selenium (for web scraping)


### **Conclusion & Interpretation**

The goal was to explore whether wind speed can be used to **predict turnover counts** in Ultimate Frisbee. The answer is: **partially, yes**—but with important caveats.

- **Wind is clearly a relevant factor**, as confirmed by hypothesis testing and predictive modeling.
- However, **Ultimate is too complex to be explained by wind alone**. Other influential variables include:
  - Opponent strength and tactics
  - Stadium conditions
  - Player fatigue and lineup changes
  - External factors like rain or crowd pressure

These limitations help explain **why linear models underperformed** and why even tree-based models have room for improvement.

Still, **Random Forest** achieved solid performance using only wind and match metrics—suggesting that even with limited data, predictive modeling in sports analytics has real potential.

### **Final Thoughts**

This project illustrates the power of combining **domain understanding** (Ultimate Frisbee) with **data science tools** (statistical testing, ML models) to analyze complex dynamics. While the findings show that **wind has a measurable impact on turnovers**, they also reveal the **multi-dimensional nature of sports**—where no single factor dictates the outcome.

Future improvements could include:

- Adding opponent difficulty as a quantified feature
- Incorporating rainfall, temperature, or home/away status
- Expanding to include multiple teams for generalizability

Even though the dataset and feature set were limited, this project proves that **data-informed insights are feasible**—and can even challenge our assumptions about what really drives performance on the field.

