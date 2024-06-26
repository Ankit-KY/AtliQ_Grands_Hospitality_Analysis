![image](https://github.com/Ankit-KY/AtliQ_Grands_Hospitality_Analysis/assets/148628279/9f77dde0-452a-4051-9d29-9a6837ad3898)



### Dashboard Link : https://app.powerbi.com/view?r=eyJrIjoiOWJlZGZiY2ItMmIzYS00ZTU2LTk5ZTMtZTZjZDYwOGM4MDViIiwidCI6ImRmODY3OWNkLWE4MGUtNDVkOC05OWFjLWM4M2VkN2ZmOTVhMCJ9

## Problem Statement

Atliq Grands has experienced declining market share and revenue due to competition and management decisions. The project focuses on revitalizing the business by leveraging hospitality analytics to make informed decisions. This dashboard helps the AtliQ Grands management to understand their customers better. It helps the management know if their customers are satisfied with their services. Through different ratings, they get to know their improvement area, & thus they can improve their services by identifying these area.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values.
- Step 5 : In the report view, under the view tab, theme was selected.
- Step 6 : Since the data contains various ratings, thus in order to represent ratings, a new visual was added using the three ellipses in the visualizations pane in report view. 
- Step 7 : Visual filters (Slicers) were added for four fields named "Property", "City", "Status", "Booking Platform" & "Months".
- Step 8 : Three card visuals were added to the canvas, one representing total revenue in millions, second representing occupancy% & last one  representing average rating.
           Using visual level filter from the filters pane, basic filtering was used.

Snap of KPI cards ,

![KPIs](https://github.com/Ankit-KY/AtliQ_Grands_Hospitality_Analysis/assets/148628279/7476834d-8910-453e-8467-27cf1a74a011)
- Step 9 : A line and clustered column chart was also added to the report design area representing the trends by week between occupancy% and average rating. While creating this visual, field named "Week no." was also added to the x_axis.

- Step 10 : Calculated column was created in which, days are grouped between weekends and weekdays.

for creating new column following DAX expression was written;
       
        day_type = 

        var wkd = WEEKDAY(dim_date[date])

        RETURN IF(wkd > 5, "Weekend", "Weekday")
Snap of new calculated column ,

![Dax Output](https://github.com/Ankit-KY/AtliQ_Grands_Hospitality_Analysis/assets/148628279/72a828fa-51c7-4a95-bdc6-f99642ea3bb3)

        
- Step 11 : New measure was created to find the booking% by room class.

Following DAX expression was written for the same,
        
        Booking % by Room class = 
        DIVIDE([Total bookings], CALCULATE([Totalbookings],ALL(dim_rooms[room_class])), 0)        
 
 - Step 12 : All the new measures were created for the analysis by using DAX expressions.
  
Snap of created measure.
 
![Key measures](https://github.com/Ankit-KY/AtliQ_Grands_Hospitality_Analysis/assets/148628279/8dac85b6-2757-4b3c-84f3-7f3cbbe427d8)

 
 - Step 18 : The report was then published to Power BI Service.

# Snapshot of Dashboard (Power BI Service)

![PowerBI Service](https://github.com/Ankit-KY/AtliQ_Grands_Hospitality_Analysis/assets/148628279/56d41b3a-3309-4881-8076-4334f34be3a8)


 
 # Report Snapshot (Power BI DESKTOP)

 
![Dashboard_upload](https://github.com/Ankit-KY/AtliQ-Grands-Hospitality-Analysis/assets/148628279/a678e5b7-3e96-4bbc-97bf-ae2d877e8e3a)

 # Data Model Snapshot

 
![Data modelling Atliq Grands](https://github.com/Ankit-KY/AtliQ-Grands-Hospitality-Analysis/assets/148628279/778a4989-6498-4057-bdb2-33bf4db3e62b)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

- The total revenue amounts to $1.69 billion, with an occupancy rate of 57.59% and a cancellation rate of 24.84%, alongside an average rating of 3.62.
- May exhibited the highest revenue generation compared to June and July, totaling $581.93 million.
- AtliQ Exotica demonstrates superior performance among all properties, achieving a revenue of $316 million, coupled with an average rating of 3.62. Its occupancy rate stands at 57.20%, while the cancellation rate is 24.49%.
- Delhi boasts the highest occupancy rate at 60.62%, despite having the lowest DSRN of 435, whereas Bangalore records the lowest occupancy rate at 55.68%.
- Mumbai leads in revenue generation, accruing $669 million, while Delhi trails with $290.92 million in revenue.
- Mumbai enjoys the highest RevPAR at $8.9K, whereas Hyderabad records the lowest at $5.4K.
- The majority of bookings originate from other sources, totaling 19K, followed by MakeYourTrip with 9K bookings.
- Luxury accommodations contribute 61.62% of the total revenue, outpacing the Business category, which contributes 38.82% of the $1.69 billion revenue.
- On weekends (Friday-Saturday), the occupancy rate is 7% higher than weekdays, though the variance in RevPAR is negligible.

# Recommendations

- Customer ratings can be enhanced through superior service, cleanliness, quality food, etc., as these factors directly influence bookings and revenue.
- Given the overall occupancy rate is 57.59%, the management team can dynamically adjust room prices in properties with low occupancy rates.
- Makeyourtrip is the second largest source of bookings (9K), but the cancellation rate is 25.03% across all cities and properties. The management team should address this issue, as it affects hotel rankings in search results, leading to decreased revenue and fewer bookings.
- The Average Daily Rate (ADR) remains consistent on weekdays and weekends, indicating an opportunity for dynamic pricing across all properties and platforms to generate additional revenue.


#### Do you have  any questions ? Feel free to ask anything….
### Connect with me on [linkedin.](https://www.linkedin.com/in/ankit-kumar-yadav3027)
