# Google-Data-Analytics-Coursera

  The topic for this Capstone project is Cyclist-Bike Sharing Analysis. This is a case study for a fictional company completed with the data analysis process: 
  - ask
  - prepare
  - process
  - analyze
  - share
  - act 
  
  The final deliverable aims to find an answer to the question: "How to improve annual memberships for non-permanenet or one-time riders/users."
  There are two files added. The history of the R code used and the final dataset created.
  
  I would like to thank **JAEYUN LIM** for the R - Code on his Kaggle page. The concatenation of such heavy files would not have been possible in the timeframe given without his inputs. The link is shared below:
  
  https://www.kaggle.com/code/jaeyun7lim/google-data-analytics-capstone-project-bike-case/script
  
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
    
## Analyze and Share

**Note:** The analysis is only for the 2020-2021 months. 2022 months (Jan-Feb) was excluded.

  The analysis is divided into 2 sections:
  - **Miscallaneous**
  - **Time and Distance**
  
  ### Miscallaneous
  
    This section is termed as "Miscallaneous", as the analysis would be focused at areas where time and distance are not a part of the metrics.
    
   - **Number of Rides per Day of the Week**:
        
        This metric is chosen to understand on which days are the rides the maximum and minimum. Also, a comparison of the types of rides on these days. Below is a visual that highlights the same:
        
![Number_Of_Rides](https://user-images.githubusercontent.com/64735037/160237852-b79eadea-5049-47b0-a0d2-6bc2ed251a73.png)
![Number_Of_Rides(%)](https://user-images.githubusercontent.com/64735037/160283559-1764c1c1-7fbc-4022-a310-46ee34c80b3e.png)

        
   From this viz, it can be seen the **electric bike usage among Casual Riders is high** and has a major contribution to the overall rides. Although, this is not the same for Annual Members as the rides are mostly evenly distributed. 
        
   Also, **the number of rides is maximum on Saturday with Friday and Sunday following up closely among Casual riders**. The minimum is on the weekdays. For Annual members, the rides are more on the weekdays.
    
   - **Top - 21 Starting Stations**:
    
      This metric is chosen so as to find out the total contribution of the top-21 stations to the overall number of rides. The below visual highlights the same in terms of number of rides against the station name.
   
![image](https://user-images.githubusercontent.com/64735037/160238857-3323b26b-7c17-4e95-a6db-03ba554d44e3.png)

Thus, the highest contribution of the top station to the total number of rides is 2.73%. The total contribution of the top-21 stations sums up to 17.1% only. Consequently, to expand in this direction with further bifurcation of type of bike and members would be futile.

  ### Time and Distance
  
     The time metric has been analysed with respect to a High Level View, Weekday View and an Hour View.
     
   - **High Level View:**

      From the below visualization, for the years 2020 and 2021, casual members have had longer rides when using a docked bike as compared to an electric bike. ALthough, when the sum of minutes is compared, the trend is reveresed with casual riders riding more on electric bikes. **This indicates, there are shorter rides when an electric bike is used but quantitavely, the rides are more in number as compared to docked bike rides.**
      
![image](https://user-images.githubusercontent.com/64735037/160273830-7a82f06f-9bf4-49ba-b5bc-b78ff703d85d.png)

   - **Weekday View:**

      This view is divided into the casual and annual members. Below are the observations:
      
        - Casual and annual members ride more in terms of time-per-ride and quantity of rides on the **weekends**, apart from the exception of casual riders - They take more time per ride on Mondays when using a docked bike.
        - The point observed in the high level view section is confirmed here. For casual riders, The average times when using a docked bike is much higher as compared to other categories with an average of 56 minutes (just under an hour), while, the number of rides (however small) are much more when using an electric bike.

**Note:** The reference line in the below visuals represents the average per pane.

**Casual Riders**
![image](https://user-images.githubusercontent.com/64735037/160278719-e291e235-b8f4-4aa7-a6ed-046461489d92.png)

        - For annual members the trends for all types of bikes are quite constant. Usage on the weekends it slightly more than that on the weekdays.

**Annual Members**
![image](https://user-images.githubusercontent.com/64735037/160278730-d19949b3-8c6a-49d0-8e3d-0ecc6cb7f1be.png)

   - **Hour View:** 
  
      This view is divided into the casual and annual members. Below are the observations:
      
        - For casual riders, almost all metrics except Average_Time_Per_Ride, the trends indicate high usage post 1100 hours continuing well beyond 1800 hours, especially, **the use of Electric Bikes**.
        - The quanitity is confirmed by the number of rides taken and the distance travelled by causal riders when using the electric bike as compared to other types during these hours.
        - The average time per ride is more for docked bikes during specific afternoon hours.
        - Focus of casual riders is mostly on electric bikes and docked bikes.

**Casual Riders**
![image](https://user-images.githubusercontent.com/64735037/160280513-d639ed4c-ceba-4044-95f5-8c0325aa4a3c.png)

   - For annual members, the distribution is quite uniform and stable for all types of bikes. The peak times being the same as for casual riders.
   - **In terms of distance travelled and number of rides, classic bikes are used the most.**
 
**Annual Members**
![image](https://user-images.githubusercontent.com/64735037/160280653-67836538-e58e-4a19-84d1-7ec42e99303c.png)

   - **Distance Analysis** (All distance visuals are in meters)

   For distance, I have captured the quarter/month in which most distance was traveled by casual riders and annual members.
      
   - Since, casual riders use electric bikes more, from the below viz, it can be seen that they **travel more distances in the 3rd and 4th quarters**.

![image](https://user-images.githubusercontent.com/64735037/160281477-1c2f0965-4c4f-4d7e-9036-0bcf40f0aba4.png)

   Second, the map comparison is shown wherein **casual riders are seen to undertake more long distance rides as compared to annual members**.
      
      - Finally, the below maps are focused on electric bike usage. The distance is plotted with the starting lat long and the end lat long.
      - From the below visuals, it can be infered that casual riders travel more distances from annual riders. This is also confirmed with the specific visual wherein Sunday and Peak-Time - 16th hour are chosen as filters
      
**Casual Riders**

![image](https://user-images.githubusercontent.com/64735037/160282281-b0bbf923-02aa-41a9-96fe-6fbafc775202.png)

**Annual Members**

![image](https://user-images.githubusercontent.com/64735037/160282291-ee7183fd-ca25-4b5f-88ae-4ee013664d20.png)

Also, a more expanded filtered view below with the 16th Hour of Sunday for Casual riders and Annual members using electric bikes.

**Casual Riders**

![image](https://user-images.githubusercontent.com/64735037/160282416-80c5a976-9edb-43c4-89ca-ce07e9d422de.png)

**Annual Members**

![image](https://user-images.githubusercontent.com/64735037/160284356-f4916e90-4f45-407f-a6e5-dd47994a8d40.png)

### Summary

- **electric bike usage among Casual Riders is high**
- **the number of rides is maximum on Saturday with Friday and Sunday following up closely among Casual riders.** Casual and annual members ride more in terms of time-per-ride and quantity of rides on the **weekends.**
- **For casual riders, there are shorter rides when an electric bike is used but quantitavely, the rides are more in number as compared to docked bike rides.**
- **In terms of distance travelled and number of rides, classic bikes are used the most by annual members.**
- **For both member types, the trends indicate high usage post 1100 hours continuing well beyond 1800 hours.**
- **casual riders travel more distances in the 3rd and 4th quarters.**
- **casual riders are seen to undertake more long distance rides as compared to annual members**

## Act

The top - 3 recommendations based on the Summary in the Analyze and Share section are:

- A miles program can be constructed as a part of the annual membership only for electric bikes wherein free miles are offered the more distance travelled.
- An additional slab of membership can be considered. An example could be a program only for Q3 and Q4 (6 months) quarters with a group admission attached to it. (Example: couple program or a family program). This would be for electric bike users only.
- A special offer for weekends can be considered only for electric bike users in the annual membership program. A special hourly offer focussed on peak timings from 1500 - 1900 hours can be considered only for electric bikes.
- Casual riders ride more in number as compared to annual riders and also they predominantly use electric bikes, consequently, addition of charging stations and/or electric bikes, specially at the outskirts (infered from the distance analysis), can be considered if the budget permits. Special concessions to electic bikes users could be added in the annual membership as an attraction.

These conclusions would have changed if all rows of the datasets had been used.


  
