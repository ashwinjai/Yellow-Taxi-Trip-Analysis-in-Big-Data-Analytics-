# Yellow Taxi Trip Analysis in Big Data Analytics

## Project Overview: <br>

The Yellow Taxi Trip Analysis project aims to leverage Big Data Analytics to derive valuable insights from vast volumes of taxi trip data. By utilizing the power of Google Cloud Platform (GCP), Hadoop, and Hive, this project seeks to analyze and extract meaningful patterns, trends, and metrics from large-scale datasets related to Yellow Taxi trips in a given geographic area. <br>

## Problem Statement: <br>
The New York City Taxi & Limousine Commission (TLC) has furnished a comprehensive dataset documenting taxi trips within the city. This detailed trip-level dataset extends beyond a mere compilation of pickup and drop-off coordinates. <br>

The dataset encompasses various fields, capturing essential information such as pickup and drop-off dates and times, location coordinates for both the starting and ending points, trip distances, itemized fare details, rate classifications, payment methods, and driver-reported passenger counts. It is important to note that the data utilized in this context was meticulously collected and supplied to the NYC Taxi and Limousine Commission by authorized technology providers operating under the Taxicab & Livery Passenger Enhancement Programs (TPEP/LPEP). <br>

The primary objective of this dataset is to enhance comprehension of the taxi system, enabling the city of New York to optimize in-city commuting efficiency. Numerous exploratory questions can be posed to gain insights into the travel experience for passengers. <br>

## High Level Diagram: <br>

![Untitled Diagram](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/9241ede8-1f08-4887-ab8a-2e64a72e203c)

## Google Cloud Setup: <br>

* New Project has been Created in GCP. Once Project-Page is up, Cluster has is Created using DataProc. <br>
* A cluster is configured by specifying the desired region, setting the cluster mode to single-node, opting for a higher configuration system, and configuring the image to Hadoop 2.10.<br>
* Bucket is Created and data is stored. <br>
* Cloud Storage Bucket is Mounted to Compute Engine Instance by Use of GCS Fuse tool. <br>
* A Directory is created in HDFS to store the NYC Dataset and moves the storage from local to HDFS Folder. At last, Start the HIVE services <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/92d9ed2c-bc74-4407-99c8-e1e18be0ede8)


![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/c351e569-d492-4235-9243-caebeb6a9667)

## Methodology: <br>

**Ingestion-** Raw Yellow Taxi trip data will be ingested into GCS, ensuring durability and availability. <br>
**Processing-** Hadoop will be used for distributed processing, and MapReduce jobs will be developed to analyze and transform the data. <br>
**Storage-** Processed data will be stored in HDFS for further analysis and exploration. <br>
**Analysis-** Hive queries will be employed to perform SQL-like analysis on the stored data, allowing for the extraction of relevant information. <br>



## BigQuery: <br>

**1. An ORC (Optimized Row Columnar) table is built on top of Hadoop to access Apache Hive as it's compatible format** <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/e84adf8b-98e0-446f-871a-5b5eb0b38a06)

**2. Count the number of records** <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/91628356-efc7-4de2-a217-0f7a58f86db1)

There are in total 1174569 records. <br>

**3. Summarises the number of Total Passenger of each provider** <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/21c6538c-cee4-4109-83f1-812b831e73c3)

For vender_id-1 total record is 47026340 and for vender_id 2 is 64716535 and for vendor_id 4 is 491751. <br>

**4. Trip duration** <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/e53ecefc-e4fe-422e-be87-3fd63b295425)

We can see Data Quality issue <br>

**5. Fare Amount** <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/e35d0d16-1d03-4b81-b8bf-3b5ec4c97b1e)

the total erroneous(negative) count by vendor_id 2 is 73049 and it amounts to -712942.76 <br>

**6. Extra charged** <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/4e5f53a8-cf96-40b8-aa21-1d41855aac58)

Three are charging some unusual Extra charges with count of 334964 , 180547 , 2391. high numbers can be seen from Vendor_iD 2(Verifone inc) <br>

**7. MTA TAX** <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/7dade77b-e7bb-4568-a09b-0ec5ea978a5e)

mta_tax was  unusually charged, from vendor 2 and 1 with count of 71239  and 172 times and total of -35155 and 172 respectively. <br>

**8. TIP AMOUNT** <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/6c044771-0bbf-4b1f-976a-42b57e4b1e24)

tip_amount was unusually charged by only vendor 2,count is 785 times with total of -4188 <br>

**9. TIP AMOUNT IMPROVEMENT_SURCHARGE** <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/c80f2578-c268-45b3-8ac7-97896aaca25c)

improvement_surcharge was charged by only from vendor 2 and 4 and count is 73264 & 10 times with total of -10656.72 <br>

**10. Payment Type** <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/b7cdef99-f880-46fd-935e-3473c0043916)

Credit Card is most preferred choice. <br> 

**11. Overall average fare per trip** <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/644353fb-2afa-4ef9-990f-e551eebcfd33)

Average Tip mostly is 1.87. <br>

**12. The average tip with the 25th, 50th and 75th percentiles** <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/8f7a6710-b9b1-46fe-80f5-d17e80ab1a1d)

25th, 50th and 75th percentiles is repectively 0.0, 1.39, 2.44 and On an average is 1.87. <br>

**13. Extra Charge Variable** <br>

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/b9e8bb24-3399-46a1-b7a2-a6fd2ff62a21)

46.20% of trips happened when extra charge was levied or when there is no extra charge people travel more. <br>

## Conclusion: <br>

The Yellow Taxi Trip Analysis project, powered by GCP, Hadoop, and Hive, aims to revolutionize the way we analyze and derive insights from large-scale taxi trip data. We discovered anomalies or irregularities in taxi trip data. Further to this, we explored Insights into customer behavior and preferences based on historical trip patterns. <br>































