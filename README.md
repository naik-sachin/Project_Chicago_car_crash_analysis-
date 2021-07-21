# Introduction:
In 2017, there were 311,679 motor vehicles accidents in Chicago, Illinois. Out of these about 21.5 % resulted in injuries. Due to the rise in injury-resulting accidents in the state of Illinois, the Department of Transportation wants to take necessary measures to make the roads safer for all motorists. 
<br/> **The goal** of this analysis is to help the Department of Transportation with meaningful insights so they can take the necessary measures needed to reduce hit and run accidents and make the roads safer for its residents. Additionally, I will build a classification model to help identify hit and run accidents that resulted in injuries.

# Data:
The data came from the traffic crashes data set that's available to the public on the [Chicago Data Portal](https://data.cityofchicago.org/). The dataset contains all traffic crashes that were reported by the police within the city limits, going back to 2013. The data set also has a persons component that was not used in this project. The Traffic Crashes dataset contains a number of features related to the accident (49 to be exact). Unusable administrative data such as CRASH RECORD ID','RD NO', etc. was eliminated. Some features such as "SECONDARY CAUSE" ,"TRAFFICWAY TYPE",etc were consolidated based on the information provided by other columns. The data was narrowed down to 23 features that resulting in about 90000 accidents. The causes that accounted for less than 1% of the data such as train accidents were also removed. Hit and Run accidents that were listed as unknowns were labelled as hit and run unknowns. Lastly the data was filtered down to injury-resulting accidents, which resulted in about 50000 accidents. The data required minor cleaning before proceeding to modelling.

# Data Exploration:
Some of the main observations and supporting visuals are as follows: 

![alt text](Images/injury_tesulting.png)

I first wanted to look at most occuring crash type and most occuring primary cause of accidents in Chicago . The top 10 causes of accidents accounted for about 93% of the accidents. As seen in the graph above, Hit and Run was the highest cause of  accidents  accounting for nearly 23% of them. Rear end accidents were the most occuring type of accidents. 
Next I wanted to see 

<br/> Considering Hit and Run accidents was the most ooccuring cause and among the top 3 to result in injuries. I focused the remainder of this analysis on traffic accidents that resulted in injuries. I first looked at the breakdown of types of injuries as seen below:

![alt text](Images/injury_breakdown.png)
Failing to yield right-of-way had the highest proportion of injury resulting instances. 
I tooked at the occurence of hit and run accidents and injury resulting accidents by location and by the time of the day and there was no obvious pattern. Both followed the same pattern as the other accidents which was during peak commuter hours which makes sense because a higher number of cars on the road result in a higher number of accidents . Roads with posted speed limit of 30 mphhad the most injury resulting accidents (about 75%).

# Data Modeling:
I Used a decision tree classifier to model and classify hit and run injury resulting accidents. There was some imbalance in classes as only about a fourth of the accidents were hit and run cases so i had to generate some synthetic data. I eliminated irrelevant features recursively from 21 to 19 and i was able to get the accuracy to 72%. Tuning the hyperparameter of the classifier I was able get the accuracy upto 79% . I further used meta estimators like random forests and bagging classifier and got the accuracy upto about 85%. 

# Conclusions and Future Work:
Based on the data I would recommend higher surveillance or the roads to remedy Hit and run cases especially during peak hours.Roads with posted speed limit of 30mph should have more speed-regulators or policing to make these roads safer. In order to reduce rear end accidents the city should take speed inhibiting/breaking measures. .For Future work we would like to focus more on the top 5 types of accidents as they account for more than 95% of all accidents.I would also like to conduct a study by sectioning the city into smaller zones to tailor the recommendations by counties or towns.
