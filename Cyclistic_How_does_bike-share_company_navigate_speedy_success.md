---

Title: 'Case Study: How does a bike-share company navigate speedy success'
Author: 'Shruti Joshi'
Date: '2024-08-05'
---

# Case study: How does a bike-share company navigate speedy success

**Author:** Shruti Joshi <br>
**Date:** 2024-08-05



## Background

**Cyclistic:** A bike-share program that features more than 5,800 bicycles and 600 docking stations. Cyclistic sets itself apart by also offering reclining bikes, hand tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities and riders who can't use a standard two-wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use them to commute to work each day.

Customers who purchase single-ride or full-day passes are referred to as casual riders. Customers who purchase annual memberships are Cyclistic members. Cyclistic's finance analysts have concluded that annual members are much more profitable than casual riders.

Moreno (Director of Marketing) has set a clear goal: Design marketing strategies aimed at converting casual riders into annual members. In order to do that, however, the marketing analyst team needs to better understand how annual members and casual riders differ, why casual riders would buy a membership, and how digital media could affect their marketing tactics. Moreno and her team are interested in analyzing the Cyclistic historical bike trip data to identify trends.

## Step 1: Getting Information of The Task

### Business Task

To identify how do annual members and casual rider s use Cyclistic differently.

### Stakeholders

**Primary:** Lily Monero, Director of Marketing

**Secondary:** Cyclistic executive team (approves recommended marketing program)

## Step 2: Collection and Preparation of Data

### Data & Source Integrity

-   Data is stored in remote server [(url)](https://divvy-tripdata.s3.amazonaws.com/index.html) and provided by Motivate International Inc. and separated in chunks of querterly .csv files.

-   Data has been protected under data-privacy license mentioned here: [license](https://ride.divvybikes.com/data-license-agreement). This license states that this data has been provided "As is" as per bikeshares sole discretion. So reliability of the data can be vetted eventhough this has been provided by third party.

-   This data cannot be connected to the individual riders and their credit card numbers as unique rider ID has been used to record ride data.
  
### Observation
- There are 13 columns in the data files. These are: ride_id, rideable_type, started_at, ended_at, start_station_name, end_station_name, start_station_id, end_station_id, start_station, start_lat, start_lng, end_lat, end_lng, member_casual

- started_at and ended_at columns contains date-time data and formatted as YYYY-MM-DD HH:MM:SS format.

- start_station_id and end_station_id has discrepancy. Some of the IDs contain alphabets at the beginning (12 char length) and some contains only numbers (variable length 3-8).

- Although some of the csv files did not have start_station_name, start_station_id, end_station_name, end_station_id; these rows contain latitude and longitude data. This can be used to fill these empty values.

- member_casual column contains 2 types of membership data: member or casual.
  
## Step 3: Processing Data (Cleaning and Transformation)
Open new workbook
- Data -> Get Data ->From file-> From folder.
- Combined all data
- Remove ride_id,start_station_name,start_station_id,end_station_name,end_station_id,start_lat,start_lng,end_lat,end_lng.
- added couple of columns such as Month, Day, Hour and Ride Time = (ended_at - started_at)*24*60 -- this data gives us a minutes.
- Add additional Custom column
  --- use conditional formula:
  If Ride Time is less than or equals to 10 : Under 10
  Else if Ride time is less than equals to 30 : 10 to 30
  Else if Ride time is less than equals to 60 : 30 to 60
  Else over 60

  - This is the data what we got.
  ![image](https://github.com/user-attachments/assets/93b1e35a-8a9c-4569-98f5-f5a7b47ed6fd)

## Step 4: Analysis
I've use Pivot Table for analysis. 
**1. Total Count by Month**

![image](https://github.com/user-attachments/assets/60f33734-67bf-4f6d-bb69-fad5e8c4efa4)

**2. Casual_Member by Month**
   
   ![image](https://github.com/user-attachments/assets/c97bae4b-a15f-4898-9eb4-04c0bfdc5736)

**3. Casual's vs Member's by Month**

   ![image](https://github.com/user-attachments/assets/952f5342-0c4b-45a2-9920-cbdfbbe0314d)

**4. Casual's vs Member's by Day**

   ![image](https://github.com/user-attachments/assets/f9b41a72-6bbe-4051-9855-6c07d155631f)

**5. Data showing with Custom time frame.**

   ![image](https://github.com/user-attachments/assets/1645b699-cdd9-4ac7-a0c9-d553ed800162)

**6. Daily Ride Type Casual Vs Member**

  ![image](https://github.com/user-attachments/assets/5841217d-5bda-4bdd-a714-0b69f93aea52)


  ### Dashboard Using Excel
  ![image](https://github.com/user-attachments/assets/163cfca5-7bcf-4aad-bd43-cb4e792cfbca)

  

### Conclusion
In conclusion, there are several features / patterns can be observed from this data set. As per these observations following recommendations can be considered:

- During summer the number of bike rides by casual riders are more than the annual members. Moreover, average bike riding time is greater in case of casual riders. This can be a good opportunity to offer discounts to become annual members with cheap rides. The longer the subscription the lower will be the down payment.

- In order to attract working casual riders to use bikes for their daily ride to the workplace, special discounts can be offered to them for using electric bikes so that they can reach their workplace quickly without having to face hassle of busy public transport as well as saving some time in the morning and in the evening to spare.

Annual members can get discounts for riding average distance traveled by a casual member distance which can stir interest among the casual members to get annual subscription.







  

