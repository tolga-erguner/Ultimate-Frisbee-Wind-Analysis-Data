### **Project Description**

This project aims to analyze how wind speed affects turnover rates in Ultimate Frisbee, using the DC Breeze team’s performance in the 2024 UFA season. Turnovers—losing possession of the disc—are critical moments in a match, and wind conditions are often considered a major factor in their occurrence.

**### How Wind Affects Ultimate Frisbee**

Ultimate Frisbee is a fast-paced sport where teams advance the disc by passing it among players. Since the disc is lightweight, wind conditions significantly impact gameplay in several ways:

- Throwing Accuracy: Strong winds make it difficult to throw precise passes, especially for longer throws (hucks) and high-release passes.

- Catching Difficulty: Crosswinds and gusty conditions can cause the disc to move unpredictably, leading to more drops.

- Strategy Adjustments: Teams may change their playstyle based on wind direction—favoring short passes in strong winds or using the wind to their advantage for deep throws.


### **Data Collection Plan**

To conduct this analysis, I will collect two main datasets:

       **1. Turnover Rates from UFA (Ultimate Frisbee Association)**
       
Source: https://watchufa.com/stats/team-game-stats (It shows all turnover and other stats for the teams)
Data: Turnover rates of a DC Breeze team throughout the last three season.

**Fields Extracted:**
	•	Date of the match
	•	Total turnovers
	•	Opponent


       **2.  Wind Speed Data**


Source: Visiual Crossing https://www.visualcrossing.com

Data: Wind speed at the specific location and time of each 

### Motivation

In Ultimate Frisbee, wind can drastically affect the game due to the light weight and flight sensitivity of the disc. Wind can:
	•	Make throws less accurate,
	•	Increase drop rates,
	•	Force teams to adopt more conservative strategies.

By understanding this relationship, teams can make better decisions when planning tactics for windy conditions.

### 


### Exploratory Data Analysis 

1. Descriptive statistics for turnover distribution and wind conditions
2. Box plots: Turnover counts by wind speed categories (e.g., calm, moderate, strong)
3. Scatter plot: Wind speed vs. turnover rate
4. Correlation matrix to explore relationship between variables


### Limitations & Considerations

- The analysis is limited to the 2022-23-24 season of DC Breeze and may not generalize to all teams or weather conditions.
- Wind speed is taken from city-level estimates and may not perfectly reflect stadium-level wind patterns.
- Turnover types (forced vs. unforced) are not distinguished due to data limitations.


###  Tools & Libraries

- Python 3.9
- pandas, numpy
- matplotlib, seaborn
- scipy (for statistical tests)
- requests (API calls)

### Hypothesis Testing

Null Hypothesis (H₀): Wind speed has no effect on turnover rates.
Alternative Hypothesis (H₁): Higher wind speed leads to higher turnover rates.
Test: Two-sample t-test (e.g., chill vs. strong wind), Pearson correlation coefficient.
