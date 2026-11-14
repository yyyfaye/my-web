
# UFO Sightings: Trends and Shapes

**IS 445 — Homework 5.1**

This project explores reported UFO sightings using a dataset containing 80,332 records. Two interactive visualizations examine how sighting reports changed over time and which UFO shapes were most commonly reported across different countries.

[The Data](https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/ufo-scrubbed-geocoded-time-standardized-00.csv) | [The Analysis](https://github.com/yyyfaye/my-web/blob/main/notebooks/ufo_analysis.ipynb)

## Visualization 1: UFO Sightings Over Time

<div id="chart1"></div>

This visualization shows the annual number of reported UFO sightings from 1990 to 2013. The horizontal axis represents the year, while the vertical axis represents the number of sightings. A line chart was chosen because it clearly communicates changes over time. Year is encoded using quantitative position on the x-axis, and sighting count is encoded using quantitative position on the y-axis. The line uses a consistent steel-blue color to emphasize the overall trend rather than differences between categories. In Python, I converted the datetime column to a datetime format, extracted the year, filtered observations to 1990–2013, and grouped the records by year to calculate annual sighting counts. The visualization shows a substantial increase in reported sightings over this period, with a particularly noticeable rise around 2012.

## Visualization 2: Most Common UFO Shapes by Country

<div id="chart2"></div>

This visualization compares the ten most commonly reported UFO shapes across five countries: the United States, Canada, the United Kingdom, Australia, and Germany. A horizontal bar chart was selected because it makes categorical comparisons easy to interpret. UFO shape is encoded using nominal position on the y-axis, while the percentage of sightings is encoded using quantitative bar length on the x-axis. A uniform teal color is used because the bars represent different categories of the same variable, and additional colors are unnecessary for distinguishing them. For data preparation, I removed records with missing country or shape values, standardized the category labels, grouped observations by country and shape, and calculated the percentage of each country's sightings belonging to each shape. I also restricted the display to the ten most common shapes overall to keep the chart readable. Percentages rather than raw counts allow comparisons between countries with very different numbers of reported sightings.

## Interactivity

Both visualizations include interactive features beyond basic pan and zoom. In the first visualization, users can drag across the smaller overview chart to select a range of years, which updates the main line chart to display the selected period. This makes it easier to examine changes within a particular time interval while retaining the context of the full dataset. In the second visualization, users can select a country from a dropdown menu to update the shape distribution. This allows comparisons between countries without displaying several separate charts, reducing visual clutter and making the exploration more focused.

## Data and Source Code

The visualizations were created using Python, Pandas, and Altair and exported as Vega-Lite specifications for display on this Jekyll webpage.

- [View the original UFO dataset](https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/ufo-scrubbed-geocoded-time-standardized-00.csv)
- [View the Python analysis notebook on GitHub](https://github.com/yyyfaye/my-web/blob/main/notebooks/ufo_analysis.ipynb)

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
vegaEmbed("#chart1", "{{ '/charts/sightings_over_time.json' | relative_url }}", {
  actions: false
}).catch(console.error);

vegaEmbed("#chart2", "{{ '/charts/ufo_shapes.json' | relative_url }}", {
  actions: false
}).catch(console.error);
</script>
