# YouTube And Spotify DataAnalysis

# Overview

The "YouTube and Spotify Data Analysis" project is an exploration of user behavior and trends on two of the most popular streaming platforms: YouTube and Spotify. By leveraging data from these platforms, this analysis aims to uncover valuable insights into user preferences, content trends, and engagement patterns.

# Technologies Used

  * Python: Python was used for data preprocessing, analysis, and visualization. Libraries such as Pandas, NumPy, and Matplotlib were utilized for these tasks.

  * SQL: SQL queries were employed to extract and manipulate data from the MySQL database, which serves as the primary data source.

  * MySQL: MySQL was used to store and manage the structured data, making it accessible for analysis and reporting.

  * Tableau: Tableau was utilized to create interactive and insightful data visualizations, allowing for a better understanding of the analyzed data.

  * Power BI: Power BI was used to generate interactive reports and dashboards, enabling stakeholders to explore the project's findings.

    

# Project Highlights

 * Data Preparation: Describe any significant data preprocessing steps, such as data cleaning, transformation, or feature engineering.
 
 * SQL Queries: Highlight key SQL queries or operations performed on the MySQL database.

 * Visualization: Mention the main visualizations created using Tableau and Power BI, and how they contribute to the project's objectives.

 * Insights: Summarize the key insights or findings derived from the analysis.

# Folder Structure

 * DataBase : This folder contain the Youtube and Spotify Data.

 * Power Bi : This folder contains the 'POWER BI' works for visualizations.

 * Python Work : This folder contains the 'PYTHON WORK' for cleaning the DataBase.

 * SQL Work : This folder contains the 'SQL WORK' .

 * Tableau DashBoard : This folder contans the 'TABLEAU WORK' for visualizations.

 * Cleaned DataBase : This folder contains the cleaned data which we use for this Performing SQL Work.


# SQL WORKS (Some of Sql Queries) --

  1. list of unique Artist list 
  
  * Query : ```select distinct Artist  from Spotify_Youtube;```
    
  2. Count total number of Unique Artist
  * Query : ```select count(distinct Artist) as Artist  from Spotify_Youtube;```

  3. Couting the number of tracks for each album
  
  * Query : ```select Album_type ,( count(Track) ) as 'Total Tracks' from Spotify_Youtube
group by Album_type```

  4. Total  Album

  * Query : ```select sum(totaltracks) as totaltracks
from (select Album_type , count(*) as totaltracks
from Spotify_Youtube
group by Album_type
) as subquery;```

  5. Album Contribution

  * Query : ```select Album_type, 
count(*)  as 'Total Tracks'
,
concat(cast(((count(*)*1.0 / 
(
select sum(totaltracks) as totaltracks
from (select count(*) as totaltracks
from Spotify_Youtube
) as subquery
) *1.0)*100)as decimal(10,2))
, 
'%')
as Precentage
from Spotify_Youtube
group by Album_type```

  6. Top 10 Artist  basis on Views On Youtube

  * Query : ```select top 10 Artist , sum(Views) as 'Total number of views' from Spotify_Youtube
group by Artist
order by sum(Views) desc```

  7. Top 10 Artist  basis on Stream On Spotify

  * Query : ```select top 10 Artist , sum(Duration_minute) as 'Total number of views' from Spotify_Youtube
group by Artist
order by sum(Duration_minute) desc```

  8. Top 10 commented songs On Youtube

  * Query : ```select top 10 Track , Artist, Views , Album,Uri , Channel, Comments as 'Total number of Comments' from Spotify_Youtube
order by Comments desc```

  9. Top 10 Liked songs On Youtube

  * Query : ```select top 10 Track , Artist,  Album,Uri , Channel, Likes as 'Total number of Likes' from Spotify_Youtube
order by Likes desc```

  10. Top 10 channel Basis on views

  * Query : ```select top 10  Channel,sum(Views) as 'Total number of views' from Spotify_Youtube
group by Channel
order by sum(Views) desc```

  11. Top 10 highest duration songs

  * Query : ```select  top 10   Track ,concat(cast(Duration_minute as decimal (10,2)) ,'Minute')as Total_Minute from Spotify_Youtube
group by Track,Duration_minute
order by Duration_minute desc```

  12. Total Licenced songs

  * Query : ```select count(Licensed) as 'Total Licensed Songs'  from Spotify_Youtube
where Licensed=1```

  13. Total UnLicenced songs

  * Query : ```select count(Licensed) as 'Total UnLicensed Songs'  from Spotify_Youtube
where Licensed=0```

  14. Average time duration for Tracks

  * Query : ```select 
concat(cast((sum(Duration_minute) / 
count(*)) as decimal(10,2)) ,' Minute')
as 'Average Time Duration'
from Spotify_Youtube```


# Creating Visualizations

# Tableau DashBoard :
  
  1. Average Play duration
     
      ![Average Play duration](https://github.com/user-attachments/assets/7441731c-c647-4f12-9dee-bd3313ebbd4d)

  3. licensed And Unliensed track
     
       ![licensed unliensed track](https://github.com/user-attachments/assets/b9deaa79-20ea-4cca-b7aa-6ac198d197fb)
     
  4.  Top 5 artist on Spotify

     
      ![top 5 artist on Spotify](https://github.com/user-attachments/assets/e54d79f8-f8e4-4ea3-8cd6-cff79563c3e0)

  5. Top 5 artist on youtube

     ![top 5 artist on youtube](https://github.com/user-attachments/assets/ccc035bd-3dbd-4bd2-836e-91e87fc596da)

  6. Top 5 channel on youtube

       ![top 5 channel on youtube](https://github.com/user-attachments/assets/16ae71e1-9e96-490e-982b-898c3183e65b)

  7. Top 5 commented songs

      ![top 5 commented songs](https://github.com/user-attachments/assets/99f8e8a9-81b1-4a08-9799-56caa8dd73e1)

  8. Top 5 liked Songs

      ![top 5 liked](https://github.com/user-attachments/assets/148d34f0-1a86-461a-b5ea-5f294ab565ab)

  9. Total Artist

        ![Total Artist](https://github.com/user-attachments/assets/4c91d6a1-da44-43fc-98e0-6fcd4d0f67e6)

  
  10. Total play duration

      ![total play duration](https://github.com/user-attachments/assets/4904835a-0ded-41b8-b7d7-5529c820d17a)

  11. Total Tracks

      ![Total Tracks](https://github.com/user-attachments/assets/d47d18f7-90c0-4f12-8747-ae72e86fb7b5)

  12. Track of each Album

      ![Track of each Album](https://github.com/user-attachments/assets/ce89b3aa-379e-4e8b-9df9-a5e51d66408c)

  13. Final Dashboard

      ![Final Dashboard](https://github.com/user-attachments/assets/a0257cb5-8f1a-4e15-aaa4-0c82414f2d8a)




 
  Note : It's dynamic dashboard .

# Power BI Dashboard

  ![dashboard](https://github.com/user-attachments/assets/818ef42f-1ba7-4c59-88da-49bde0f12e89)

  Note : It's dynamic dashboard .

# Contributions

Contributions and feedback are welcome. If you'd like to contribute to this project or report issues, please follow GitHub's standard procedures for pull requests and issue tracking.
