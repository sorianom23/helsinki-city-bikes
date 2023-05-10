
# 🚲 Helsinki City Bikes 🚲

### **Table of Contents**
- [🚲 Helsinki City Bikes 🚲](#-helsinki-city-bikes-)
    - [**Table of Contents**](#table-of-contents)
  - [**Introduction**](#introduction)
  - [**Data Sources**](#data-sources)
  - [**Data Exploration and Analyisis**](#data-exploration-and-analyisis)
  - [**Prediction**](#prediction)
  - [**Results and conclusions**](#results-and-conclusions)
  - [**Tableau Dashboard**](#tableau-dashboard)

---

## **Introduction**

The Helsinki City Bikes have become an increasingly popular mode of transportation for citizens of Helsinki and Espoo, with more than 10 million trips taken between 2016 and 2020. As the city bike system continues to expand and evolve, it is important to gain insights into the usage patterns and trends of the bikes. In this data analysis project, I will explore the Helsinki City Bike dataset to uncover valuable insights about how citizens are using the bikes, when and where they are most frequently used, and how usage patterns have changed over time. By analyzing this data, I aim to gain a deeper understanding of the impact of the Helsinki City Bikes on the community and inform future decisions regarding the system's expansion and operation.

---

## **Data Sources**
- Main data source: https://www.kaggle.com/datasets/geometrein/helsinki-city-bikes
- Webscraped data is from: https://www.cityfillarit.fi/en/

---

## **Data Exploration and Analyisis**

I conducted several steps to prepare the data for analysis, including:

- Treated null values by either removing them or imputing values where appropriate.
- Changed some metrics from meters (m) to kilometers (km) and from seconds (sec) to minutes (min) to make the data more user-friendly.
- Added specific columns that show the year, month, weekday, and hour of each rental to help with time-based analysis.
- Added "total_rentals" column based on "departures".
- Removed outliers, especially for distance and duration. I found some extreme values that were likely errors in the device that stores the bike metrics, so I removed them to improve the accuracy of the analysis.
- Dropped the column that shows the average speed in kilometers per hour because it had too many outliers and was not important for our analysis.
- Saved the clean data in a new file (clean_data.csv) that is now ready for prediction.
  
By taking these steps, we were able to ensure that our data was reliable and well-prepared for analysis.

---

## **Prediction**

In this project, one of my goals was to predict the total number of bike rentals without using a linear regression model. To do this, I first checked the distribution of the columns and realized that some were skewed, so I applied algorithmic transformation to these columns.

Next, I used an encoder to encode the categorical columns, and applied both the standard scaler and MinMax scaler to standardize the values and put them in the same range for the model.

After treating the data, I built the model. I printed out various metrics, such as R^2 score, mean squared error, root mean squared error, and mean absolute error. And visualized the performance of the model with a scatterplot.

Overall, the model performed well and provided accurate predictions for the total number of bike rentals.

---

## **Results and conclusions**

Based on the analysis performed, several interesting findings were observed.

- There is a correlation between the amount of rentals and the weather based on the degrees. The service is used more frequently when the weather is good, and temperatures are moderate. Secondly, the service is used more frequently between June and August, which are typically the months with better weather in Helsinki and Espoo.

- There are spikes in the total amount of rentals early in the morning when people usually want to get to work or to school and also in the afternoon when people come back from school and work. This indicates that the service is mainly used for commuting purposes.

- People travel more than 1M km per season with the bike system, which has a significant impact on how people move around the city in a more sustainable way.

- The busiest stations where there are more departures and returns. The busiest stations are Itämerentori, Kamppi, and Töölönlahdenkatu.


Additionally, the results indicate that the bike-sharing system has a significant impact on how people move around the city in a more sustainable way. The insights obtained from this analysis can be used to inform policy decisions related to transportation and urban planning in the region.

---


## **Tableau Dashboard**

https://public.tableau.com/app/profile/maria.soriano/viz/helsinki-city-bikes/dashboard 

<div class='tableauPlaceholder' id='viz1683711967546' style='position: relative'><noscript><a href='#'><img alt='Helsinki City Bikes ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;he&#47;helsinki-city-bikes&#47;dashboard&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='path' value='views&#47;helsinki-city-bikes&#47;dashboard?:language=en-US&amp;:embed=true' /> <param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;he&#47;helsinki-city-bikes&#47;dashboard&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /></object></div>                <script type='text/javascript'>                    var divElement = document.getElementById('viz1683711967546');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth > 800 ) { vizElement.style.width='1100px';vizElement.style.height='1127px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.width='1100px';vizElement.style.height='1127px';} else { vizElement.style.width='100%';vizElement.style.height='1677px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>