# Road Crashes in South Australia from 2020 to 2022

_Author: Clara Le_

_Date: 15/06/2023_
___

## INTRODUCTION

The analysis project was aimed to define actionable and reasonable solutions to reduce the number of road crashes in South Australia through analyzing the dataset of road crashes in South Australia from 2020 to 2022. Besides evaluating the trend of road crashes' quantities over years, this project also measured the effects of various relevant factors, such as road condition, traffic control signs, weather condition, daytime or night, and the involvement of DUI or drugs, on the frequency of road crashes. An interactive report of this analysis project was also created for users' interaction, so users can employ this Power BI report to perform their own analysis if needed. Please refer to the interactive version of the Power BI report in this link: [Interactive report](https://github.com/Tien-le98/Road_crashes/blob/main/Road_crashes_SA.pbix). Besides, the statis version of the Power BI report also can be found in this link: [Static report](https://github.com/Tien-le98/Road_crashes/blob/main/Road_crashes_SA.pdf).

## Data collection, data cleaning and pre-processing
The "Road crashes in South Australia" dataset was gather from South Australian Government Data Directory website. This dataset went through various pre-processing steps including modifying data type of each variable, removing invalid values, handling missing values, encoding categorical variables, and removing duplicates. The original dataset comprised about 65000 road crashes' records from 2018 to 2022, however, only about 37000 records from 2020 to 2022 were considered in this analysis project. Main variables were:
+ Stats Area: A code defining whether the road crash occurred (City, Metro, Country Area)
+ Total Units: The total number of units involved in a road crash. Total Units = Total Cas + Total Property Damage Only
+ Total Cas: Total number of casualties in a road crash. Total Cas = Total Fats + Total SI + Total MI
+ Total Fats: Total number of fatalities as a result of a road crash
+ Total SI: Total number of people admitted to hospital with overnight stay as a result of a road crash
+ Total MI: Total number of people treated by private doctor or treated at hospital but not admitted
+ Year: Year of Crash
+ Month: Month of Crash
+ Day: The day of the week the crash occurred
+ Area speed: The speed limit at the time and location of the crash
+ Horizontal Align: Defines the horizontal alignment of the road at the sight of the crash (Curved road with View obscured, Curved road with View open, Straight road)
+ Vertical Align: Defines the vertical alignment of the road at the sight of the crash (Slope, Bottom of Hill,...)
+ Road Surface: Defines the road surface type at the crash location (Sealed or Unsealed road)
+ Weather Cond: Defines the weather condition at the time and location of the crash (Not Raining, or Raining)
+ DayNight: Defines that a road crash occured during daylight or at night
+ Crash Type: Defines the road crash type (Hit Fixed Object, Hit Animal, Hit Pedestrian,...)
+ Entity Code: Defines the entity deemed to be responsible for the road crash (Driver, Animal, Pedestrian,...)
+ CSEF Severity: Defines the road crash severity, classified by the highest injury severity sustained in the crash (Serious Injury - SI, Minor Injury - MI, Property Damage Only - PDO)
+ Traffic Controls (Traffic Ctrls): Defines the traffic control at the time and location of the road crash (No Control, Roundabout, Stop Sign,...)
+ DUI Involved: Involved if at least one controller in the crash recorded an illegal Blood Alcohol Concentration level (Yes - Y, No - N)
+ Drugs Involved: Involved if at least one controller in the crash tested positive for a prescribed drug (THC (cannabis), methylamphetamine (speed, ice or crystal meth) or MDMA (ecstasy)) (Yes - Y, No - N).

## Exploratory Data Analysis (EDA)
### Trend of road crashes' quantities in South Australia over years (2020-2022)

The number of road crashes in 2021 and 2022 were higher than the figure for 2020. The reason can be a lot of more vehicles were used to travel on roads in 2021 and 2022 than in 2020.

However, the positive signal was that in general, the figure for 2022 was lower than the previous year. It can be because of higher roads quality, or more effective control signals, or other improvements of infrastructure was implemented in 2022.

There are several public holidays in January, and April, such as New Year, Easter, Australia Day, Anzac Day, hence not many vehicles travelling on roads in SA because people have days off on those holidays or they go on a trip to other places. Therefore, the number of road crashes in SA in those months were lower than the figure for other months in general.

<p align="center" width="100%">
    <img width="70%" src="https://github.com/Tien-le98/Road_crashes/blob/main/trend_over_years.png">
</p>

### Effect of Severity level and Stats Area on the total number of road crashes

Crashes are categorized into four main categories which are Fatality (Fatal), Property Damage Only (PDO), Serious Injury (SI), and Minor Injury (MI).

In Proper Damage Only and Minor Injury classes, the majority of crashes occurring in Metropolitan which can be five times higher than the figure for Country and more than 10 times higher than the figure for City.

In Serious Damage, the proportion of crashes happening in Country was much higher than its proportion in other severity categories. Particularly, the quantity of crashes happened in Country were about a half of the figure for Metropolitan area.

In Fatality, the number of crashes occured in the Country was even slightly higher than the figure for Metropolitan areas, and City has no road crashes with fatalities.

<p align="center" width="100%">
    <img width="70%" src="https://github.com/Tien-le98/Road_crashes/blob/main/quantity_severity level.png">
</p>

#### Average Area Speed limit of road crashes, by Severity level and Stats Area

The average area speed (shown in red lines) in Country was the highest, followed by the figure for Metropolitan, and the least speed was in City. This can be why least crashes happening in the City.

The majority of road crashses happened in areas allowing speeds between 50km/h and 60km/h, which are driving speeds in the Metropolitan areas. There is not a lot of road crashes happened in Country areas, which allow up to 100km/h. Although the area speed of Metropolitan was lower than the figure for Country, the total quantity of road crashes in Metropolitan was much higher than the figure for Country, it can be because there is a lot more vehicles travelling on roads in Metropolitan than in Country. Therefore, area speed might be not a major factor affecting the quantity of road crashes, but the number of vehicles travelling on roads may be a significant factor.

In Country areas, generally, the increase in area speed can result in the higher level of severity of road crashes. That can be why there was higher quantity of road crashes with fatalities in Country than in other areas.

<p align="center" width="100%">
    <img width="70%" src="https://github.com/Tien-le98/Road_crashes/blob/main/speed_area.png">
</p>

### Effect of Road Condition on the total number of road crashes

Most of road crashes happened on sealed roads, instead of unsealed roads. It can be because sealed roads can be constructed mostly in metropolitan areas, and major highways are always sealed. On the contrary, many roads in the countryside and remote areas may be unsealed. Therefore, the total number of road crashes happening on sealed roads were higher than the figure for unsealed roads because a lot more vehices travelling in Metropolitan and highways connecting states, than in Country areas.

Stat_area | Road Surface | Total crashes in 2020 | Total crashes in 2021 | Total crashes in 2022
--- | --- | --- | --- | ---
City | Sealed | 477 | 600 | 546
City | Unsealed | 2 | 6 | 3
Country | Sealed | 1471 | 1687 | 1685
Country | Unsealed | 278 | 288 | 280
Metropolitan | Sealed | 9197 | 10451 | 9712
Metropolitan | Unsealed | 97 | 113 | 120

It can be seen that less crashes happening on sealed roads in 2022 than in 2021, especially in Metropolitan area. In addition, most crashes occurred in T-Junction, Cross Road, Not Divided Road, and Divided Road.

### Effect of Horizontal Align and Severity on the total number of road crashes
The highest number of crashes occurred on straight road, followed by Curved road with Open View. In addition, more than 85% of road crashes caused minor injuries or Property Damage Only happened on straight roads. But in terms of crashes with serious injuries and fatalities, it can be seen that the proportion of Curved road with open view was much higher than its figure for other severity levels, which mean that curved roads can be one of main factors lead to crashes with higher severity levels. For example, in terms of road crashes with fatalities, upto 30% total road crashes occurred on Curved road with View open.

Severity |	Horizontal Align |	Total Crashes by Horiztontal Align and Severity	| Total crashes	Proportion (%)
---|---|---|---|
Fatal | Straight road | 155 | 246 | 63
Fatal | Curved, View open | 72 | 246 | 29
Fatal | Curved, View obscured | 19 | 246 | 8
MI | Straight road | 8270 | 9678 | 85
MI | Curved, View open | 984 | 9678 | 10
MI | Curved, View obscured | 424 | 9678 | 5
SI | Straight road | 1407 | 1890 | 74
SI | Curved, View open | 317 | 1890 | 17
SI | Curved, View obscured | 166 | 1890 | 9
PDO | Straight road | 21828 | 25095 | 87
PDO | Curved, View open | 2373 | 25095 | 9
PDO | Curved, View obscured | 894 | 25095 | 4

### Effect of Traffic Control on the total number of road crashes

The majority of crashes happened on roads without any traffic control signals (No Control). The second highest figure was for Traffic Signals in Metropolitan and City, and Give Way Sign in Country. Hence it raises a need to check traffic signals to evaluate if they are effective in controlling the traffic and whether new necessary control signals should be established on roads.

### Effect of Weather Condition and DayNight on the total number of road crashes

<a href="url"><img src="https://github.com/Tien-le98/Road_crashes/blob/main/weathercond_quantity_daynight.png" align="right" width = "50%" ></a>

In general, the majority of crashes happened in no raining condition. The proportion of crashes in no raining condition in 2022 was lower than the figure for 2021. However, the opposite was true for raining condition, because the percentage of crashes occuring in raining condition in 2022 was higher than the figure for 2021. 

Most of crashes occurred on daylight instead of night, on both raining and not raining condition. In addition, during raining condition, the quantity of road crashes happend during daylight was even higher than the figure for night. This issue happened can be because of human perspective. When people drive during daylight, they can have clearer visibility, hence they can drive less carefully than at night, and it leads to higher quantity of crashes during daylight than night.

In addition, the proportion of some crash types such as Hit fixed object, hit object on road, and hit pedestrian was higher at night on raining condition than during daylight. For example, in terms of Hit Object on Road, during daylight, only about 10% of crashes due to the rain. However, at night, more than 23% of crashes occurred because of the rain.

DayNight | Weather Condition | Crash Type | Total crashes by Weather Condition | Total crashes | Proportion (%)
---|---|---|---|---|---|
Daylight | Not raining | Hit Object on Road | 78 | 86 | 91
Daylight | Raining | Hit Object on Road | 8 | 86 | 9
Night | Not raining | Hit Object on Road | 50 | 65 | 77
Night | Raining | Hit Object on Road | 15 | 65 | 23

### Effect of Human behaviour on the total number of road crashes

<a href="url"><img src="https://github.com/Tien-le98/Road_crashes/blob/main/dui_drug_severity.png" align="right" width = "30%" ></a>

Most crashes happened when there was no DUI or Drugs Involved. And the proportion of crashes with DUI or Drug Involves was negligible, in comparison to the figure for crashes without DUI and Drugs. In crashes having injuries and fatalities, the contribution of crashes DUI involved and Drug involved were higher than its proportion in crashes with Property damage only. It means if a crash has injuries, or fatalities, it is more likely that there is a participation of DUI and Drugs.

In addition, the quantity of crashes with DUI involved in hit fixed object was larger than other types. The figure for Drug Involved also saw the same thing.

### Effect of Responsible entity on the total number of road crashes

Drivers take responsibility for most road crashes. Animals took responsibility for road crashes happening in Country and Metropolitan, not in City. In terms of road crashes with injuries and fatalities, the proportion of road crashed happened due to Pedestrian increased, which means that the responsibility of Pedestrian were more significant in crashes with higher severity levels.

<p align="center" width="100%">
    <img width="70%" src="https://github.com/Tien-le98/Road_crashes/blob/main/entitycode_severity.png">
</p>

## Conclusion

Through this analysis, there are several main points as belows:

+ The higher number of vehicles travelling on roads in 2021-2022 can be a reason for the higher road crashes' quantities in 2022 than the figure for previous years. However, the figure for 2022 was lower than 2021. It can be because of higher roads quality, or more effective control signals, or other improvements of infrastructure was implemented in 2022.
+ The majority of crashes occurring in Metropolitan. However, in Fatality class, the number of crashes occured in the Country was even slightly higher than the figure for Metropolitan areas.
+ The area speed in City was the least, compared to the figure for other areas. This can be why least crashes happening in the City.
+ The majority of road crashses happened in areas allowing speeds between 50km/h and 60km/h, which are driving speeds in the Metropolitan areas. Although the area speed of Metropolitan was lower than the figure for Country (100km/h), the total quantity of road crashes in Metropolitan was much higher than the figure for Country. It can be because there is a lot more vehicles travelling on roads in Metropolitan than in Country. Therefore, area speed might be not a major factor affecting the quantity of road crashes, but the number of vehicles travelling on roads may be a significant factor.
+ In Country areas, generally, the increase in area speed can result in the higher level of severity of road crashes. 
+ Most of road crashes happened on sealed roads, instead of unsealed roads. It can be because sealed roads can be constructed mostly in metropolitan areas, where higher number of vehicles travelling on roads.
+ The highest number of crashes occurred on straight road, followed by Curved road with Open View. In addition, more than 85% of road crashes caused minor injuries or Property Damage Only happened on straight roads. But in terms of crashes with serious injuries and fatalities, the proportion of Curved road with open view was much higher than its figure for other severity levels, which mean that curved roads can be one of main factors lead to crashes with higher severity levels. In terms of road crashes with fatalities, upto 30% total road crashes occurred on Curved road with View open.
+ The majority of crashes happened on roads without any traffic control signs. The second highest figure was for Traffic Signals in Metropolitan and City, and Give Way Sign in Country. Hence it raises a need to check traffic signals to evaluate if they are effective in controlling the traffic and whether new necessary control signals should be established on roads.
+ In general, the majority of crashes happened in no raining condition. In addition, most of crashes occurred on daylight instead of night, on both raining and not raining condition. In addition, during raining condition, the quantity of road crashes happend during daylight was even higher than the figure for night. This issue happened can be because of human perspective. When people drive during daylight, they can have clearer visibility, hence they can drive less carefully than at night, and it leads to higher quantity of crashes during daylight than night.
+ The proportion of some crash types such as Hit fixed object, hit object on road, and hit pedestrian was higher at night on raining condition than during daylight.
+ Most crashes happened when there was no DUI or Drugs Involved. And the proportion of crashes with DUI or Drug Involves was negligible, in comparison to the figure of no DUI and no Drugs. In crashes having injuries and fatalities, the contribution of crashes DUI involved and Drug involved were higher than its proportion in crashes with Property damage only. It means if a crash has injuries, or fatalities, it is more likely that there is a participation of DUI and Drugs.
+ Drivers take responsibility for most road crashes. Animals took responsibility for road crashes happening in Country and Metropolitan, not in City. In terms of road crashes with Serious Injury and Fatalities, the proportion of Pedestrian increased, which means that the responsibility of Pedestrian were more significant in crashes with higher severity levels.

Please refer to the analysis report in this link: [Analysis report](https://github.com/Tien-le98/Road_crashes/blob/main/Road_Crashes_in_SA.ipynb)

