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



# Temperature and Atmospheric Conditions by Precipitation Type

intro
<vegachart schema-url="{{ site.baseurl }}/assets/json/precip_type.json" style="width: 100%"></vegachart>
gsdgwgydgwy

<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://github.com/vega/vega/blob/main/docs/data/cars.json" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/jnaiman/online_cv_public/blob/main/python_notebooks/test_generate_plots.ipynb" text="The Analysis" %}
</div>