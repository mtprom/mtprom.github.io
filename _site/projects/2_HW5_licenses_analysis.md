---
name: HW5 Licenses Analysis
tools: [Python, Altair, Vega-Lite]
image: assets/pngs/cars.png
description: Illinois professional licenses analysis
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# HW5 Licenses Analysis

## Links

**Data Source:** [licenses_fall2022.csv](https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/licenses_fall2022.csv)

**Notebook:** [HW5.ipynb](LINK_TO_YOUR_NOTEBOOK_HERE)

## Visualization 1

This visualization displays the distribution of the top 15 most common license types in the dataset, showing how many licenses exist for each type and their current status (Active, Expired, Not Renewed, etc.). I used a horizontal bar chart format with the License Type encoded as a nominal variable on the y-axis, Count encoded as a quantitative variable on the x-axis, and License Status encoded as a nominal variable using color. The bars are sorted in descending order by total count to make it easy to identify which license types are most prevalent. For the color encoding, I chose the category20 color scheme for License Status because it provides clear visual distinction between the different status categories, making it easy to compare status distributions across license types. In terms of data transformations, I grouped the original dataset by both License Type and License Status to aggregate the counts, then filtered the results to include only the top 15 license types by total count to prevent overcrowding and maintain readability.

<vegachart schema-url="{{ site.baseurl }}/assets/json/hw5_chart1.json" style="width: 100%"></vegachart>

## Visualization 2

This visualization shows the distribution of license statuses across the top 10 states by license count, excluding Illinois to prevent scale distortion since Illinois had an overwhelming number of licenses compared to other states. I used a grouped bar chart with State encoded as a nominal variable on the x-axis (sorted by total count in descending order), Count encoded as a quantitative variable on the y-axis, and License Status encoded as a nominal variable using color with an xOffset to group bars side by side. The color encoding uses the category10 color scheme, as similarly to category20, it provides clear visual distinction between the different status categories, making it easy to compare status distributions across license statuses. For data transformations, I first filtered out all records where the state was Illinois, then identified the top 10 states by total license count, and finally grouped the filtered dataset by both State and License Status to create the aggregated counts used in the visualization. The grouped bar format allows for easy comparison both within states (comparing different statuses) and across states (comparing the same status).

<vegachart schema-url="{{ site.baseurl }}/assets/json/hw5_chart2.json" style="width: 100%"></vegachart>

## Interactivity

The first visualization uses the .interactive() method which provides basic pan and zoom functionality. The second visualization includes a dropdown selector that filters the chart by License Status, which goes beyond basic pan/zoom and represents custom interactivity as required by the assignment. This dropdown makes the visualization clearer by letting users focus on one license status at a time, making state-to-state comparisons easier without visual clutter from other categories.
