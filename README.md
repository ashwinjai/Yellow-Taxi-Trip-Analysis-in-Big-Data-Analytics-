# Yellow Taxi Trip Analysis in Big Data Analytics

## Project Overview

## Problem Statement
The New York City Taxi & Limousine Commission (TLC) has furnished a comprehensive dataset documenting taxi trips within the city. This detailed trip-level dataset extends beyond a mere compilation of pickup and drop-off coordinates. <br>

The dataset encompasses various fields, capturing essential information such as pickup and drop-off dates and times, location coordinates for both the starting and ending points, trip distances, itemized fare details, rate classifications, payment methods, and driver-reported passenger counts. It is important to note that the data utilized in this context was meticulously collected and supplied to the NYC Taxi and Limousine Commission by authorized technology providers operating under the Taxicab & Livery Passenger Enhancement Programs (TPEP/LPEP). <br>

The primary objective of this dataset is to enhance comprehension of the taxi system, enabling the city of New York to optimize in-city commuting efficiency. Numerous exploratory questions can be posed to gain insights into the travel experience for passengers. <br>

### High Level Diagram 

![Untitled Diagram](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/9241ede8-1f08-4887-ab8a-2e64a72e203c)

### Cloud Setup

* New Project has been Created in GCP. Once Project-Page is up, Cluster has is Created using DataProc. <br>
* A cluster is configured by specifying the desired region, setting the cluster mode to single-node, opting for a higher configuration system, and configuring the image to Hadoop 2.10.<br>
* Bucket is Created and data is stored. <br>
* Cloud Storage Bucket is Mounted to Compute Engine Instance by Use of GCS Fuse tool. <br>
* A Directory is created in HDFS to store the NYC Dataset and moves the storage from local to HDFS Folder. At last, Start the HIVE services <br>

![Bucket_Data](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/8a4382a2-2e66-4775-8c2a-9f43b83cfc0e)

![image](https://github.com/ashwinjai/Yellow-Taxi-Trip-Analysis-in-Big-Data-Analytics-/assets/36980518/c351e569-d492-4235-9243-caebeb6a9667)













