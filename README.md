# Google-Data-Analytics-Coursera

  The topic for this Capstone project is Cyclist-Bike Sharing Analysis. This is a case study for a fictional company completed with the data analysis process: 
  - ask
  - prepare
  - process
  - analyze
  - share
  - act 
  
  The final deliverable aims to find an answer to the question: "How to improve annual memberships for non-permanenet or one-time riders/users."
  I have highlighted the various tools used in the forthcoming steps:
  
  ## Ask
  
    Through this project, the difference in trends between rides of annual members and casual riders has been explored. The original business task remains the same : "How to convert casual riders to annual members" and this has been brought into the spotlight through identifying various trends between different columns in the dataset. 
    
    Key stakeholders are the CEO, Cyclists executive team and the marketing analysis team.
    
  ## Prepare
    
   ### Description of the Data
   
   The datasets are divided into monthly folders (zipped files). There are more than 1040000 rows in each dataset which is why it cannot be operated through Excel or Google Sheets. The files are from Apr-2020 till Feb-2022. A total of 23 Datasets.
   
   Once this dataset is cleaned and combined into one, with the below data dictionary, some trends can be explored to highlight the differences in trends between Annual Members and Casual Riders.
   
   The data looks credible although I might have considered a short dataset (after truncating each dataset till 1000 rows) to highlight the trends.
  
    The dataset provided follows the following dictionary:
    
    - S.No. : Just a serial number to distinguish an entry
    - ride_id : Every ride is unique with an alphanumeric 16 digit ID.
    - rideable_type : Categorical column with 3 categories: "Electric_Bike","Classic_Bike",Docked_Bike""
    - started_at : Time and Date at which the ride was started.
    - ended_at : Time and Date at which the ride ended.
    - start_station_name : Name of station at which the ride was started.
    - start_station_id : ID of starting station.
    - end_station_name : Name of station at which the ride ended.
    - end_station_id : ID of the station where the ride concluded.
    - start_lat
    - start lng
    - end lat
    - end lng
    - member_casual : Categorical column with 2 categories: "Member","Casual"
    
 ## Process
 
    Tools used: 
    
   - **R** for concatenation and cleaning
   - **Excel** for Feature Engineering and Cleaning
   - **Tableau** for Visual Analysis.
 
    The concatenation of all these monthly files into one file was done through R since the files were too big to load onto Excel or Google Docs. The code in R could be done with the help of a fellow peer - JAEYUN LIM. I have also linked his Kaggle code with this project since I am a beginner in R.
    
    Now, since the number of rows were too much I have truncated the data from every monthly file till a 1000 rows. The number of rows chosen was just random.
    
   ### Cleaning
   
   - Through R, the number of rows in each monthly dataset was reduced to 1000.
   - Through R, the date column was cleaned (After Concatenation) and brought to the same format as the other formats (Date Data-Type)
   - Through Excel, there were two more columns created.
     - Distance: Using the formula, ACOS [(sin(Lat_place_1*PI()/180)*sin(Lat_place_2*PI()/180)+cos(Lat_place_1*PI()/180)*cos(Lat_place_2*PI()/180)*
                 cos(Lon_place_2*PI()/180-Lon_place_1*PI()/180)) ] *3443.8985
     - Time_Per_Ride: Using the formula, (End_Time - Start_Time)*24*60 for minutes calculation.
   - Finally, through Tableau, any missing data, null, N/A values were removed when the visualization was made.
    
## Analyze

  The analysis is divided into 3 sections:
  - **Miscallaneous**
  - **Time**
  - **Distance**
  
  ### Miscallaneous
  
    This section is termed as "Miscallaneous", as the analysis would be focused at areas where time and distance are not a part of the metrics.
    
   - **Number of Rides per Day of the Week**:
        
        This metric is chosen to understand on which days are the rides the maximum and minimum. Also, a comparison of the types of rides on these days. Below is a visual form Tableau that highlights the same:
        
![Number_Of_Rides](https://user-images.githubusercontent.com/64735037/160237852-b79eadea-5049-47b0-a0d2-6bc2ed251a73.png)
        
   From this viz, it can be seen the **electric bike usage among Casual Riders is high** and has a major contribution to the overall rides. Although, this is not the same for Annual Members as the rides are mostly evenly distributed. 
        
   Also, **the number of rides is maximum on Saturday with Friday and Sunday following up closely among Casual riders**. The minimum is on the weekdays. For Annual members, the rides are more on the weekdays.
    
   - **Top - 21 Starting Stations**:
    
      This metric is chosen so as to find out the total contribution of the top-21 stations to the overall number of rides. The below visual highlights the same in terms of number of rides against the station name.
   
![image](https://user-images.githubusercontent.com/64735037/160238857-3323b26b-7c17-4e95-a6db-03ba554d44e3.png)

Thus, the highest contribution of the top station to the total number of rides is only 2.73%. The total contribution of the top-21 stations sums up to 17.1% only. Consequently, to expand in this direction with further bifurcation of type of bike and members would be futile.

  
    
    
  
