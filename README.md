# Qliksense Extension integrating amCharts.

## Introduction
This is a work in progress project for integrating [amCharts](https://www.amcharts.com/) charting library into qliksense extension(s).

At the moment this project is an implementation of a combo chart that includes a waterfall type measure.

The goal of the combo chart is to give the user alooot of settings to mess around with, the screenshot examples below are just a small subset of outcomes you can produce. It is definatly possible to make visualizations that don't make sense or don't follow best practices or similar. I think the standard QlikSense charts are really good at helping the user make charts that make sense and follow best practices, but that sometimes removes alot of flexibility. When developing this extension I will to a greater degree choose flexibility even when it means giving the users settings that potentially can make graphs that don't make sense.

Please rate & give feedback! If you wan't to contribute feel free to message me on github.

### Current Development
Sorry that I havn't been able to do any updates, for the last 6 months. Doing this pro-bono makes it hard to justify spending 2 much time on it. I am reading all your messages & issues and reaching a critical mass will encourage me to do an update on the extension like i did today  (17/11/2016), albeit it being a code quality update only.

### Latest 5 Changes
* Added option to add and modify a categoryaxis scrollbar after several people requested it.
* Did a major change to the coding structure. The preperation of datainput into amCharts are now beeing done in an OOP solution in the 'dataProvider.js' file.
This doesnt change anything on the front-end, but will make it alot easier to make changes going forward.
* Made the calculated colors now appear on legends as a calculation disregarding the chart dimensions. (Think how the color calculations would calculate on a total row). Added a calculation field to calculate the minimum value for the left and right axis. Added a screenshot to explain usage of the the mentioned changes.
* The line & fill colors on the measures are now entered via expression and applied on each dimension/x-axis value. Which means that you can color stuff based on your data e.g. if(sum(x)>sum(y), 'rgb(0,220,0)', 'rgb(220,0,0)'). Another usefull way that I usually use this for is when you have a dimensional heirarchy that is the 'center-piece' of your application, then you can load in RGB/Hex values that correspond to that heirarchy e.g. ProductGroup=FX,Hex=#123123. And then color your data consistently based on that. However for that to be more usefull I have to look into implementing multidimensionality in the amCombo chart.
* Added theme's setting in the amChart settings. If you make any setting that conflicts with the theme it will choose your setting. E.g. choosing to change color of a measure. See screenshots below of the themes.

## Screenshots
### Added scrollbar option for category axis
![Category Axis Scrollbar](comboPictures/categoryAxisScrollbar.PNG)
### Calculated colors and calculated minimum axis values
![Calc colors & minimum axis values](comboPictures/comboColorFixes.PNG)
### amChart themes.
![New themezz](comboPictures/comboThemes.PNG)
### New method for creating waterfall's in the combo chart.
![New waterfall method](comboPictures/comboNewWaterfall.PNG)
### Combo chart (waterfall measure type)
![Waterfall Chart Screens](comboPictures/comboFall.PNG)
### Random settings screens.
![Combo Chart Screens](comboPictures/comboRandom.PNG)
### Combo chart (silly visualizations)
![Really stupid combo charts](comboPictures/sillyGraphs.PNG)
### Combo Chart (New measure Opacity)
![Combo Chart Opacity](comboPictures/areaOpacity.PNG)
### Combo Chart (New stacking settings)
![Combo Chart Opacity](comboPictures/stacking.PNG)

## How to use
Import amCombo.zip into your qliksense dev-hub extensions folder.

## Documentation
When using the amCombo chart the naming and structure follows that of the amCharts API.
* The additional properties on the measures are a subset of the API properties [amGraph](https://docs.amcharts.com/3/javascriptcharts/AmGraph).
* The properties in the amCharts section are a subset of the API properties of the [amSerialChart](https://docs.amcharts.com/3/javascriptcharts/AmSerialChart) and its descendant objects (valueAxes, legend, titles & categoryAxis).

## Disclaimer
I'm in no way affiliated with amcharts.com. Their library is free to use for commercial purposes with the caveate that you must include the link to their website in the charts (as seen on the top left of the chart screenshots). If you would want a version without links to amcharts.com they would have to implement a solution to market.qlik.