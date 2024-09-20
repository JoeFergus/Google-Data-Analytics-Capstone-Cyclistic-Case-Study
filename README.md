# **Case Study: Google Data Analytics Cyclistic Bike-Share Analysis**

**Capstone Course:** [Complete a Case Study](https://www.google.com/url?q=https://www.coursera.org/learn/google-data-analytics-capstone)

# **Introduction**

In this case study, I will undertake various tasks typical of a junior data analyst at the fictional company, Cyclistic. I will use the data analysis process steps of Ask, Prepare, Process, Analyze, Share, and Act to address the key business questions.

# **Citations & Sources:**

**Source:** [Divvy Trip Data](https://divvy-tripdata.s3.amazonaws.com/index.html) {[files: Divvy Trips 2019 (Quarter 1)](https://divvy-tripdata.s3.amazonaws.com/Divvy_Trips_2019_Q1.zip) and [Divvy Trips 2020 (Quarter 1)](https://divvy-tripdata.s3.amazonaws.com/Divvy_Trips_2020_Q1.zip)}

**Data Visualizations:** [Tableau](https://public.tableau.com/app/profile/joseph.fergus7805/viz/bike-trip-case-study/Dashboard1#1) & R Studio ***8888888888888888888888888888888888

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

