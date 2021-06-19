# (Dataset Exploration Title)
## by (your name here)


## Dataset

> The fordgobike-tripdata dataset provides information on each bike ride made in the fordgobike program from February 1st, 2019 to March 1st, 2019. 
It contains information such as starting station details, ending station details, starting time, ending time, 
duration of the ride and information about the rider such as rider's gender, birth_year, program subscription type for about 183K rides made. 
There are about 183k rows and 16 columns.

The columns have 2 Datetime variables('start_time', 'end_time')
2 numerical types('duration_sec', 'member_birth_year')
4 geo-location types('start_station_latitude', 'start_station_longitude', 'end_staion_latitude', 'end_station_longitude')
5 categorical types('start_station_id', 'end_station_id', 'bike_id', 'user_type', 'member_gender')
2 object types('start_station_name', 'end_station_name')
1 boolean type('bike_share_for_all_trip). The boolean type variable is 'bike_share_for_all_trip' which denotes whether the rider is enrolled in the "bike_share_for_all" program for low income households.

>Data Wrangling performed:
After priliminary data wrangling, the dataset got reduced to 174.9K from 183.4K. The dataset originally contained 16 features out of which 12 features are of variables of interest.
I removed entries with missing data. Split the dataset into two categories based on age with condition being age<=50 and age>50.
Created a new variable called duration_min from duration_sec for more readability


## Summary of Findings

> As expected, the age is skewed to the right with majority of the people being in the age group between 20 to 50 years and less people above 50 years
> The median age for the group(duration > 50 mins) is higher than the median age for the group(duration < 50 mins).
For group normal, age above 100 years is present. This is really odd. Hence let us remove entries that has age greater than 80 years
> there are more number of male numbers in both the categories than female numbers
> It looks like there are very less customer based users than subsriber based users in the group(duration <= 50 mins) and less difference in customers and subsribers in the group(duration > 50)
> As expected, In the group where duration < 50 mins, most of the rides have ocurred in the week days. The reasons might be work and local commutation, etc. For the group where duration > 50 mins, most of the rides have ocurred in the weekends. The reasons I can think of is recreational activities like bike rides, etc
> most number of rides ocurred in 28th in the normal group and on 17th in the extreme group
> For the normal group, the distribution looks bimodal. It is clear that most bike rides occur during morning and evening work commutation peak times
For the extreme group, the distribution looks normal with peak ocurring at 1pm
> he duration_min took on a large number of values and had a long tail. Hence I applied log tranformation. Under log transformation, the distribution looked normal with the peak ocurring around 9 mins.
> When investigating the age feature, a number of extreme values were discovered. For safety, I decided to split the dataframe into two dataframes one with age group under 80 and other with age group above 80 years.
> I expected a strong correlation between duration and age, but the investigation showed there exists no correlation between age and duration. While certainly there is large number of male users than female and other users, the female median ride duration stands higher than the other categories. Customer type users intend to have more median travel duration than subscriber type users. Time duration during weekends tend to have more median duration than the weekdays. istribution is multimodal with peaks ocurring at 2am, 8am, 11am, 4pm of the day. Unsuprisingly these are the peak hours of work commutation.
> Across week days, the bike rides peak at 8 to 9 am and 4 to 5pm. Interestingly this does not happen in the weekends. Though the number of subscribers making rides is higher, the customer intends to have high median duration. However this needs further analysis which can done via multivariate exploration
> Relationship was found one numerical variable(duration_min) and three categorical variables(dayofweek, hourofday and user_type). On an average, customer intend to travel more than the subcriber type user. The customer travels significantly during the weekends than the weekdays. The number of susbscribers travelling in the weekdays is larger. During weekdays the peak is seen at 8 to 9 am and at 4 to 5pm which appears to be peak hours of office commuting.


## Key Insights for Presentation

> In the presentation, I intend to show how variables are associated with the duration
> In the first visual, I intend to show how the duration is associated with age
> In the Second visual, I intend to show how the duration is associated with gender
> In the third visual, I inted to show how the duration is associated with day of week, hour of day and user_type