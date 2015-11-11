# Galway Park Locater API
#### Data Representation and Querying Project 2015
#### Declan Duffy
## Overview
This project will detail the locations of parks in Galway based on data recieved from https://data.gov.ie/data and provide the design and documentation for the dataset "Parks in Galway". The aim of this project is to provide the information for all the parks available in Galway city. This project will also be able to be updated with added information so more parks info will become readily available as Galway is an ever expanding city.
## About the data
This dataset was received in Comma Separated Values (CSV) format, and was downloaded from [*Parks in Galway City*] https://data.gov.ie/dataset/parks-in-galway-city. This CVS file contains 29 rows, a header row with 14 values. These Columns are: 
- **Object Id:** The ID assigned to each park in Galway
- **Number:** Number(s) assigned to each park based on size
- **Name:** Name associated with the given park
-  **Location:** The main section (most precise) of the address of the park
-  **Area of City:** The section in the city in which the park can be found
-  **Opening Hours:** How long the park will be open for
-  **Facilities:** What amenities are available in that park
-  **Description:** Anything extra about the park
-  **Lattitude:** The lattitude coordinates for the park
-  **Longitude:** The longitude coordinates for the park
-  **East Irish Transverse Mercator (ITM):** Irish Transverse Mercator (ITM) is the geographic coordinate system for Ireland. Therefore the East ITM refers to the coordinates in Galway city itself
-  **North Irish Transverse Mercator (ITM):** The North ITM refers to coordinates in Galway city itself 
-  **East Irish Grid reference system (IG):** In general, neither Ireland nor Great Britain uses latitude or longitude in describing internal geographic locations. Instead grid reference systems are in common usage. East IG therefore refers to coordinates in Galway city itself
-  **North Irish Grid reference system (IG):** North IG refers to coordinates in Galway city itself

## Design

## Methods
####HTTP Request Methods  
Method | Definitions
--------|--------------------------------
**GET** | Allows user to access data form the server and retreive it to your own device  
**HEAD** | Retrieve response header   
**POST** | Allows user to update data that is already at the server and have it recorded there for other users to see       
**PUT** | Allows user to send new data to the server and have it recorded there for other users to see   
**DELETE** | Deletes the data at the server

##Status Codes
Code | Definition | Code | Definition     
------|--------|--------|----------      
**200** | Works Ok | **202** | Works Very Well 
**301** | Moved Permanently  | **302**| Moved Temporarily 
**303** | Redirect to new location | **400** | Bad Request/ Unknown request 
**404** | Not Found - Deleted/Moved |  **405** | Invalid Method
**500** |  Server Error | **503** | Service Unavaiable  

## Live data

## Usefullness
