---
name: Homework 5
tools: [Python, HTML, vega-lite]
image: assets/pngs/uv_index.png
description: Weiting's HW 5 vega-lite interactive visualization
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Average UV Index by State and Month


<vegachart schema-url="{{ site.baseurl }}/assets/json/uv_state_month.json" style="width: 80%"></vegachart>
### Description
The first plot allows users to explore the average UV index across all the U.S. states in different months. By clicking one of the blocks on the heatmap, users will see a line chart pop up on the right of the heatmap and see how UV patterns change over the year. In the heatmap, it displays the mean UV Index by state. In the line chart, it shows the UV trend from the selected state from the heatmap. This side by side pairing enables users to identify both national scale seasonal UV patterns and specific within state trends. 
### Encodings
As for the encodings, the x-axis encodes month as an ordinal variable, which represents the time of year. The y-axis encodes State as a nominal variable to show each state as a separate row. In the heatmap, color encodes the mean UV Index. The darker the shade is, the higher the UV intensity is. In the line chart, x-axis represents the month and y-axis is the average UV index over time. The trend line will show up after the users click their desired heat block of their chosen state and month. Regarding the color map, the heatmap uses Altair’s red sequential color scale for quantitative data to demonstrate the intensity of average UV index, which aligns with the common perception, darker reds signal stronger UV exposure. The line in the line chart encodes the selected state so it is easier for users to track which state is selected.
### Transformations
Data transformations are applied in Altair to avoid errors. First, missing values are removed to prevent error and ensure clear visualization. As the plot is illustrating the average of UV index, the mean aggregation is computed in Altair’s encoding stage. In addition, the application of selection filter transformation is applied to filter the dataset for the clicked state in the linked view. To make the plot easier to read, axis labels and titles are enlarged with parameters, labelFontSize and titleFontSize. The point selection is bound to the state field in the heatmap, so the line chart filters to show the chosen state’s UV data with the corresponding month by users’ choice. This added interactivity prevents users from feeling overwhelmed by reading the heatmap alone. Users can also observe the trend of UV over the year of a state. 
### Interactivity
The point selection is bound to the state field in the heatmap. When a user clicks on any heat block of a state, the line chart automatically updates to display that state’s average monthly UV data. This lets users focus on one state at a time and observe how UV levels change across all months for their selection. This added interactivity prevents users from feeling overwhelmed by reading the heatmap alone. Users can also observe the trend of UV over the year of a state. 
### Analysis
The heatmap demonstrates the seasonal pattern of UV index. The values are high in summer months in most of the states. Southern states such as Texas or Arizona will experience higher UV levels all year than other northern states. The line chart can let users see one state’s UV temporal variation. UV is more intense in summer times, and UV has less intensity in winter. 


# Temperature and Atmospheric Conditions by Precipitation Type

<vegachart schema-url="{{ site.baseurl }}/assets/json/precip_type.json" style="width: 100%"></vegachart>
### Description
The second plot allows users to examine how mid temperature in fahrenheit can be related to different precipitation types, rain and snow, in the year after 2000. The year is limited to after 2000 to ensure modern climatological patterns are reflected . A dropdown button is created, enabling users to choose their atmospheric variables to observe how precipitation probably, precipitation intensity, and wind speed relates to changes in temperature across different weather conditions. 
### Encodings
For this scatter plot, I applied circles to represent individual observations with size 60 and adjusted the opacity to 0.8 for better visibility. The mid temperature on the x-axis is the average daily temperature in Fahrenheit. On the y-axis, it displays the atmospheric variables that can be chosen from the dropdown by the users with the bound parameter, y_var. Two colors are encoded for the precipitation types with categorical hues, so users can differentiate between rain and snow. Tooltips are added to display other important contextual information such as state, month, year, and exact atmospheric numerical values, so users can read the desired information directly when hovering their mouse on the plot. 
### Transformations
Two transformations are included in this plot. Transform_fold is applied to reshape the dataset so multiple atmospheric variables can be toggled on the same y-axis. Transform_filter ensures only the selected variable is displayed when users switch dropdown options. Another filter applies on precipitation type so it removes  missing precipitation types to avoid NaN values shown on the legend and scatter plot. 
### Interactivity
Besides the zooming through .interactive() that allows users to observe clusters of similar temperatures or zoom out for overall climate trends, another interactivity in this plot is the dropdown menu. Users can switch between precipitation probability, precipitation intensity, and wind speed, allowing users to compare and explore how these atmospheric variables behave in relation to mid temperature and precipitation types. Hover tooltips provides contextual details such as state, month, year, and exact numeric values of the chosen atmospheric variables. Including this feature not only transforms this plot from a static scatter plot into an interactive analytical tool but also offers users more details that interest them. 
### Analysis
After switching between atmospheric variables using the dropdown, we can see important trends and observations. In precipitation probability, snow events tend to occur at lower temperatures, while rain events dominate higher temperatures. Also, slightly more rain points are clustered around higher probability values, showing that rain is more common in warmer conditions. In wind speed, both rain and snow show moderate wind speeds across temperature ranges, but rain generally occurs over a wider temperature span. Both rain and snow show different wind speeds across the same temperature ranges, but rain occurs over a wider temperature span. As for precipitation intensity, slightly more rain events show slightly higher intensity values than snow, but both of the events have low intensity overall. 

<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/tinayang922/tinayang922.github.io/blob/main/python_notebooks/Workbook.ipynb" text="The Analysis" %}
</div>