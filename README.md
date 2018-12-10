# CRAB Data Analysis

## Problem Statement

To compare the data gathered by BU Spark from Massachusetts Central Register, with the
state’s databases of minority-owned and women-owned businesses, to look for patterns in the
procurement database that may indicate the imbalance in participation by minority and
women-owned businesses, as well as the disparity in the number of RFPs and the awards.

## Datasets

We basically have 2 sources of data-  

1. From BU-Spark! - [http://necirspark.herokuapp.com]  
This data consists of all the contracts by the State and the businesses that they were
awarded to. We can analyze the disparity between the number of RFPs and the awards
from this database.

2. From [https://www.sdo.osd.state.ma.us/BusinessDirectory/BusinessDirectoryDownload.aspx]:  
  a. SDO (MBE, WBE, PBE and NPO) Directory Listing by Business Name  
  b. DBE Directory Listing by Business Name  
  c. ACDBE Directory Listing by Business Name  
This data consists of information about all the minority and women-owned businesses in
the state. We can compare this data with the contracts and their awards from the
previous dataset to analyze the participation of minority and women-owned businesses.

*In this report, we will primarily be working with the RFP and award datasets since we analyze the disparity in their numbers.*

## Approach

Our main challenge in this project was to deal with the dirty/empty and duplicate data in the given datasets. First, we basically produced cleaner datasets by removing all the duplicates and by not considering any RFPs where the project number was missing. We did this because we used the project numbers to match the RFPs and the awards from the two datasets.  

We also calculated the number of awards each contractor was awarded. Something that we observed here was that there were many contractors with multiple similar names, which again happened because the data was not entered in a uniform manner. For example, N.E.L Corporation, MA 01949 and NEL Corporation, MA, were considered as separate contractors. We needed to employ a separate algorithm to tackle this problem.  
