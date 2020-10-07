# US Flights Data Exploration

## Dataset


>The dataset consists of 5 years of information on US flight performance data. Each dataset (for each year) contains around 1 to 7 millions of records. I used a subset of each dataset (20,000) records per year (100K in total.) Dataset contains many variables including delay sources (Carrier delay, NAS delay, etc), flight distance, elapsed time, arrival & departure times and more. For me, sources of delay and time factors were the most interesting variables to explore why a flight may arrive late (Variable of Interest: ArrDelay).
A good amount of wrangling was performed prior to exploration since some variables had missing records (such as Arrival & departure delays), many variables had problematic datatypes. And some variables required some basic feature engineering to facilitate data analysis & exploration (i.e. changing arrival time from hh.mm. format to a single number: Arrival hour). I stored the resulting clean dataframe into a CSV file and exported it locally.
- Dataset: https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/HG7NV7
- Variables description: https://www.stat.purdue.edu/~lfindsen/stat350/airline2008_dataset_definition.pdf



## Summary of Findings


>During exploration phase, I found many strong, positive correlations between predicting variables and arrival delay. First, as expected, departure delay was very much in line with arrival delay where correlation between them exceeded 0.9. Second, there were 3 top sources of delay that were consistently affecting arrival delay, and to a large extent. These factors were namely Late Arrival Delay, Carrier Delay, and NAS Delay. When any of these variables increased, Arrival Delay increased too. Also, when adding these variables together (via feature engineering), the correlation between them and Arrival Delay becomes really significant! 

>On the other hand, Time proved to be a main contributor too. Exploring departure delay along the day showed that there is a general upward trend where flights face higher departure delay with every extra hour. Shockingly, the average departure delay for late-night flights was incredibly high. Digging deeper shown that Late AirCraft Delay was a main contributor to this phenomenon where average delay was around 80 minutes+. It was hard though to further explain why this happens. 

>Finally, exploring year-over-year change in delay showed very interesting results, where flight performance seem to **worsen** over 5 years with average arrival & departure delays increasing consistently. Also the other sources of delay (especailly top 3) seemed to spike over the years too. Especially Late Arrival Delay again was a major contributor to overall delay and flight performance.






## Key Insights for Presentation

> For the presentation phase, I was mainly interested in two sets of relationships. 
A- How main sources of delay impacted flight performance? In this part, I started by logically visualizing the main variable of interest (Arrival delay) and the top 3 sources of delay. Then I plotted the relationship between these variables using heatmaps & scatterplots whenever relevant.  In the process I used both axis limits & log transformation for better visualization. Also for further polishing, I simplified heatmaps to only show relevant information.
B- How time influenced arrival performance? In this regard, I used multivariate explanation charts to show the relationship between Arrival vs Departure delay over years. I also used seaborn pointplots in a very simple fashion to show  average change in delay for main delay sources (Carrier, NAS, etc.) over a period of 5 years. I used salient color coding for different variables to show that there is no sequence/order to the variables. 


## References
- On creating dataframe subsets:  
https://stackoverflow.com/questions/22258491/read-a-small-random-sample-from-a-big-csv-file-into-a-python-data-frame  
- Adding an empty plot for multiple legends:  
https://stackoverflow.com/questions/28078846/is-there-a-way-to-add-an-empty-entry-to-a-legend-in-matplotlib/28081279
- US flights data descriptions:  
https://www.bts.gov/topics/airlines-and-airports/understanding-reporting-causes-flight-delays-and-cancellations

