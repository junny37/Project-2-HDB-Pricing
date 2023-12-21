<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Project 2 - Singapore Housing Data and Kaggle Challenge


## Background
---

[The Housing Development Board (HDB)](https://www.hdb.gov.sg/cs/infoweb/about-us) is a government board that offers affordable public housing to Singapore citizens. 

In the recent [2023 Asia Pacific ULI Attainability Index](https://asia.uli.org/wp-content/uploads/2023/05/ULI-Home-Attainability-Index-report_-28-May-Finalised.pdf), Singapore passes Hong Kong as the highest median housing price per unit in 2023. As [private housing increases](https://www.channelnewsasia.com/singapore/private-property-condo-prices-q1-2023-absd-ura-3450651), Singaporeans would logically look at HDB housing for a more afforable and reasonable option. However, with [HDB housing prices increasing](https://www.businesstimes.com.sg/property/hdb-resale-prices-rise-further-april-amid-falling-volume-srx-99co), it is suffocating to think about saving up to purchase housing for the future.


### Problem Statement

Coming from the background of someone who has recently moved back to Singapore and is planning on settling down and starting a family here in the future, I am interested in <font color = 'green'>**analysing and predicting housing resale prices**</font>, given the current trends and the possible factors that could affect the price.


## Data Dictionary
----

[**All information from Kaggle**](https://www.kaggle.com/competitions/dsi-sg-project-2-regression-challenge-hdb-price/data)

|Feature|Type|Description|
|---|---|---|
|resale_price|float|the property's sale price in Singapore dollars. This is the target variable that we're trying to predict for this challenge.|
|Tranc_YearMonth|object|year and month of the resale transaction|
|town|object|HDB township where the flat is located|
|flat_type|object|type of the resale flat unit|
|block|object|block number of the resale flat|
|street_name|object|street name where the resale flat resides|
|storey_range|object|floor level (range) of the resale flat unit|
|floor_area_sqm|float|floor area of the resale flat unit in square metres|
|flat_model|object|HDB model of the resale flat|
|lease_commence_date|integer|commencement year of the flat unit's 99-year lease|
|Tranc_Year|integer|year of resale transaction|
|Tranc_Month|integer|month of resale transaction|
|mid_storey|integer|median value of storey_range|
|lower|integer|lower value of storey_range|
|upper|integer|upper value of storey_range|
|mid|integer|middle value of storey_range|
|full_flat_type|object|combination of flat_type and flat_model|
|address|object|combination of block and street_name|
|floor_area_sqft|float|floor area of the resale flat unit in square feet|
|hdb_age|integer|number of years from lease_commence_date to present year|
|max_floor_lvl|integer|highest floor of the resale flat|
|year_completed|integer|year which construction was completed for resale flat|
|residential|object|boolean value if resale flat has residential units in the same block|
|commercial|object|boolean value if resale flat has commercial units in the same block|
|market_hawker|object|boolean value if resale flat has a market or hawker centre in the same block|
|multistorey_carpark|object|boolean value if resale flat has a multistorey carpark in the same block|
|precinct_pavilion|object|boolean value if resale flat has a pavilion in the same block|
|total_dwelling_units|integer|total number of residential dwelling units in the resale flat|
|1room_sold|integer|number of 1-room residential units in the resale flat|
|2room_sold|integer|number of 2-room residential units in the resale flat|
|3room_sold|integer|number of 3-room residential units in the resale flat|
|4room_sold|integer|number of 4-room residential units in the resale flat|
|5room_sold|integer|number of 5-room residential units in the resale flat|
|exec_sold|integer|number of executive type residential units in the resale flat block|
|multigen_sold|integer|number of multi-generational type residential units in the resale flat block|
|studio_apartment_sold:|integer|number of studio apartment type residential units in the resale flat block|
|1room_rental|integer|number of 1-room rental residential units in the resale flat block|
|2room_rental|integer|number of 2-room rental residential units in the resale flat block|
|3room_rental|integer|number of 3-room rental residential units in the resale flat block|
|other_room_rental|integer|number of "other" type rental residential units in the resale flat block|
|postal|object|postal code of the resale flat block|
|Latitude|float|Latitude based on postal code|
|Longitude|float|Longitude based on postal code|
|planning_area|object|Government planning area that the flat is located|
|Mall_Nearest_Distance|float|distance (in metres) to the nearest mall|
|Mall_Within_500m|float|number of malls within 500 metres|
|Mall_Within_1km|float|number of malls within 1 kilometre|
|Mall_Within_2km|float|number of malls within 2 kilometres|
|Hawker_Nearest_Distance|float|distance (in metres) to the nearest hawker centre|
|Hawker_Within_500m|float|number of hawker centres within 500 metres|
|Hawker_Within_1km|float|number of hawker centres within 1 kilometre|
|Hawker_Within_2km|float|number of hawker centres within 2 kilometres|
|hawker_food_stalls|integer|number of hawker food stalls in the nearest hawker centre|
|hawker_market_stalls|integer|number of hawker and market stalls in the nearest hawker centre|
|mrt_nearest_distance|float|distance (in metres) to the nearest MRT station|
|mrt_name|object|ame of the nearest MRT station|
|bus_interchange|integer|boolean value if the nearest MRT station is also a bus interchange|
|mrt_interchange|integer|boolean value if the nearest MRT station is a train interchange station|
|mrt_latitude|float|latitude (in decimal degrees) of the the nearest MRT station|
|mrt_longitude|float|longitude (in decimal degrees) of the nearest MRT station|
|bus_stop_nearest_distance|float|distance (in metres) to the nearest bus stop|
|bus_stop_name|object|name of the nearest bus stop|
|bus_stop_latitude|float|latitude (in decimal degrees) of the the nearest bus stop|
|bus_stop_longitude|float|longitude (in decimal degrees) of the nearest bus stop|
|pri_sch_nearest_distance|float|distance (in metres) to the nearest primary school|
|pri_sch_name|object|name of the nearest primary school|
|vacancy|integer|number of vacancies in the nearest primary school|
|pri_sch_affiliation|integer|boolean value if the nearest primary school has a secondary school affiliation|
|pri_sch_latitude|float|latitude (in decimal degrees) of the the nearest primary school|
|pri_sch_longitude|float|longitude (in decimal degrees) of the nearest primary school|
|sec_sch_nearest_dist|float|distance (in metres) to the nearest secondary school|
|sec_sch_name|object|name of the nearest secondary school|
|cutoff_point|integer|PSLE cutoff point of the nearest secondary school|
|affiliation|integer|boolean value if the nearest secondary school has an primary school affiliation|
|sec_sch_latitude|float|latitude (in decimal degrees) of the the nearest secondary school|
|sec_sch_longitude|float|longitude (in decimal degrees) of the nearest secondary school|


## Analysis & Conclusions Summary
---

Using different regression models, we found the best model to make the most accurate predictions using our Train, Test, Split method.

We can see that the most important factor that affect resale pricing in Singapore is determined on location. Other factors also include amenities nearby, proximity to primary schools, and size of property.

From the above few models, we can see that it is possible to predict the housing resale price. Evaluating how well our best prediction model faired, it gave us an approximate 0.91 R<sup>2</sup> value, and a RMSE of approximately $44.6K. If more time was given, more improvements can be made to the models, including exploring different combinations of features, and feature engineering.

