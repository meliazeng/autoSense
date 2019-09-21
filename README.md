# Business requirement
## Objective
The solution is designed to analysis customer interests on Auto Dealership by catching visitor's behavior on Shop floor with cutting edge sensor technologies. 
## What is involved
- Brand/Owner: The owner or the brand of the chained stores. (optional)
- Store: The location to group sensoring data before analysis.
- Car: Items that contain brand, condtion(new/used), model (url on office site), color, type(sedan, truck, two door, four door, van...), price range, Display spot
- Door: The basic unit in which activities is being track and collected by sensor
- Sensor: The device that attached on each door to catch movement and submit data for analysis
- Activity: Door open (Seat on, duration of proximity)
## Pattern to be analysis
- Popularity of **Model** 
- Popularity of **Brand** 
- Popularity of **color** 
- Popularity of **type** 
- Popularity of **Codition** 
- Popularity of **Price range** 
- Popularity of **Condition** 
- Popularity of **individual car** 
- Popularity of Dispaly spot**
## Information display method
- Real time Dashboard
- Power BI analysis
```
* Pipe Chart
* Bar Chart
* Line Graph
```
## Scarnio for sensoring
- Visitor open the door, get into the card and close the door. Open the door again and leave the seat, close the door. (Interested and being attracted) 
- Visitor open the door and close the door without getting inside.  (interested but not being attracted)
- Visitor open and close the door, in and out to the car for multiple time, all activities are in a continue maner. (very interested)
# Solution Design
The solution contains tow parts - Sensor collection and Data processing unit. This document foucs on Data processing unit only. 
## POC stage
The design for SQL database

- Tbl_owner_store
```
- ID : uniqueidentifier
- Name : nvarchar(100)
- Address: nvarchar(200)
- Parent: uid
``` 
- Tbl_car
```
- ID : uniqueidentifier
- Name: nvarchar(100)
- url: nvarchar(200)
- Serial: nvarchar(100)
- Position: nvarchar(10)
- Color: nvarchar(20)
- Type: int
- Note: nvarchar(100)
- Condition: boolean
```
- Tbl_Door
```
- ID: uniqueidentifier
- CarID: uid
- SensorID: uid
- Note: nvarchar(100)
```
-Tbl_Activities
```
- ID: uniqueidentifier
- startTime: DateTime
- endTime: DateTime
- DoorID: uid
- type: int
```
