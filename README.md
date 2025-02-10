# ML-EDA
Overview This dataset aims to provide insights into the dating app usage patterns and preferences of Generation Z (individuals aged 18-25) in India. It encompasses various aspects of demographic details, app usage behavior, and user preferences.

 Dataset Features The dataset includes the following categories: 
 1. Demographic Information
  Age 
  Gender 
  Location (City/State) 
  Education Level 
  Occupation (Potentially) 
  Religion 
  Sexual Orientation 

2. App Usage Data
 Primary and secondary dating apps used 
 Frequency of usage 
 Average time spent on apps 
 Reasons for using dating apps (e.g., finding a partner, casual dating, social interaction) 
 Satisfaction levels with dating apps 
 Challenges faced (e.g., safety concerns, lack of genuine matches)

 3. User Preferences 
 Desired features in dating apps (e.g., video/audio calls, detailed profiles, location-based matching) 
 Preferred communication methods
Attitudes towards online dating and relationships 
Importance of various factors in partner selection, such as: Physical appearance 
Personality 
Interests 
Values 

Potential Applications 
This dataset can be valuable for: 
Researchers: To study trends in online dating among young adults in India. 
Marketers: To understand consumer behavior and improve targeted marketing strategies. 
Dating App Developers: To enhance features and user experience based on preferences and challenges faced by Generation Z.

DATA DICTIONARY

| Column Name           | Data Type|  Description |
|---------------------------|----------|-------------|
| User_ID               | int64    | This is a special identifier for each individual. |
| Age                   | int64    | Age of the individual (18-25 years). |
| Gender                | object   | Gender identity of the individual (e.g., Male, Female, Non-binary). |
| Location              | object   | City or state where the individual is located. |
| Education             | object   | Highest level of education attained (e.g., Undergraduate, Graduate). |
| Occupation            | object   | Current employment status (e.g., Freelancer, Intern, Full-time Job). |
| Primary_App           | object   | The main dating app used by the individual. |
| Secondary_Apps        | object   | Other dating apps used by the individual. |
| Usage_Frequency       | object   | How often the individual uses dating apps (e.g., Daily, Weekly, Monthly). |
| Daily_Usage_Time      | object   | Average time spent on dating apps per day (e.g., 30 minutes, 1 hour). |
| Reason_for_Using      | object   | The respondent’s primary reason for using dating apps (e.g., Finding a Partner, Casual Dating, Social Interaction). |
|Satisfaction          | int64    | Satisfaction level with dating apps on a scale (e.g., 1-5). |
|Challenges            | object   | Difficulties faced by the individual when using dating apps (e.g., Safety Concerns, Lack of Genuine Matches). |
|Desired_Features      | object   | Features the individual wants in dating apps (e.g., Video Calls, AI Recommendations). |
|Preferred_Communication | object | Preferred communication method for online dating (e.g., Text, Video Calls, Voice Notes). |
|Partner_Priorities    | object   | Factors prioritized in selecting a partner (e.g., Personality > Interests > Values). |

### Below Are the Data Cleaning Steps That The Data Went Through

# Identifying and Handling Missing Values
Retrieved missing values with print(df.isnull().sum())
Identified the Percentage of Missing Values using ((data.isnull().sum())/data.shape[0] ) * 100
Categorical Columns were filled using the mode and A Placeholder

# The standardization of Categorical Data.
- Made all text fields lowercase. 
- Ensured that formatting was consistent (for example, Male and Male were unified).

# Detecting and Handling Outliers
- Used the box plot method to identify outliers in the Age ,Satisfaction and Daily_Usage_Time Columns

# Version Control.

- Version 1 of the cleaned dataset was committed to GitHub, with the message: "Cleaned dataset: removed duplicates, handled missing values, and standardized categories."


#### Deep Exploratory Data Analysis (EDA)

#### Below Are the EDA Steps That Were Performed on The Dataset
# Relationship Ananlysis
1. A Correlation Heat Map was plotted to identify the relationships between the numerical variables (User_ID,Age, Daily_Usage_Time,Satisfaction)

2. Performed Groupby Aggregations(listed below) and Pivot Table
- Grouping by gender and calculating average satisfaction level
- Grouping by location and getting counts of Primary Apps used
- Plotted a pivot table to analyze app usage by gender

3. Plotted a Stacked Bar Chart to visualize categorical comparison between Dating App Usage and Gender

# Github Branch
A dedicated GitHub branch (feature-EDA ) was created to ensured safe experimentation

## Detecting Patterns and Bias in Data
- Density Plots and Histograms were utilized to compare distributions across various demographic groups
- Identify overrepresented and underrepresented groups using demo_counts = df[demographic_cols].value_counts(normalize=True) * 100
print("Demographic Group Representation (%):\n", demo_counts.sort_values(ascending=False))

# GitHub Repository Updated With Commit Message
"Added bias detection analysis and demographic trends" ##

## Temporal & Regional Trends
- Plotted a Line Chart to show trends in the time Daily Usage Time Trends by Usage Frequency and Gender
- A Geospatial Visualization was created to visualize the App Usage Differences Across different Locations ( Cities)
- A  Bubble Chart was plotted to represent app popularity across age groups

## Feature Engineering for Future Modeling 
- Encoded categorical variables using One-Hot Encoding or Label Encoding.
- Normalized numerical variables using MinMaxScaler or StandardScaler.
- Created a new feature, "active app count," by summing the number of apps used per user.

# The engineered dataset with a message:  
“Feature engineering: Encoded categorical variables & added new features."

### FINAL SUMMARY
- The dataset was cleaned, standardized, and analyzed through EDA, revealing trends in demographics, app usage, and preferences, followed by bias detection, geospatial analysis, and feature engineering for future modeling. All changes were version-controlled on GitHub, ensuring a structured and collaborative workflow
