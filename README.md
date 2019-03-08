Sustainable Development Goals - Energy
=========================

Visualizations for Global Energy Access

A series of dashboards was created to visualize Sustainable Development Goal #7: “Ensure access to affordable, reliable, sustainable, and modern energy for all.” Two indicators were chosen to represent progress toward this goal: 

1. “Proportion of the population with access to electricity”
2. “Renewable Energy Share in the Total Fine Energy Consumption”

The purpose of the project was to not only graphically depict the current degree of headway made toward these SDG indicators, but also better understand the relationships between them and identify areas of potential improvement. Concretely, the visualization’s key story is the connection between National Trends in Energy Development and the Human Development Index (HDI), with HDI being a metric for the developed/developing status of a country (calculated using factors such as standard of living, life expectancy, and education). The visualizations demonstrate that global access to electricity has indeed increased since 1990, particularly in developing African countries where it has historically been low. However, the proportion of developing countries with significant renewable energy consumption is, interestingly, much higher than that of developed countries in Europe and North America. A greater effort must therefore be made by the developed nations of the world to lead in the advancement and adoption of renewable energy technology in order to achieve the UN’s goal of increasing “substantially the share of renewable energy in the global energy mix” by 2030. 

Data
=========================

The data itself was drawn from the publicly available .csv files associated with the charts of [Our World in Data’s SDG Tracker](https://sdg-tracker.org/energy). Two .csv files were extracted for SDG Indicator 7.1.1: Access to Electricity and SDG Indicator 7.2.1: Renewable Energy. Data was also drawn from a publicly available .csv file associated with the charts of [Our World in Data’s Human Development Index (HDI)](https://ourworldindata.org/human-development-index). Due to there not being data for all years from 1990 to present in all .csv files, the geographical maps in the two visualizations show data for the year 2014 (the last year common between all .csv files). 

Static Visualization
=========================

The static visualization, optimized for distribution on social media, was created using ggplot in R Markdown: color indicates the proportion of the population with access to electricity, while the transparency of the markers associated with each country indicate what percentage of the total national fine energy consumption was renewable. For simplicity, triangles are used to indicate developing countries (arbitrarily defined as countries with HDI < 0.5 since HDI values range from 0 to 1) and circles are used to indicate developed countries (defined as countries with HDI > 0.5). 

![staticvis](https://github.com/cchinchristopherj/Global-Energy-Access/blob/master/Static-Visualization/sdg_staticvis.png)

Interactive Visualization
=========================

For the interactive visualization, leaflet and Shiny were used to take advantage of the possibility of user input. Leaflet added greater interactivity with the map, while Shiny allowed the user to select a country from a drop-down menu to display a line chart with trends in the three variables of interest (Percent Electricity Access, Percent Renewable Energy, and HDI) from 1990 to 2014. (Again, due to there not being data for all countries in this range, there are occasions where data points and/or variables are missing from the chart, also filled in as NA on the geographical map).

Modules and Installation Instructions
=========================

**Libraries Required for Static Viz:** rgeos, rworldxtra, rworldmap, ggplot2, tidyverse, sf, rvest, stringr, scales, viridis

These modules can also be installed using R's install.packages() method. For example, for the "rworldmap" library: 

        install.packages('rworldmap')

**Additional Libraries Required for Interactive Viz:** shiny, shinythemes, shinyWidgets, leaflet, leaflet.extras, plotly

Correct Usage
=========================

- For the static visualization, open the 'sdg_staticvis.Rmd' file in R Studio and click the "Knit" button to create the image
- For the interactive visualization, open the 'sdg_interactivevis.Rmd' file in R studio and click the "R Document" button to create the dashboards

