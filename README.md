# Delhivery 

## About Delhivery :
Delhivery is the largest and fastest-growing fully integrated player in India by revenue in Fiscal 2021. They aim to build the operating system for commerce, through a combination of world-class infrastructure, logistics operations of the highest quality, and cutting-edge engineering and technology capabilities.The Data team builds intelligence and capabilities using this data that helps them to widen the gap between the quality, efficiency, and profitability of their business versus their competitors.


## Column Profiling:
    •	data - tells whether the data is testing or training data
    •	trip_creation_time – Timestamp of trip creation
    •	route_schedule_uuid – Unique Id for a particular route schedule
    •	route_type – Transportation type
    o	FTL – Full Truck Load: FTL shipments get to the destination sooner, as the truck is making no other pickups or drop-offs along the way
    o	Carting: Handling system consisting of small vehicles (carts)
    •	trip_uuid - Unique ID given to a particular trip (A trip may include different source and destination centers)
    •	source_center - Source ID of trip origin
    •	source_name - Source Name of trip origin
    •	destination_cente – Destination ID
    •	destination_name – Destination Name
    •	od_start_time – Trip start time
    •	od_end_time – Trip end time
    •	start_scan_to_end_scan – Time taken to deliver from source to destination
    •	is_cutoff – Unknown field
    •	cutoff_factor – Unknown field
    •	cutoff_timestamp – Unknown field
    •	actual_distance_to_destination – Distance in Kms between source and destination warehouse
    •	actual_time – Actual time taken to complete the delivery (Cumulative)
    •	osrm_time – An open-source routing engine time calculator which computes the shortest path between points in a given map (Includes usual traffic, distance through major and minor roads) and gives the time (Cumulative)
    •	osrm_distance – An open-source routing engine which computes the shortest path between points in a given map (Includes usual traffic, distance through major and minor roads) (Cumulative)
    •	factor – Unknown field
    •	segment_actual_time – This is a segment time. Time taken by the subset of the package delivery
    •	segment_osrm_time – This is the OSRM segment time. Time taken by the subset of the package delivery
    •	segment_osrm_distance – This is the OSRM distance. Distance covered by subset of the package delivery
    •	segment_factor – Unknown field

# Problem Statement:
    * Indian states with source and destination delivery count
       * Destination state with  delivery count
       * Source state with  delivery count
    * Analaysing through destination places in each state Which place have more delivery ?
    * Analaysing through source places in each state Which place have more delivery?
    * Analaysing through cities in each state Which city have more delivery ?
    * Which month proceed more trip?
    * Which route type use more time to reach destination?
    * Which state has more source center?
    * Which state has more destination center?
    * Weekday with most delivery of the product
    * Actual time v/s Time which computes the shortest path
    * Feature engineering
       * Calculate the time taken between od_start_time and od_end_time as time_difference
    * Hypothesis
        * Compare the difference between time_difference and start_scan_to_end_scan.
        * Actual_time aggregated value and OSRM time aggregated value
        * Actual_time aggregated value and segment actual time aggregated value 
        * Osrm distance aggregated value and segment osrm distance aggregated value 
        * Osrm time aggregated value and segment osrm time aggregated value 
    * Find outliers in the numerical variables and check it using visual analysis
    * One-hot encoding of categorical variables
    * Normalize/ Standardize the numerical features using MinMaxScaler or StandardScaler

## Concept Used:
      •	Feature Creation
      •	Relationship between Features
      •	Column Normalization /Column Standardization
      •	Handling categorical values
      •	Missing values - Outlier treatment / Types of outliers




## Project Accomplishments and Process Overview
    1.	Basic data cleaning and exploration:
          o	Handle missing values in the data.
          o	Analyze the structure of the data.
          o	Try merging the rows using the hint mentioned above
    2.	Build some features to prepare the data for actual analysis. Extract features from the below fields:
          o	Destination Name: Split and extract features out of destination. City-place-code (State)
          o	Source Name: Split and extract features out of destination. City-place-code (State)
          o	Trip_creation_time: Extract features like month, year and day etc
    3.	In-depth analysis and feature engineering:
          o	Calculate the time taken between od_start_time and od_end_time and keep it as a feature. Drop the original columns, if required
          o	Compare the difference between Point a. and start_scan_to_end_scan. Do hypothesis testing/ Visual analysis to check.
          o	Do hypothesis testing/ visual analysis between actual_time aggregated value and OSRM time aggregated value (aggregated values are the values you’ll get after merging the rows on the basis of trip_uuid)
          o	Do hypothesis testing/ visual analysis between actual_time aggregated value and segment actual time aggregated value (aggregated values are the values you’ll get after merging the rows on the basis of trip_uuid)
          o	Do hypothesis testing/ visual analysis between osrm distance aggregated value and segment osrm distance aggregated value (aggregated values are the values you’ll get after merging the rows on the basis of trip_uuid)
          o	Do hypothesis testing/ visual analysis between osrm time aggregated value and segment osrm time aggregated value (aggregated values are the values you’ll get after merging the rows on the basis of trip_uuid)
          o	Find outliers in the numerical variables (you might find outliers in almost all the variables), and check it using visual analysis
          o	Handle the outliers using the IQR method.
          o	Do one-hot encoding of categorical variables (like route_type)
          o	Normalize/ Standardize the numerical features using MinMaxScaler or StandardScaler
          
