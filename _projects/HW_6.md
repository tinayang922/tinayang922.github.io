---
name: Interactive Visualization of Univeristy of Illinois Building
tools: [Python, HTML, vega-lite]
image: assets/pngs/gov_building.png
description: Vega-lite Interactive Visualization
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Year Constructed and Total Floors of University of Illinois Buildings


<vegachart schema-url="{{ site.baseurl }}/assets/json/year_building.json" style="width: 80%"></vegachart>
### Description
In the first plot, I am highlighting how University of Illinois buildings have been constructed over time from 1800 to 2025. Detailed information of the building is included such as the total floors, the square footage, and the usage types. 
On the top, a linked histogram with Year Constructed will show how many buildings were built within every 5 years,which helps smooth out year-to-year fluctuations and makes long-term construction patterns easier to see. By clicking a bar, it will highlight the time range in both the histogram and the scatterplot via opacity and color changes. For users, it is easier for them to focus on specific construction eras. Scatterplot is applied with circle marks where the x-axis is Year Constructed and the y-axis is Total Floors. The size of the circle marks are encoding Square Footage so that buildings with larger square footage will visually stand out to the viewers. As for the design choices, usage description is encoded with colors to compare how education, residential, and other types of buildings are distributed across time and number of floors. Tooltips are applied to allow users to see location context and building information on hover. For users, it is easier for them to focus on specific construction eras. If I had more time, I would experiment with log-scaled encodings for square footage to reduce overlap in years with many buildings and add more filters like dropdown buttons to let users explore specific campuses or usage types. 


# In Use Buildings Acquired After 2000 by Government Department

<vegachart schema-url="{{ site.baseurl }}/assets/json/gov_building.json" style="width: 80%"></vegachart>
### Description
In the second plot, I am highlighting how many in-use government buildings acquired after 2000 are managed by different Illinois departments and how each department's acquisitions change over time. The horizontal bar chart on the left shows the total number of buildings acquired by each department. The departments are sorted by count so the departments having more properties stand out. I removed the “Department of” prefix from labels to keep the y-axis concise and easier to read. Color encodes the departments, and interactive selection is applied on all bars so the chosen department is emphasized in color while others fade to light gray. This selection is linked to the line chart on the right to demonstrate the number of buildings acquired per year for only the selected department. This will make it easier for users to read the temporal trends without all lines clustered all together. Tooltips are included so users can easily view detailed information about each acquisition, including the department and the number of buildings acquired. If I had more time, I would use County or City data and add filters on them to support more localized analysis, which could examine how each department's building acquisitions and related budgeting differ across regions.

<!-- these are written in a combo of html and liquid -->

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/tinayang922/tinayang922.github.io/blob/main/python_notebooks/Workbook_HW6.ipynb" text="The Analysis" %}
</div>