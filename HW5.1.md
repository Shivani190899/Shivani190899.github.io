---
layout: default
title: "HW5.1 – UFO Sightings with Altair"
---
<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

# HW5.1 – UFO Sightings with Altair

I have used the UFO sightings dataset from which I created two visualizations using Python and Altair: a bar chart of sightings per year, and an interactive global map showing UFO sightings with a year slider. Below are my visualizations and explanations.

<p>
  <a class="btn" href="https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/ufo-scrubbed-geocoded-time-standardized-00.csv" target="_blank">The Data</a>
  <a class="btn" href="https://github.com/Shivani190899/Shivani190899.github.io/blob/main/Workbook.ipynb" target="_blank">The Analysis</a>
</p>

---

## Visualization 1 – UFO Sightings Per Year

<div id="plot1"></div>
<script type="text/javascript">
  vegaEmbed('#plot1', 'ufo_years.json');
</script>

- So, for my first visualization, I am plotting a bar chart for showing the number of UFO sightings that were reported every year which will help the viewers to understand and analyse a pattern if any.
- For that, I decided to use a bar chart since its easier to display the comparison of the sightings for every year. On the X axis, I have displayed all the years as an Ordinal value since they should be displayed in a natural order, whereas on Y axis i have displayed a quantitative value ie. the count of UFO sightings. I have also added tooltips so its easier for the viewer to interpret the chart when they hover over it. Also chose a single colour for the bar chart so its not distracting the viewer from the insights that I am trying to display.
- For data transformation, I first loaded the data with correct headers since no headers were present in the dataset. After that I made sure to clean the data since after loadingthe dataset, the datetime column looked like 1/1/2000 23:43 which gets stored like a string and not like real dates which Python does not understand so converted these strings to real time stamps which converts the date to 2000-01-01 23:45:00 format and if no values are present it will change to NaT ie. Not a Time. 
---

## Visualization 2 – UFO Sightings Map with Year Slider

<div id="plot2"></div>
<script type="text/javascript">
  vegaEmbed('#plot2', 'ufo_map.json');
</script>

- In this visualization, I am showing the occurence of UFO sightings around the world by plotting them using the latitude and longitude which will help the users to understand in which geographic area are UFO sightings seen more and that in what area are what UFO shapes seen.
- For designing, I have used circle dots to display the UFO sightings and have placed them using the latitude(x axis) and longitude(y axis). I have also used different colours to display different shapes of UFO. Also, bigger the dot, longer the sighting lasted. I have also added tooltips so whenever the viewer hovers over the dot, they can see details like the city, state, date and shape. I have also chosen different colours for differnt shapes so that it gets easier to distinguish even if they overlap.
- For plot 2, I used the same cleaned dataset but added some extra steps like removed any empty rows from date or latitude or longitude column, since the missing values wouldve been plotted inaccurately and incorrectly. I also replaced the missing values from the shape column to 'Unknown' in order to make sure the shape column remains consistent. Also, since the dataset it very large, I took smaller random sample so its easier and efficient to plot and load the interactive bar chart. Also from the timestamp, I extracted the year field so that I can use it on the year slider.

---

## Interactivity

- For interactivity, I have created a year slider, which on selection will show the listings of different shapes of UFO in different areas of the world for that particular year. This visualisation is a better updated way of displaying UFO sightings since in the bar chart, all year UFO sightings are displayed together, but here, viewer can focus on the UFO sightings from a particular year and can get more information about it like Date, City, State, Country and Shape of that UFO sighting.
---

*Last updated: {{ site.time | date: "%Y-%m-%d" }}*
