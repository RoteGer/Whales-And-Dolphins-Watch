# Dolphins and Whales Watching - Machine Learning project
##### By Guy Ofir and Rotem Gershenzon

## Project intro
Almost every day, for over 20 years, Capt. Dave and Mrs. Captain Dave have been taking people sailing in Southern California (San Diego) to enjoy the company of some of the most magnificent marine mammals on the planet. Since 2002, they have kept records of every sea animal they saw during their trips that day.

## Research Question
Can we predict whether an animal will be seen based on past records and weather records?

## Data Sources
Capt. Dave’s Whale Watching log, Sightings Archive - https://www.dolphinsafari.com/sightings-log/whale-watching-sightings-archive/
California Current Ecosystem LTER - https://oceaninformatics.ucsd.edu/datazoo/catalogs/ccelter/form

## Data Acquisition
We crawled to Capt. Dave’s website and got a list of all the relevant links. from each link we extracted the sightings table. the tables on the website does not have identical columns. therefore, plenty of data organization was needed.

## Data Organization
We classified the data to a few main groups, based on years. for each group we used a different method of data organization.
Once we had identical coulumns in each group, we merged all to one big data frame, then added a data frame of weather for each day (Avg Temp (C), Avg Wind Speed (M/C)).


## Visualizations
### Scatter plots
<img width="245" alt="image" src="https://user-images.githubusercontent.com/76396600/149321348-fad140ce-f711-4d2a-b539-dc249f5ba424.png"> <img width="246" alt="image" src="https://user-images.githubusercontent.com/76396600/149321434-659be168-be2d-434c-afd5-1675ca105832.png"> <img width="250" alt="image" src="https://user-images.githubusercontent.com/76396600/149321481-fc7c38e3-2c2e-489d-8945-15fef6e02201.png"><img width="240" alt="image" src="https://user-images.githubusercontent.com/76396600/149321524-780a379e-52e7-42d9-8744-ee3532e090d0.png"><img width="250" alt="image" src="https://user-images.githubusercontent.com/76396600/149321399-08227f7f-886f-4e64-a727-40d0af5fc615.png"><img width="232" alt="image" src="https://user-images.githubusercontent.com/76396600/149321628-e9004997-7116-46a8-a168-c6eff6d784fd.png">

It is hard to see in these scatter plots a very strong connection, hence we looked for a connection with line plots:
### Line Plots

![image](https://user-images.githubusercontent.com/76396600/149322952-0061d8c5-bb7d-4f28-8a79-0f5e4d5fedc7.png)![image](https://user-images.githubusercontent.com/76396600/149323050-efaafacd-15db-4e36-8533-78eb9deea6de.png)![image](https://user-images.githubusercontent.com/76396600/149323060-3ee1a40d-1235-4ccb-b22f-8c36a7b3b69a.png)![image](https://user-images.githubusercontent.com/76396600/149323070-79268ed8-4130-4d1b-80cc-c9c11350fa5b.png)![image](https://user-images.githubusercontent.com/76396600/149323085-a9d8c3e4-2936-44c3-b0a2-d43db279c770.png)![image](https://user-images.githubusercontent.com/76396600/149323240-1f8d35e9-a9c1-436a-9579-917b7a5ed246.png)

There is a strong connection between months and the amount of each animal they saw throughout the years, especially Gray Whales.
Therefore there is a seasonal connection as we can see in the next plot:

### Scatter Plot - Gray Whale
![image](https://user-images.githubusercontent.com/76396600/149323970-4f0f2ed2-3864-4192-9ca1-1c55153f1944.png)


#### We transferred the data to be binary. 
0 means the animal was not seen that day.
1 means the animal was seen.

![image](https://user-images.githubusercontent.com/76396600/149324144-264e1d38-0dbe-4d09-82ac-9fdb5111b251.png)![image](https://user-images.githubusercontent.com/76396600/149324168-27a7d421-7190-4d67-b838-86661fd8d605.png)

## Machine Learning
First, we tried the Decision Tree algorithm and The Random Forest algorithm. Although they yielded high accuracies for each animal, we assumed it is because of overfitting. Hence, we used Logistic Regression Algorithm that works well with categorized Binary problems.
The Logistic regression indeed yielded great accuracies on our Binary data, especialy for animals with patterns to their occurence (such as Gray Whale).

![image](https://user-images.githubusercontent.com/76396600/149327571-aec38f31-a5ec-4219-8e5d-d96ab067da00.png)


