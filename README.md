# **Case Study: Google Data Analytics Cyclistic Bike-Share Analysis**

**Capstone Course:** [Complete a Case Study](https://www.google.com/url?q=https://www.coursera.org/learn/google-data-analytics-capstone)

**Table of Contents**
- Introduction
- Citations & Sources
- Background
- Ask
- Prepare
- Process
- Analyze
- Share
- Act

# **Introduction**

In this case study, I will undertake various tasks typical of a junior data analyst at the fictional company, Cyclistic. I will use the data analysis process steps of Ask, Prepare, Process, Analyze, Share, and Act to address the key business questions.

# **Citations & Sources:**

**Source:** [Divvy Trip Data](https://divvy-tripdata.s3.amazonaws.com/index.html) files: [Divvy Trips 2019 (Quarter 1)](https://divvy-tripdata.s3.amazonaws.com/Divvy_Trips_2019_Q1.zip) and [Divvy Trips 2020 (Quarter 1)](https://divvy-tripdata.s3.amazonaws.com/Divvy_Trips_2020_Q1.zip)

**Data Visualizations:** [Tableau](https://public.tableau.com/authoring/Google-Data-Analytics-Capstone-Cyclistic-Case-Study/Dashboard1#1) & [R Studio](https://posit.cloud/content/8703911?idle=1726802544442)

# **Background**

**About Cyclistic**

In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown
to a fleet of 5,824 bicycles that are geotracked and locked into a network of 692 stations
across Chicago. The bikes can be unlocked from one station and returned to any other station
in the system anytime.


Until now, Cyclistic’s marketing strategy relied on building general awareness and appealing to
broad consumer segments. One approach that helped make these things possible was the
flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships.
Customers who purchase single-ride or full-day passes are referred to as casual riders.
Customers who purchase annual memberships are Cyclistic members.


Cyclistic’s finance analysts have concluded that annual members are much more profitable
than casual riders. Although the pricing flexibility helps Cyclistic attract more customers,
Moreno believes that maximizing the number of annual members will be key to future growth.
Rather than creating a marketing campaign that targets all-new customers, Moreno believes
there is a solid opportunity to convert casual riders into members. She notes that casual riders
are already aware of the Cyclistic program and have chosen Cyclistic for their mobility needs.


Moreno has set a clear goal: Design marketing strategies aimed at converting casual riders into
annual members. In order to do that, however, the team needs to better understand how
annual members and casual riders differ, why casual riders would buy a membership, and how
digital media could affect their marketing tactics. Moreno and her team are interested in
analyzing the Cyclistic historical bike trip data to identify trends.

**Scenario**

I am taking on the role of a junior data analyst within the marketing team at Cyclistic. The director of marketing believes that increasing the number of annual memberships is crucial for the company’s future success. To achieve this, my team aims to understand the differences in how casual riders and annual members use Cyclistic bikes. Using these insights, we will develop a new marketing strategy to convert casual riders into annual members. However, before we proceed, our recommendations need approval from the stakeholders, the Cyclistic executives, which means they must be supported by compelling data insights and professional data visualizations.


# **Ask**

**Goal**
Come up with marketing strategies to convert casual riders to members.

**Business task**
Analyze historical bike trip data to identify trends in how annual members and casual riders use Cyclistic bikes differently.

**Analysis Questions**
Three questions that will guide the future marketing program:

1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

Moreno has assigned me the first question to answer: How do annual members and casual riders use Cyclistic bikes differently?

By performing the “Ask, Prepare, Process, Analyze, Share, Act” framework on the data, we can initially identify broad patterns emerging within the two distinct groups. Understanding these differences will enable us to develop more precise customer profiles for each segment. These insights will empower the marketing analytics team to craft high-quality, targeted marketing strategies aimed at converting casual riders into members. For the Cyclistic executive team, these insights will be instrumental in maximizing the number of annual members and driving future growth for the company.

# **Prepare**

**Data Source**

Using data provided by Cyclistic to analyze data and identify trends from both 2019 Q1 and 2020 Q1 available from the divvy trip data in the source section that was made available by Motivate International Inc. user their [Data License Agreement](https://divvybikes.com/data-license-agreement). Because this data was organized in R, only Q1 of 2019 and 2020 were readable for the capstone and will not contain Q2, Q3, or Q4.

This data is public and can be used to gain insights of how different user types use bikes from Cyclistic. This data takes into account data privacy by excluding personally identifiable information. No data including names or financial information will be provided to ensure security as well as prohibit any ability to connect the user. This however will bring up issues like determining if the user is nearby one of the serviced areas or if they have made multiple purchases previously. 

In terms of bias and credibility, the data sources is mostly using **ROCCC** as

1. **Reliable and original:** the public data contains accurate, complete and unbiased info on Cyclistic’s historical bike trips that comes from the primary source that allows us to explore how different customer types are using Cyclistic bikes.
2. **Comprehensive and current:** the source contains data needed to understand the different ways members and casual riders use Cyclistic bikes. However, the data we are using is 4 to 5 years old which is a significant time passed to look at more current files. Though the data is not too old that it still can be considered current enough for our analysis.
3. **Cited:** Because these data sources are publicly provided by Cyclistic it can be referenced easily and we know where the source came from.

**Data Information**
The data is externally stored in the cloud, utilizing the CSV format to manage large datasets. As first-party data, it is inherently more reliable, being original and unaltered by secondary or tertiary sources. It is distributed under a license and excludes Personally Identifiable Information (PII), ensuring the security of customer data.

**Data Acquisition**
Datasets for Q1 of 2019 and 2020 were downloaded from the cloud and stored locally on my hard drive. Subsequently, they were imported into Google Drive for examination in Google Sheets and further imported into R Studio for processing. The data was then exported to Tableau for visualization.

**Data Identification**
The process involves evaluating IDs, locations, ride lengths, and dates. Filters are applied to identify duplicate or missing values. The data is sorted to detect inconsistent formats and columns.

**Data Organization**
The two files used have the naming convention Divvy_Trips_YYYY_Q1. This includes the months of January, February, and March. 2019 used several different columns with some being the same as 2020 but with different column names that were edited later to match so that the two years could be compared. Such examples were “from_station_id” in 2019 became “start_station_id”

![file-structure](https://github.com/user-attachments/assets/448ebb3d-0402-4b99-a153-b7bb444c3f21)

The data is structured and organized in rows and columns. Each row represents one trip, and each trip has a unique field called the ride ID. You can see the fields here:

        ride_id
        rideable_type
        started_at
        ended_at
        start_station_name
        start_station_id
        end_station_name
        end_station_id
        start_lat
        start_lng
        end_lat
        end_lng
        member_casual

# **Process**

As part of the Process stage, it is imperative to cleanse the data to ensure its accuracy and eliminate any incomplete entries. Additionally, it is crucial to maintain consistency across all data elements, such as column names. This meticulous preparation will facilitate the subsequent Analyze stage, where we will delve into the data to uncover any intriguing insights.

**Tools**
We have meticulously selected tools to perform specific tasks, as outlined below:

* **Google Sheets:** For initial data inspection using pivot tables and graphs, as well as minor analyses.
* **R Studio:** To execute scripts for cleaning, manipulating, transforming, and organizing the dataset, thereby initiating the analysis process.
* **Tableau:** For creating comprehensive data visualizations.

**R Studio Packages**
* **tidyverse:** For data importation and wrangling.
* **libridate:** For handling date functions.
* **ggplot:** For data visualization.

**Step 1: Combine & Explore Data - Perform small process of data in Google Sheets combining and minor analysis exploration**

1. Open each .csv file in Google Sheets and save it to the appropriate subfolder.

2. Open your spreadsheet and create a column called ride_length.

* Calculate the length of each ride by subtracting the column started_at from the column ended_at (for example, =D2-C2).
* Format as time
* Format > Cells > Time > HH:MM:SS.

3. Create a column called day_of_week

* Calculated the day of the week that each ride started using the WEEKDAY command (example: =WEEKDAY(C2,1))
* Formatted as a NUMBER with no decimals
* Format > Cells > Number (no decimals) > 1,2,3,4,5,6,7
* Note: 1 = Sunday and 7 = Saturday

5. Where relevant, make columns consistent and combine them into a single worksheet.

6. Clean and transform your data to prepare for analysis.

* Select Columns and apply filters
* Go to each column and filter out blank data

7. Conduct descriptive analysis.

* Ride lengths are longer on Thursday and Friday and that casuals have longer ride lengths on average than members

8. Run a few calculations in one file to get a better sense of the data layout.

* Calculate the mean of ride_length
* Calculate the max ride_length
* Calculate the mode of day_of_week

9. Create a pivot table to quickly calculate and visualize the data. 

* Calculate the average ride_length for members and casual riders. Try rows = member_casual; Values = Average of ride_length.
* Calculate the average ride_length for users by day_of_week. Try columns = day_of_week; Rows = member_casual; Values = Average of ride_length.
* Calculate the number of rides for users by day_of_week by adding Count of trip_id to Values.

10. Open another file and perform the same descriptive analysis steps.

* When doing so, noticed a trend where thursdays were showing a higher number of ride lengths

11. Save files into one Google Sheet to further process in R Studio.

**Step 2: Clean Data - Import data from Google Sheets to R Studio and clean futher**

1. Start a New Workspace and Upload Files

        "Divvy_Trips_2019_Q1.csv"
        "Divvy_Trips_2020_Q1.csv"

2. Install Packages

```r
install.packages(tidyverse)
library(tidyverse)  #helps wrangle data
# Use the conflicted package to manage conflicts
library(conflicted)

# Set dplyr::filter and dplyr::lag as the default choices
conflict_prefer("filter", "dplyr")
conflict_prefer("lag", "dplyr")
```

3. Collect Data

```r
# Upload Divvy datasets (csv files) here
q1_2019 <- read_csv("Divvy_Trips_2019_Q1.csv")
q1_2020 <- read_csv("Divvy_Trips_2020_Q1.csv")
```

4. Wrangle Data and Combine Into A Single File

```r
# Compare column names each of the files
# While the names don't have to be in the same order, they DO need to match perfectly before we can use a command to join them into one file
colnames(q1_2019)
colnames(q1_2020)

# Rename columns  to make them consistent with q1_2020 (as this will be the supposed going-forward table design for Divvy)

(q1_2019 <- rename(q1_2019
                   ,ride_id = trip_id
                   ,rideable_type = bikeid
                   ,started_at = start_time
                   ,ended_at = end_time
                   ,start_station_name = from_station_name
                   ,start_station_id = from_station_id
                   ,end_station_name = to_station_name
                   ,end_station_id = to_station_id
                   ,member_casual = usertype
))

# Inspect the dataframes and look for incongruencies
str(q1_2019)
str(q1_2020)

# Convert ride_id and rideable_type to character so that they can stack correctly
q1_2019 <-  mutate(q1_2019, ride_id = as.character(ride_id)
                   ,rideable_type = as.character(rideable_type)) 

# Stack individual quarter's data frames into one big data frame
all_trips <- bind_rows(q1_2019, q1_2020)#, q3_2019)#, q4_2019, q1_2020)

# Remove lat, long, birthyear, and gender fields as this data was dropped beginning in 2020
all_trips <- all_trips %>%  
  select(-c(start_lat, start_lng, end_lat, end_lng, birthyear, gender,  "tripduration"))
```

5. Clean up and add data to prepare for analysis

```r
# Inspect the new table that has been created
colnames(all_trips)  #List of column names
nrow(all_trips)  #How many rows are in data frame?
dim(all_trips)  #Dimensions of the data frame?
head(all_trips)  #See the first 6 rows of data frame.  Also tail(all_trips)
str(all_trips)  #See list of columns and data types (numeric, character, etc)
summary(all_trips)  #Statistical summary of data. Mainly for numerics

# There are a few problems we will need to fix:
# (1) In the "member_casual" column, there are two names for members ("member" and "Subscriber") and two names for casual riders ("Customer" and "casual"). We will need to consolidate that from four to two labels.
# (2) The data can only be aggregated at the ride-level, which is too granular. We will want to add some additional columns of data -- such as day, month, year -- that provide additional opportunities to aggregate the data.
# (3) We will want to add a calculated field for length of ride since the 2020Q1 data did not have the "tripduration" column. We will add "ride_length" to the entire dataframe for consistency.
# (4) There are some rides where tripduration shows up as negative, including several hundred rides where Divvy took bikes out of circulation for Quality Control reasons. We will want to delete these rides.

# In the "member_casual" column, replace "Subscriber" with "member" and "Customer" with "casual"
# Before 2020, Divvy used different labels for these two types of riders ... we will want to make our dataframe consistent with their current nomenclature
# N.B.: "Level" is a special property of a column that is retained even if a subset does not contain any values from a specific level
# Begin by seeing how many observations fall under each usertype
table(all_trips$member_casual)

# Reassign to the desired values (we will go with the current 2020 labels)
all_trips <-  all_trips %>% 
  mutate(member_casual = recode(member_casual
                                ,"Subscriber" = "member"
                                ,"Customer" = "casual"))

# Check to make sure the proper number of observations were reassigned
table(all_trips$member_casual)

# Add columns that list the date, month, day, and year of each ride
# This will allow us to aggregate ride data for each month, day, or year ... before completing these operations we could only aggregate at the ride level
# https://www.statmethods.net/input/dates.html more on date formats in R found at that link
all_trips$date <- as.Date(all_trips$started_at) #The default format is yyyy-mm-dd
all_trips$month <- format(as.Date(all_trips$date), "%m")
all_trips$day <- format(as.Date(all_trips$date), "%d")
all_trips$year <- format(as.Date(all_trips$date), "%Y")
all_trips$day_of_week <- format(as.Date(all_trips$date), "%A")

# Add a "ride_length" calculation to all_trips (in seconds)
# https://stat.ethz.ch/R-manual/R-devel/library/base/html/difftime.html
all_trips$ride_length <- difftime(all_trips$ended_at,all_trips$started_at)

# Inspect the structure of the columns
str(all_trips)

# Convert "ride_length" from Factor to numeric so we can run calculations on the data
is.factor(all_trips$ride_length)
all_trips$ride_length <- as.numeric(as.character(all_trips$ride_length))
is.numeric(all_trips$ride_length)

# Remove "bad" data
# The dataframe includes a few hundred entries when bikes were taken out of docks and checked for quality by Divvy or ride_length was negative
# We will create a new version of the dataframe (v2) since data is being removed
# https://www.datasciencemadesimple.com/delete-or-drop-rows-in-r-with-conditions-2/
all_trips_v2 <- all_trips[!(all_trips$start_station_name == "HQ QR" | all_trips$ride_length<0),]
```

6. Conduct Descriptive Analysis

```r
# Descriptive analysis on ride_length (all figures in seconds)
mean(all_trips_v2$ride_length) #straight average (total ride length / rides)
[1] 1189.459
median(all_trips_v2$ride_length) #midpoint number in the ascending array of ride lengths
[1] 539
max(all_trips_v2$ride_length) #longest ride
[1] 10632022
min(all_trips_v2$ride_length) #shortest ride
[1] 1

# You can condense the four lines above to one line using summary() on the specific attribute
summary(all_trips_v2$ride_length)
    Min.  1st Qu.   Median     Mean  3rd Qu.     Max. 
       1      331      539     1189      912 10632022 

# Compare members and casual users
aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual, FUN = mean)
all_trips_v2$member_casual all_trips_v2$ride_length
1                     casual                5372.7839
2                     member                 795.2523
aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual, FUN = median)
all_trips_v2$member_casual all_trips_v2$ride_length
1                     casual                     1393
2                     member                      508
aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual, FUN = max)
all_trips_v2$member_casual all_trips_v2$ride_length
1                     casual                 10632022
2                     member                  6096428
aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual, FUN = min)
all_trips_v2$member_casual all_trips_v2$ride_length
1                     casual                        2
2                     member                        1
# See the average ride time by each day for members vs casual users
aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual + all_trips_v2$day_of_week, FUN = mean)
all_trips_v2$member_casual all_trips_v2$day_of_week all_trips_v2$ride_length
1                      casual                   Friday                6090.7373
2                      member                   Friday                 796.7338
3                      casual                   Monday                4752.0504
4                      member                   Monday                 822.3112
5                      casual                 Saturday                4950.7708
6                      member                 Saturday                 974.0730
7                      casual                   Sunday                5061.3044
8                      member                   Sunday                 972.9383
9                      casual                 Thursday                8451.6669
10                     member                 Thursday                 707.2093
11                     casual                  Tuesday                4561.8039
12                     member                  Tuesday                 769.4416
13                     casual                Wednesday                4480.3724
14                     member                Wednesday                 711.9838
# Notice that the days of the week are out of order. Let's fix that.
all_trips_v2$day_of_week <- ordered(all_trips_v2$day_of_week, levels=c("Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"))
# Now, let's run the average ride time by each day for members vs casual users
aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual + all_trips_v2$day_of_week, FUN = mean)
all_trips_v2$member_casual all_trips_v2$day_of_week all_trips_v2$ride_length
1                      casual                   Sunday                5061.3044
2                      member                   Sunday                 972.9383
3                      casual                   Monday                4752.0504
4                      member                   Monday                 822.3112
5                      casual                  Tuesday                4561.8039
6                      member                  Tuesday                 769.4416
7                      casual                Wednesday                4480.3724
8                      member                Wednesday                 711.9838
9                      casual                 Thursday                8451.6669
10                     member                 Thursday                 707.2093
11                     casual                   Friday                6090.7373
12                     member                   Friday                 796.7338
13                     casual                 Saturday                4950.7708
14                     member                 Saturday                 974.0730
# analyze ridership data by type and weekday
all_trips_v2 %>% 
+   mutate(weekday = wday(started_at, label = TRUE)) %>%  #creates weekday field using wday()
+   group_by(member_casual, weekday) %>%  #groups by usertype and weekday
+   summarise(number_of_rides = n()							#calculates the number of rides and average duration 
+             ,average_duration = mean(ride_length)) %>% 		# calculates the average duration
+   arrange(member_casual, weekday)								# sorts
`summarise()` has grouped output by 'member_casual'. You can override using the `.groups` argument.
# A tibble: 14 × 4
# Groups:   member_casual [2]
   member_casual weekday number_of_rides average_duration
   <chr>         <ord>             <int>            <dbl>
 1 casual        Sun               18652            5061.
 2 casual        Mon                5591            4752.
 3 casual        Tue                7311            4562.
 4 casual        Wed                7690            4480.
 5 casual        Thu                7147            8452.
 6 casual        Fri                8013            6091.
 7 casual        Sat               13473            4951.
 8 member        Sun               60197             973.
 9 member        Mon              110430             822.
10 member        Tue              127974             769.
11 member        Wed              121902             712.
12 member        Thu              125228             707.
13 member        Fri              115168             797.
14 member        Sat               59413             974.
```

**Findings**

**All riders (both casual and member):**
- Mean (seconds) - 1189
- Median (seconds) - 539
- Max (seconds) - 10632022
- Min (seconds) - 1

**Comparison (casual vs member):**

**Mean (seconds)**
- Casual - 5373
- Member - 795

**Median (seconds)**
- Casual - 1393
- Member - 508

**Max (seconds)**
- Casual - 10632022
- Member - 6096428

**Min (seconds)**
- Casual - 2
- Member - 1

```r
# Let's visualize the number of rides by rider type
all_trips_v2 %>% 
  mutate(weekday = wday(started_at, label = TRUE)) %>% 
  group_by(member_casual, weekday) %>% 
  summarise(number_of_rides = n()
            ,average_duration = mean(ride_length)) %>% 
  arrange(member_casual, weekday)  %>% 
  ggplot(aes(x = weekday, y = number_of_rides, fill = member_casual)) +
  geom_col(position = "dodge")

# Let's create a visualization for average duration
all_trips_v2 %>% 
  mutate(weekday = wday(started_at, label = TRUE)) %>% 
  group_by(member_casual, weekday) %>% 
  summarise(number_of_rides = n()
            ,average_duration = mean(ride_length)) %>% 
  arrange(member_casual, weekday)  %>% 
  ggplot(aes(x = weekday, y = average_duration, fill = member_casual)) +
  geom_col(position = "dodge")
```


7. Export Summpary File For Further Analysis

```r
# Create a csv file that we will visualize in Google Slides, Tableau, and my presentation software
# N.B.: This file location is for a Mac. If you are working on a PC, change the file location accordingly (most likely "C:\Users\YOUR_USERNAME\Desktop\...") to export the data. You can read more here: https://datatofish.com/export-dataframe-to-csv-in-r/
counts <- aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual + all_trips_v2$day_of_week, FUN = mean)
write.csv(counts, file = 'avg_ride_length.csv')
write.csv(all_trips_v2, file = 'all_trips_v2.csv')```

8. Continue to Analyze and Visualize in R Studio and Tableau

# **Analyze**

1. Analyze & Visualize Data in R Studio

```r
# Load the necessary libraries
library(ggplot2)

# Summarize the data to get min ride lengths for each rider type
summary_data <- all_trips_v2 %>%
  group_by(member_casual) %>%
  summarize(
    min_ride_length = min(ride_length, na.rm = TRUE)
  )

# Create the plot for min ride lengths
ggplot(summary_data, aes(x = member_casual, y = min_ride_length, fill = member_casual)) +
  geom_col() +
  labs(
    title = "Min Ride Lengths for Casual and Member Riders",
    x = "Rider Type",
    y = "Min Ride Length (hours)"
  ) +
  theme_minimal()

# Summarize the data to get max ride lengths for each rider type
summary_data <- all_trips_v2 %>%
  group_by(member_casual) %>%
  summarize(
    max_ride_length = max(ride_length, na.rm = TRUE)
  )

# Create the plot for max ride lengths
ggplot(summary_data, aes(x = member_casual, y = max_ride_length, fill = member_casual)) +
  geom_col() +
  labs(
    title = "Max Ride Lengths for Casual and Member Riders",
    x = "Rider Type",
    y = "Max Ride Length (hours)"
  ) +
```
![Rplot](https://github.com/user-attachments/assets/ee9853b0-23e1-4a56-9768-caa352afd45d)

![Rplot01](https://github.com/user-attachments/assets/d29bc446-3a94-4ced-b2f2-68cd543a8997)

**Step 2: Imported Data in Tableau for Further Visualization**

While we have some initial visuals from R Studio, let's enhance our analysis by creating additional, more sophisticated visualizations in Tableau, which is specifically designed for this purpose.

In this case, I made 4 graphs to compare the average daily ride lengths. With both a stacked line graph to show trends and a bar chart to show the average ride length for each day of the week to see the increased amount. I then created a chart to visually see the minimum and maximum average ride lengths of both member and casual riders.

![2024-09-19 22_24_42-Window](https://github.com/user-attachments/assets/9fd3a000-dca5-45e7-82f9-299285b70aef)

Additionally, I took the same CSV into google sheets to quickly do a further visual analysis that worked better for floating bar charts on the minimum and maximum averages as well as the shorted and longest ride length per user time

![2024-09-19 23_03_45-Window](https://github.com/user-attachments/assets/83744ef4-de73-461f-b578-e4653c47ed91)
![2024-09-19 23_02_32-Window](https://github.com/user-attachments/assets/d0a341f6-25a6-4e33-9e88-bbb404e286da)

# **Share**

Now time to share the findings with Google Sheets a presentation

**[Case Study Presentation](https://docs.google.com/presentation/d/1O6cmXXAkFVgYleRydRlN0Ze1TXTKl1dPoGuuK3VBxw0/pub?start=true&loop=true&delayms=5000)**

# **Act**

**Key Takeaways**

Findings from the data:

Highest Average Ride Lengths:
*  **Casual riders:** Thursdays, with an average ride length of >2 hours (notable outlier). Friday is the second highest.
*  **Member riders:** Slightly higher average ride lengths on weekends by >0.25 hours.

Daily Percentile Average Ride Lengths:
*  Casual Riders are approximately 75% or higher.
*  Significant increase in casual riders from Q1 2019 to Q1 2020.

Growth in Rider Numbers (2020):
*  Both casual and member riders have increased.
*  Higher percentage growth in casual riders, with fewer opting for membership.

Shortest to Longest Ride Length Range
*  Casuals went from 0.0006 hours to 2955.34 hours
*  Members went from 0.0003 hours to 1693.45 hours

Average Min & Max Ride Length (Casual vs Member)
*  Casuals ranged from 1.245 hours to 2.348 hours
*  Members ranged from 0.196 hours to 0.27 hours

**Recommendations**

Marketing wise in relation to the first phase, I have several recommendations with a focus on casual riders who have a behavior that mimics that of a member in terms of ride length and consistent daily usage. These users will have a ride length between over Min time length (>=X) and under a Max time length of (<=Y)

* The most effective route is to do marketing advertisements heavily on weekdays when the casual rider numbers are at their highest.
  * Especially around Thursday and Friday when the average casual rider duration length is also at its highest.

* Make aware to these casual riders the benefits of becoming a member. Such as cost saving by being on a subscription plan and accessibility and convenience for getting to their common routes of work, school, or other daily activities.
  * Mainly focus on those who are spending usually using more consistent and might be spending more.
  * I would recommend targeted social media on these specific riders if possible using the rider’s ID.

* Focus marketing around high density areas with the most casual riders. Preferably education institutions, businesses, malls, gyms, bike trails, concerts and other common gathering places that bike-share riders use.
  * I would also recommend social media advertisement in this geolocation, if they allow it
  * Additionally, I’d recommend in these bike share locations to use physical advertising at docking stations.
  * Lastly, a huge boost here is to see if there is any way to partner or work deals with these businesses or institutions to see if you can advertise with them. Whether that be posters in the school or promo deals that HR teams can hand out to employees or even retail businesses
    * I’d even use some government promotion routes for bike trails and parks to get them to promote healthy habits or at least environmentally-friendly promotion for those who may have interest.

* Use Net Promoter Scores and see which members score in the 90% or higher range as advertise to them a discount reward for recruiting new members with prompt codes.
    * Especially around weekends when members will get the advertisements and then promote to the casual riders when it comes to the weekdays when the casuals increase their usage.

**Conclusion**

Our analysis reveals distinct usage patterns between casual riders and annual members at Cyclistic. Casual riders exhibit significantly longer ride lengths, particularly on Thursdays and Fridays, and have shown substantial growth from 2019 to 2020. To capitalize on this, targeted marketing strategies should focus on converting high-usage casual riders into members by highlighting the benefits of membership, such as cost savings and convenience. By leveraging data-driven insights and strategic advertising, Cyclistic can effectively increase its annual membership base and drive future growth.

**Outro**

I appreciate all who took the time out of their day to review my case study that guided me through the full process of data analysis and how it relates to real world use using tools such as Google Sheets, R Studio, and Tableau. And eagerly look forward to adding this certificate to my resume and seeing what new opportunities may bring me in my career.
