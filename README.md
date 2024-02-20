# The City of Calgary: Traffic Incidents and the Impacts on Residents

By Harjot Dhaliwal

February 15, 2024

## Introduction

As Calgary's population continues to expand and traffic incidents rise, it is crucial to address this significant concern impacting our city. Traffic incidents often result in premature deaths, particularly among young people, and may influence families' decisions to relocate to Calgary. Prioritizing automobile safety not only reinforces residents' trust in Calgary but also attracts skilled individuals seeking a conducive environment to raise families or advance careers, thus bolstering the city's businesses and economy. Understanding the causes behind these premature deaths can prevent countless tragedies, preserving family bonds. Factors contributing to traffic incidents include insufficient traffic signs, winter driving conditions, and reckless driving, all of which I will explore in this data story utilizing Calgary's open data portal.

## Guiding Questions

1. How does the distribution of traffic signs look like around Calgary?
2. How many traffic cameras do the different quadrants of Calgary have?
3. Where are traffic incidents occurring most in Calgary, and how does this change over time?
4. At what hour of day do traffic incidents occur most for each month?
5. What are the biggest reasons for traffic incidents occurring in Calgary?

## Datasets

The datasets were obtained from the city of Calgary's open data portal. Specifically, I selected the Map of Traffic Signs, Traffic Cameras, and Traffic Incidents datasets for exploration. These datasets contain various types of data, including spatial information, dates, strings, and numeric values (City of Calgary, 2024). To prepare the data for analysis, I utilized the Pandas package in Python. This involved several steps such as removing unnecessary columns, adjusting column data types, renaming columns, eliminating null rows, filtering out irrelevant data, and excluding stop words. All these datasets are pertinent to understanding Calgary's traffic incidents.

Some examples of the cleaned datasets are shown below:

### Map of Traffic Signs:

| sign | count | geometry |
| --- | --- | --- |
| Yield | 1 | POINT (-113.90912231652905 50.95285265999816) |
| Yield | 2 | POINT (-114.04310221676731 51.08744321592933) |
| Stop | 1 | POINT (-114.08361871907864 51.02702379547069) |
| … | … | … |

(City of Calgary, 2024)

### Traffic Cameras:

| quadrant | geometry |
| --- | --- |
| NE | POINT (-114.149379 51.0988494) |
| SE | POINT (-114.0811808 51.0536259) |
| NW | POINT (-113.9817289 51.1543016) |
| … | … |

(City of Calgary, 2024)

### Traffic Incidents:

| Incident info | Description | Date | Longitude | Latitude |
| --- | --- | --- | --- | --- |
| Westbound 16 Avenue at Deerfoot Trail NE | Stalled vehicle. Partially blocking the right lane | 2022-06-21 07:31:40 | 114.02668672232672 | 51.06748512927624 |
| 11 Avenue and 4 Street SW | Blocking multiple lanes | 2022-06-21 04:02:11 | 114.07148057660925 | 51.04262449261462 |
| 68 Street and Memorial Drive E | Traffic incident. | 2022-06-20 23:53:08 | 113.935553325751 | 51.0524735056658 |
| … | … | … | … | … |

(City of Calgary, 2024)

## Analyses

To initiate the analysis, let's begin by examining the distribution of traffic signs across Calgary. This will help identify any areas that may be lacking adequate signage, potentially contributing to traffic incidents. A common cause of such incidents could be the absence of clear signage at intersections, leading to confusion, especially during periods of heavy traffic flow. Here, we'll visualize the distribution of stop signs and yield signs on a map of Calgary.

### Map of Traffic Signs around Calgary

https://public.tableau.com/views/trafficsignsmap/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link

(City of Calgary, 2024)

Upon reviewing the map, one notable observation is the diverse distribution of stop signs compared to the more concentrated clustering of yield signs, particularly within the city limits. The prevalence of stop signs extends even to rural roads surrounding the city. Of particular interest are two areas exhibiting a higher proportion of yield signs compared to stop signs: the southeastern region and the vicinity of Arbour Lake in the northwest. Conversely, heavy concentrations of stop signs are evident in downtown, central north, central east, and southwest areas. Notably, the industrial section of the southeast appears neglected in terms of yield signs, prompting a potential investigation by the city to assess if traffic incidents stem from drivers failing to yield at uncontrolled intersections in this area.

Next, we'll examine the distribution of traffic cameras across different quadrants of Calgary. Another significant factor contributing to traffic incidents could be drivers exceeding speed limits or disregarding traffic signals, leading to collisions or loss of vehicle control. It's crucial to assess which communities in Calgary are under close surveillance and whether there are any quadrants lacking sufficient monitoring for speeding and red-light violations. This analysis will provide insight into potential areas requiring increased monitoring to enhance road safety measures.

### Counts of Traffic Cameras in Various Quadrants of Calgary

https://public.tableau.com/views/trafficcameras/Dashboard1?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link

(City of Calgary, 2024)

In our analysis, we observe that the southeast (SE) quadrant boasts the highest number of traffic cameras, followed closely by the southwest (SW). These two southern quadrants significantly surpass the northeast (NE) and northwest (NW) in terms of camera count. This finding is unexpected considering the substantial size of the NE and NW quadrants, which are often chosen by newcomers to Calgary. One would anticipate a higher number of traffic cameras in these areas to deter traffic violations effectively. However, it's worth highlighting the apparent neglect of camera deployment in the northern parts of the city, particularly in the NE quadrant. Intriguingly, despite being predominantly industrial, the SE quadrant enjoys a substantial presence of traffic cameras, suggesting a relative lack of camera coverage in residential areas compared to industrial zones.

## Traffic Incidents Over Time

Another important aspect of traffic incidents worth investigating is how they evolve over time across the city of Calgary. This analysis can provide valuable insights into the trends of traffic incidents and identify any shifts in occurrence within specific communities or hotspots. It's worth noting that the dataset indicates the city began recording this data in 2016, as evidenced by the limited number of entries in this year.

### Map of Traffic Incidents in Calgary Over Recent Years

https://public.tableau.com/views/TrafficIncidentsMap/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link

(City of Calgary, 2024)

Two notable observations emerge from our analysis. Firstly, downtown Calgary and the Deerfoot Trail corridor consistently stand out as hotspots for traffic incidents over the years. Particularly concerning is the prevalence of multi-vehicle incidents along the segment of Deerfoot Trail close to downtown, suggesting a need for investigation and potential implementation of speed reduction measures in that specific area. Secondly, Glenmore Trail consistently appears as a hotspot across all years examined.

Conversely, traffic incidents in the northwest (around Arbour Lake) and southeast (around Fish Creek Park) exhibit a scattered distribution and relatively low frequency. However, it's noteworthy that over time, traffic incidents seem to increase citywide, with a notable expansion towards the west side of the city. Additionally, there is a recent surge in traffic incidents along Stoney Trail, a trend that stands out given the highway's longstanding presence. Anecdotal evidence suggests that this increase may be attributed to a perceived lack of police presence, particularly on the eastern stretch of Stoney Trail.

Overall, the trend of traffic incidents gradually spreading from the city center towards the periphery is concerning and warrants further investigation. Government intervention and effective tools are imperative to mitigate these incidents and ensure road safety throughout Calgary.

Another aspect worth investigating is the timing of traffic incidents each month. This information can help determine optimal allocation of police presence. It's crucial to consider both the timing of incidents throughout the day as well as the months in which they occur.

### Traffic Incidents in Calgary by Hour of Day for each Month

https://public.tableau.com/views/HourofDay/Dashboard1?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link

(City of Calgary, 2024)

The plot reveals two notable peaks: one around 8am and another at 5pm, corresponding to typical commute times when roads are busiest. Interestingly, the most perilous time for traffic incidents appears to be 5pm in December, coinciding with winter driving conditions and rush hour traffic. However, it's noteworthy that the morning peak danger occurs at 8am in February rather than December. This anomaly could potentially be attributed to residual ice buildup from winter months prior. The higher incidence of incidents around 5pm may be attributed to individuals rushing home after a long workday.

Furthermore, an interesting observation is the lack of a significant morning peak during summer months compared to winter months. This discrepancy could be attributed to parents driving their children to school during winter months or hazardous road conditions caused by ice.

## Traffic Incident Descriptions

In addressing the high frequency of traffic incidents in Calgary, it's paramount to grasp the primary causes behind them. One effective approach is analyzing the descriptions provided by police officers regarding these incidents. By generating a word cloud from these descriptions after filtering out common and irrelevant terms, we can gain valuable insights into the prevailing factors contributing to traffic incidents.

### Count of Word Occurrences  in Traffic Incident Descriptions

https://public.tableau.com/views/WordCloud_17074254933000/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link

(City of Calgary, 2024)

The word cloud analysis reveals that lane blocking emerges as a predominant cause of traffic incidents in Calgary. Additionally, there is a notable disparity in incidents between the right and left lanes, with more occurrences observed in the right lane. Furthermore, it's apparent that a significant portion of incidents occur during traffic congestion. Most incidents involve two vehicles, as opposed to single or other multi-vehicle incidents.

A key implication drawn from this analysis is the need for closer examination of lane-blocking issues, particularly in the right lanes, as they generally contribute significantly to traffic incidents.

## Concluding Remarks

In conclusion, several key insights emerge from our analysis. Firstly, certain areas in the northwest (NW) and southeast (SE) of Calgary exhibit a lower density of stop signs, indicating potential areas of concern for the city to explore further. Additionally, there appears to be a discrepancy in the distribution of traffic cameras, with the north Calgary region potentially receiving less attention compared to the south, despite experiencing a comparable population size.

Furthermore, the concentration of traffic incidents in high-traffic areas such as Deerfoot Trail and downtown Calgary warrants further investigation, particularly concerning the prevalence of multi-vehicle incidents. Consideration should be given to implementing speed reduction measures in specific sections of Deerfoot Trail close to downtown.

Over time, there is a noticeable trend of traffic incidents spreading towards the outer parts of the city, with Stoney Trail emerging as a hotspot. This may be attributed to a perceived lack of police presence in these areas. Moreover, our analysis highlights peak incident times at 8am and 5pm, suggesting the need for heightened police presence during these periods.

Furthermore, there is a higher incidence of traffic incidents during winter mornings compared to summer, potentially due to factors such as parental school drop-offs and icy road conditions.

Notably, lane blocking in the right lane emerges as a significant contributor to traffic incidents.

With this comprehensive understanding and community action, we can address the issue of traffic incidents in Calgary, ultimately saving lives, boosting the economy, and fostering a vibrant and safe city for all residents to enjoy.

## References

City of Calgary. (2024). Map of Traffic Signs. Open Calgary. https://data.calgary.ca/Transportation-Transit/Map-of-Traffic-Signs/2c7u-hsrm

City of Calgary. (2024). Traffic Cameras. Open Calgary. https://data.calgary.ca/Transportation-Transit/Traffic-Cameras/k7p9-kppz/about_data 

City of Calgary. (2024). Traffic Incidents. Open Calgary. https://data.calgary.ca/Transportation-Transit/Traffic-Incidents/35ra-9556/about_data

Dhaliwal, H. (2024). The City of Calgary Traffic Incidents and the Impacts on Residents. Github. https://github.com/Harjot66/The-City-of-Calgary-Traffic-Incidents-and-the-Impacts-on-Residents

Froberg D. (2019). Grey Concrete Buildings. Unsplash. https://unsplash.com/photos/grey-concrete-buildings-NreIaUZ-h7U?utm_source=63921&utm_medium=referral
