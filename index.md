# UFO Sightings: Trends and Shapes

*IS 445 · Homework 5*

What can reported UFO sightings tell us about when people see unusual things in the sky, and how they describe them? I used a dataset of 80,332 sighting reports to explore these questions through two interactive charts.

[The Data](https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/ufo-scrubbed-geocoded-time-standardized-00.csv) · [The Analysis](https://github.com/yyyfaye/my-web/blob/main/notebooks/ufo_analysis.ipynb)

## 1. How have UFO sighting reports changed over time?

<div id="chart1"></div>

This line chart shows the number of UFO sightings reported each year from 1990 to 2013. I used year on the x-axis and sighting count on the y-axis because a line chart makes it easy to follow changes over time. I kept the line blue and used a lighter shade for the overview below it so the focus stays on the trend. 

In Python, I converted the dates, extracted the year, filtered the data to 1990–2013, and counted reports for each year. Reports generally increased over this period, especially toward 2012. The lower chart also lets you drag across a range of years to take a closer look at the main chart without losing the bigger picture.

## 2. What UFO shapes are reported most often?

<div id="chart2"></div>

This bar chart compares the ten most common reported UFO shapes across five countries. Shape is a categorical variable on the y-axis, and the percentage of reports is shown by bar length on the x-axis. I used a single teal color because the shape labels already distinguish the categories, so extra colors would not add much. To prepare the data, I removed rows with missing country or shape information, counted reports by country and shape, and calculated each shape's share of all reports with a known shape in that country. Using percentages helps compare countries with very different numbers of reports. You can switch countries using the dropdown to see how the distribution changes. The ten shapes shown are the most common across the full dataset, not necessarily the top ten in every country.

*Note: These are reported sightings, not verified UFO events. Differences in reporting do not necessarily mean differences in actual activity.*

## Data and notebook

- [Original UFO dataset](https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/ufo-scrubbed-geocoded-time-standardized-00.csv)
- [Python analysis notebook](https://github.com/yyyfaye/my-web/blob/main/notebooks/ufo_analysis.ipynb)

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>
<script>
vegaEmbed("#chart1", "{{ '/charts/sightings_over_time.json' | relative_url }}", {actions: false}).catch(console.error);
vegaEmbed("#chart2", "{{ '/charts/ufo_shapes.json' | relative_url }}", {actions: false}).catch(console.error);
</script>
