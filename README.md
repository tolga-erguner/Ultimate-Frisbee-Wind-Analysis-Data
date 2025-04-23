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
- Pearson correlation coefficient: r = 0.33, p = 0.0314 (Significant positive correlation)
- Two-sample t-test (Calm vs Windy+Very Windy): t = -1.33, p = 0.2047 (Not significant)

### **Limitations & Considerations**

- The analysis is limited to the 2022–2024 seasons of DC Breeze and may not generalize to all teams or locations.
- Wind speed is derived from city-level weather data and may not reflect actual stadium conditions.
- Turnover types (forced vs. unforced) are not distinguished due to data limitations.

### **Tools & Libraries**

- Python 3.9
- pandas, numpy
- matplotlib, seaborn
- scipy (for statistical tests)
- requests (API calls)
- selenium (for web scraping)

### **Conclusion**

The analysis suggests that higher wind speeds are moderately associated with more turnovers. While the Pearson correlation supports the hypothesis, the t-test does not confirm a statistically significant difference between calm and windy groups. Future work could involve a larger sample size, more granular wind data, or including turnover types to strengthen the findings.
