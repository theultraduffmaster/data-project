# Galway Park Locator API
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

###Search for park by name
This is a GET method

Replace Name with the name of any of the parks in Galway 

*http://www.galway.ie/galwayparklocatorapi/galway-parks/[Name]*   
E.G.
*http://www.galway.ie/galwayparklocatorapi/galway-parks/[RENMORE-PARK]*   

**JSON Results by Name** 
```json   
[{      
    "OBJECTID":"23",   
    "NUMBER":"16",   
    "NAME":"RENMORE PARK",   
    "LOCATION":"RENMORE, GALWAY",   
    "AREAOFCITY":"CITY-EAST",   
    "OPENINGHRs":"NO RESTRICTED OPENING HOURS",   
    "FACILITIES":"2 GAELIC PLAYING PITCHES, 2 SOCCER PLAYING PITCHES, PLANTING AREAS WITH FLOWERS, SHRUBS AND TREES.",   
    "DESCR":"LOCAL NEIGHBOURHOOD PARK",   
    "Lat":"53.276",   
    "Long":"-9.018",   
    "EastITM":"532136.258",   
    "NorthITM":"725529.593",   
    "EastIG":"132170.842",   
    "NorthIG":"225500.493"   
  },]   
  ```
  
###Search for park by Area
This is a GET method

Replace Area with the name of the Area in Galway 

*http://www.galway.ie/galwayparklocatorapi/galwayparks/[Area]*   
E.G.
*http://www.galway.ie/galwayparklocatorapi/galwayparks/[CITY-WEST]*   

**JSON Results by Area** 
```json   
[{      
    "OBJECTID":"23",   
    "NUMBER":"16",   
    "NAME":"BARNA - LOUGH RUSHEEN PARK",   
    "LOCATION":"BARNA ROAD, GALWAY",   
    "AREAOFCITY":"CITY-WEST",   
    "OPENINGHRs":"NO RESTRICTED OPENING HOURS",   
    "FACILITIES":"PEDESTRIAN WALKWAYS, CAR PARK/ BUS PARK, WOODLANDS, PICNIC AREA, PLANTING AREA WITH FLOWERS, SHRUBS AND TREES.",   
    "DESCR":"LOCAL NEIGHBOURHOOD PARK",   
    "Lat":"53.259",   
    "Long":"-9.131",   
    "EastITM":"524524.759",   
    "NorthITM":"723726.893",   
    "EastIG":"124557.707",   
    "NorthIG":"223697.361"   
  },]   
  ```
  
### Search for park by Opening Hours

This is a GET method

Replace Opening Hours with the time you want to look for

*http://www.galway.ie/galwayparklocatorapi/galwayparks/[OpeningHRs]*   
E.G.
*http://www.galway.ie/galwayparklocatorapi/galwayparks/[MON-SUN]*   

**JSON Results by Opening Hours** 
```json   
[{      
    "OBJECTID":"14",   
    "NUMBER":"14",   
    "NAME":"MILLENNIUM CHILDRENS PARK",   
    "LOCATION":"NEWCASTLE ROAD, GALWAY",   
    "AREAOFCITY":"CITY-CENTRE",   
    "OPENINGHRs":"MON-SUN",   
    "FACILITIES":"PLAYGROUNDS, PEDESTRIAN WALKWAYS, PICNIC AREA, SKATEBOARDING PARK, SEATING, TOILET FACILITIES, PLANTING AREAS WITH FLOWERS, SHRUBS AND TREES.",   
    "DESCR":"THIS CITY PARK WAS THE FIRST DEDICATED CHILDRENS PARK IN GALWAY.",   
    "Lat":"53.276",   
    "Long":"-9.06",   
    "EastITM":"529302.83",   
    "NorthITM":"725605.605",   
    "EastIG":"129336.803",   
    "NorthIG":"225576.505"   
  },]   
  ```
  
### Search for park by Facilities

This is a GET method

Replace Facilites with the facilites you want to look for

*http://www.galway.ie/galwayparklocatorapi/galwayparks/[Facilites]*   
E.G.
*http://www.galway.ie/galwayparklocatorapi/galwayparks/[1-soccer-playing-pitch]*   

**JSON Results by Facilites** 
```json   
[{      
    "OBJECTID":"26",   
    "NUMBER":"30",   
    "NAME":"DOUGHISKA PARK",   
    "LOCATION":"DOUGHISKA ROAD, GALWAY",   
    "AREAOFCITY":"CITY-EAST",   
    "OPENINGHRs":"NO RESTRICTED OPENING HOURS",   
    "FACILITIES":"1 SOCCER PLAYING PITCH, WALKWAYS, 2 TENNIS COURTS, BASKETBALL COURT, TODDLER PLAYGROUND, ADVENTURE PLAYGROUND, SKATEBOARDING PARK.",   
    "DESCR":"LOCAL NEIGHBOURHOOD PARK.",   
    "Lat":"53.283",   
    "Long":"-8.989",   
    "EastITM":"534027.432",   
    "NorthITM":"726260.028",   
    "EastIG":"134062.422",   
    "NorthIG":"226231.096"   
  },]   
  ```

### Search using mutliple parameters
You can also search using multiple parameters to narrow down your search E.G.
http://www.galway.ie/galwayparklocatorapi/galwayparks/?[filter]=[parameter]&[filter]=[parameter]
Is what you would use replacing filter with things like area and opening hours and the parameters to things like "CITY-CENTRE" and "MON-SUN". To search for multiple parameters just use & and add another parameter you want to look for The ? just starts a query string. This is also a GET method.

**JSON Results by Multiple parameters** 
```json   
[{      
    "OBJECTID":"14",   
    "NUMBER":"14",   
    "NAME":"MILLENNIUM CHILDRENS PARK",   
    "LOCATION":"NEWCASTLE ROAD, GALWAY",   
    "AREAOFCITY":"CITY-CENTRE",   
    "OPENINGHRs":"MON-SUN",   
    "FACILITIES":"PLAYGROUNDS, PEDESTRIAN WALKWAYS, PICNIC AREA, SKATEBOARDING PARK, SEATING, TOILET FACILITIES, PLANTING AREAS WITH FLOWERS, SHRUBS AND TREES.",   
    "DESCR":"THIS CITY PARK WAS THE FIRST DEDICATED CHILDRENS PARK IN GALWAY.",   
    "Lat":"53.276",   
    "Long":"-9.06",   
    "EastITM":"529302.83",   
    "NorthITM":"725605.605",   
    "EastIG":"129336.803",   
    "NorthIG":"225576.505"   
  },]   
  ```
  
 > Millenium Park is the only park with opening hour restrictions in Galway.

### Post Method
When this app is up and running it will be possible to update the info if anything changes E.G. a park gets named after an important member of the community. But this will only be on the maintanence end.

*http://www.galway.ie/galwayparklocatorapi/galway-parks/[GARY-OLDMAN-PARK]*  

**JSON Results of Renmore Park being renamed to Gary Oldman Park** 
```json   
[{      
    "OBJECTID":"23",   
    "NUMBER":"16",   
    "NAME":"GARY OLDMAN PARK",   
    "LOCATION":"RENMORE, GALWAY",   
    "AREAOFCITY":"CITY-EAST",   
    "OPENINGHRs":"NO RESTRICTED OPENING HOURS",   
    "FACILITIES":"2 GAELIC PLAYING PITCHES, 2 SOCCER PLAYING PITCHES, PLANTING AREAS WITH FLOWERS, SHRUBS AND TREES.",   
    "DESCR":"LOCAL NEIGHBOURHOOD PARK",   
    "Lat":"53.276",   
    "Long":"-9.018",   
    "EastITM":"532136.258",   
    "NorthITM":"725529.593",   
    "EastIG":"132170.842",   
    "NorthIG":"225500.493"   
  },]   
  ```

### Put Method
When this app is up and running it will be possible to add new info. But this will only be on the maintanence end.

*http://www.galway.ie/galwayparklocatorapi/galway-parks/[new-park]*  

**JSON Results of adding a new Park** 
```json   
[{      
    "OBJECTID":"30",   
    "NUMBER":"34",   
    "NAME":"NEW PARK",   
    "LOCATION":", GALWAY",   
    "AREAOFCITY":"CITY-",   
    "OPENINGHRs":"",   
    "FACILITIES":"",   
    "Lat":"",   
    "Long":"",   
    "EastITM":"",   
    "NorthITM":"",   
    "EastIG":"",   
    "NorthIG":""   
  },]   
  ```
  
### Delete Method
On the maintenance end once this app is up and running it will be possible to delete parks if the are constructed over to make something else E.G. a multi storey car park for a shopping centre/ even a shopping centre itself.
  

## Usefullness
This app I believe would be a very useful app because it will make finding parks easier and finding them based on a personal preference even easier. Originally I had designed this app to be aimed at mothers who want to find somewhere near to them where they could bring their children to but now after finishing I realize this app could be used by many more people E.G. local soccer/ gaelic/ rugby teams who are looking for a pitch to play. There are also basketball and tennis courts so a lot of sports people are covered. Runners could also use it to find parks with walkways or woodland paths to run on or even the ones with running tracks. Dog owners could also use this app to find places to walk their dogs like woodland paths. This can also be useful to people who are looking for things like a skateboarding park, ornamental pond, changing rooms, car parks, bus parks, picnic areas, rock climbing areas, toilet facilities, etc. etc. So this app can be useful to absolutely anyone whether they just need a nearby toilet or they want to play 5- aside with their friends or go for walks with their grandparents, this app can help them find it.
