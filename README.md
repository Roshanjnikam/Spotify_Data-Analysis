# Spotify Listening Behaviour Analysis Report
##### By Roshan Nikam 
This report presents an in-depth analysis of user listening behaviour on Spotify, based on detailed session-level data. It explores user engagement, skip behaviour, content preferences, and time-based trends.

### 1.  Average Listening Duration per Session by Platform


<img width="610" height="394" alt="image" src="https://github.com/user-attachments/assets/f38cc389-48bb-42f0-8e4c-450f9441ab1b" />

 
Visualization Description:
A bar chart was used to compare average session duration (in minutes) across platforms. MAC showed the highest duration, followed by Cat to device, with ios platforms trailing behind.

### 2. Skip Rate by Platform and Shuffle Mode
Insight:
Approximately 26% of all tracks were skipped. The skip rate was notably higher on windows platforms and when shuffle mode was enabled. This suggests that users are more selective or less engaged when listening passively or on less controllable interfaces.


<img width="527" height="344" alt="image" src="https://github.com/user-attachments/assets/5f37ac61-6c34-4c20-88eb-89fabde8725a" />


<img width="522" height="304" alt="image" src="https://github.com/user-attachments/assets/e8b0d0a4-0960-4305-910f-84ce844fb108" />


Visualization Description:
Two bar plots were created:
•	One showing skip percentage by platform.
•	Another showing skip percentage by shuffle mode (On vs. Off).

### 3.  Relationship Between Shuffle and Skip Rate
Insight:
There is a clear correlation between shuffle mode and skip behavior


 <img width="461" height="288" alt="image" src="https://github.com/user-attachments/assets/55d38709-7875-41d8-a179-51e444b1b15b" />


Visualization Description:
A grouped heatmap chart illustrated skip rates for both shuffle.

### 4. Time of Day with Highest Listening Volume
Insight:
Listening activity downfall during the midnight hours (12 AM to 12PM), aligning with. A secondary peak is seen around 5 PM and 6PM after-work or relaxation times.
`

<img width="618" height="372" alt="image" src="https://github.com/user-attachments/assets/bbc4de0c-3230-403c-acbb-071232dcfcbd" />


Visualization Description:
A line chart plotting total listening time per hour of the day revealed these time-based patterns.

### 5.  Most Played Artists and Tracks
Insight:
Artists like The Beatles, The killers, and John Mayer  were among the most played, both in terms of total time listened and play count. “ode to the ments” was a standout track.


<img width="530" height="407" alt="image" src="https://github.com/user-attachments/assets/d1899a7a-beae-47fa-a460-7bda82b2ed4d" />


Visualization Description:
 charts showed the top 10 artists and tracks ranked by total ms_played.

### 6. Artists/Albums with Longest Average Playtime
Insight:
Artists known for immersive music—such as cory weeds and dan Lackman—had the longest average playtime per track, indicating deeper engagement or album-oriented listening.


<img width="524" height="247" alt="image" src="https://github.com/user-attachments/assets/80561e61-0198-4b4b-a79d-eda55b7935fd" />


<img width="940" height="250" alt="image" src="https://github.com/user-attachments/assets/9acef0f6-903d-434c-b466-d01f1e9ff701" />


Visualization Description:
Grouped showed average ms_played per track by artist and album

### 7. Most Skipped Artists or Songs
Insight:
Tracks with high skip rates tended to be paraiso or photograph, suggesting users might sample them frequently but not finish them. Some lesser-known artists also had high skip rates, possibly due to mismatched recommendations.


<img width="483" height="305" alt="image" src="https://github.com/user-attachments/assets/dc4a213f-45dc-4fdd-98dd-19b8ffe64850" />


<img width="328" height="317" alt="image" src="https://github.com/user-attachments/assets/f65525af-686a-4998-9604-067b4b520a1f" />


Visualization Description:
 charts ranked artists and songs by skip rate.

### 8.  Average Listening Time Before Skip
Insight:
Tracks are most often skipped within the first  52 seconds. This reflects user impatience or disinterest when a song fails to immediately capture attention.


 <img width="922" height="97" alt="image" src="https://github.com/user-attachments/assets/261cc967-f614-4671-ae5c-444be5893ab1" />


### 9.  Start and End Reasons for Tracks


<img width="417" height="321" alt="image" src="https://github.com/user-attachments/assets/355e4346-1888-4aa8-a17c-312a0718e5f8" />


<img width="440" height="402" alt="image" src="https://github.com/user-attachments/assets/ae503183-3e4b-427c-b034-ef6599194981" />


Visualization Description:
Two bar charts showed the distribution of reasons for track start and end.

### 11. How Listening Behavior Changed Over Time
Insight:
Listening habits revealed weekly cycles, with noticeable peaks on weekday. A long-term trend showed increasing engagement, possibly due to seasonal factors or new content releases.
 

<img width="940" height="132" alt="image" src="https://github.com/user-attachments/assets/e1b58092-ee65-460d-b67d-a47e519d1879" />


## Machine learning
### 1. Random Forest Classifier
Model Type: Ensemble decision tree-based algorithm
Why Used: Good for handling both numerical and categorical data, robust to overfitting, and provides feature importance.


 <img width="523" height="204" alt="image" src="https://github.com/user-attachments/assets/33e32712-7fb0-4cd2-bea8-ef53768a11af" />


Performance Summary:
Accuracy: 0.95 → 95% of all predictions were correct.
•	Precision: Out of the predictions for each class, how many were correct.
 For True, only 61% of the predicted True values were actually correct.
•	Recall: Out of the actual samples of a class, how many were correctly predicted.
For True, only 19% of actual True cases were correctly predicted — very low recall.
•	F1-Score: Harmonic mean of precision and recall.
True has an F1-score of 0.29 → very poor performance on this class.
•	Support: Number of actual occurrences in the dataset.
Class True is highly underrepresented → data imbalance issue.
Key Features Identified:
•	ms_played: Most important feature (short play duration strongly predicts a skip)
•	platform: Mobile platforms slightly more predictive of skips
•	shuffle: Correlated with higher skip probability
•	reason_start: Autoplay and playlist-generated starts were more likely to be skipped



### 2.  Logistic Regression
Model Type: Linear classifier for binary outcomes
Why Used: Interpretable model that helps understand linear relationships between features and skip probability.


 <img width="630" height="232" alt="image" src="https://github.com/user-attachments/assets/559c5377-941b-40ca-894d-14348b28ce8b" />


Performance Summary:
Class 'False':
•	Precision: 95% of predicted 'False' labels were correct.
•	Recall: 100% of actual 'False' cases were correctly predicted.
•	F1-Score: Very strong (0.97), confirming excellent performance on this class.
Class 'True':
•	Precision: 20% of predictions labeled as 'True' were correct.
•	Recall: 0% of actual 'True' cases were detected by the model.
•	F1-Score: 0 — the model completely fails on the minority class.
 Insights from Coefficients:
•	Negative coefficient for ms_played: The longer a user listens, the less likely they are to skip
•	Positive coefficient for shuffle: Increases odds of a skip
•	Some reason_start types (e.g., manual play) decreased skip probability

