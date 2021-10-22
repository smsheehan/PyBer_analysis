# PyBer_analysis



## Overview of the analysis: 

Explain the purpose of the new analysis.

The purpose of this analysis was to evaluate ride-sharing data from the fictional ride-share company, PyBer.  Specifically, our fictional CEO was interested in understanding if any business insights could be gleaned through evaluation of the relationships between city type, fares, and number of drivers.  Additionally, since our data contains detailed information about the date of each individual ride, we were asked to evaluate the data temporally over the first trimester of 2019.  From a skills standpoint, this purpose of this challenge was to explore merging two data sets, demonstrate proficiency with utilization of the groupby() function, and to introduce us to two new functions: pivot() and resample(). 

## Results: 
Using images from the summary DataFrame and multiple-line chart, describe the differences in ride-sharing data among the different city types.


In order to best present the results, I will also describe the process used to obtain the results.  The PyBer data needed for this analysis exists in two separate .csv files and I first needed to merge the files using the code shown below.  It was important to inspect the data first to ensure a) that the two data sets shared a mutual column to be merged upon, and b) that I knew what the columns were named in each file.

![image](https://user-images.githubusercontent.com/90977689/138496682-98ac7b6a-94b6-4f4e-8ca4-e113f2dc41da.png)

Now that the datasets were combined into a single dataframe, grouping the data by city type and using the count() function on ride_id revealed the first insight of this analysis:

![image](https://user-images.githubusercontent.com/90977689/138497015-6140ca34-afde-4cc3-af66-fb77a5ff874b.png)


As we can see from the above image, it is clear that most of PyBer's business, in terms of number of rides, comes from urban cities.  Suburban locations are the next busiest, followed by rural locations.  It is interesting to see that Pyber provides 2.6x more rides in urban vs suburban and 13x more rides in urban vs rural.  

Next, grouping the data by city type and using the count() function on driver_count elucidated the next insight.  The number of drivers per city type follows a similar trend to that of number of rides.  Urban areas had the most number of drivers, followed by suburban, and then rural.  Urban had 4.9x the number of drivers vs suburban and urban had 30.8x the number of drivers vs rural. The code for this is shown below.  The important thing to note about this code is that you need to go back to the city_data_df to get this information.  If one tries to extract this information from the merged data frame, the numbers retrieved are not correct.  The reason for this is that when the data sets are merged, the driver_count gets populated into every row for each individual ride in a particular city.  For example, the city of Amandaburgh has 12 drivers and 18 rides.  If we ran this code on the merged dataframe, we would get 12x18 drivers as our count.  Running the count on the original city_data_df solves this problem.

![image](https://user-images.githubusercontent.com/90977689/138514758-a1888676-d66d-46d0-85bd-972e990d4e1a.png)



## Summary: 
Based on the results, provide three business recommendations to the CEO for addressing any disparities among the city types.
