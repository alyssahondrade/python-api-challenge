# python-api-challenge
Module 6 Challenge - UWA/edX Data Analytics Bootcamp

Github repository at: [https://github.com/alyssahondrade/python-api-challenge.git](https://github.com/alyssahondrade/python-api-challenge.git)

## Table of Contents
1. [Introduction](https://github.com/alyssahondrade/python-api-challenge/tree/main#introduction)
    1. [Goal](https://github.com/alyssahondrade/python-api-challenge/tree/main#goal)
    2. [Repository Structure](https://github.com/alyssahondrade/python-api-challenge/tree/main#repository-structure)
    3. [Dataset](https://github.com/alyssahondrade/python-api-challenge/tree/main#dataset)
2. [Approach](https://github.com/alyssahondrade/python-api-challenge/tree/main#approach)
    1. [WeatherPy](https://github.com/alyssahondrade/python-api-challenge/tree/main#weatherpy)
    2. [VacationPy](https://github.com/alyssahondrade/python-api-challenge/tree/main#vacationpy)
3. [References](https://github.com/alyssahondrade/python-api-challenge/tree/main#references)

## Introduction
### Goal
The goal is to investigate the question `"What is the weather like as we approach the equator?"`, by investigating the relationships between:
- Latitude vs Temperature
- Latitude vs Humidity
- Latitude vs Cloudiness
- Latitude vs Wind Speed

Given the data gathered to answer the question above, identify cities with "ideal weather conditions" for a vacation.

This will be achieved through two scripts: [`WeatherPy.ipynb`](https://github.com/alyssahondrade/python-api-challenge/blob/main/WeatherPy.ipynb) and [`VacationPy.ipynb`](https://github.com/alyssahondrade/python-api-challenge/blob/main/VacationPy.ipynb).

### Repository Structure
The Jupyter notebooks [`WeatherPy.ipynb`](https://github.com/alyssahondrade/python-api-challenge/blob/main/WeatherPy.ipynb) and [`VacationPy.ipynb`](https://github.com/alyssahondrade/python-api-challenge/blob/main/VacationPy.ipynb) are held in the root directory.

`output` directory contains the results for [`WeatherPy.ipynb`](https://github.com/alyssahondrade/python-api-challenge/blob/main/WeatherPy.ipynb).

### Dataset
[`OpenWeatherMap's Weather API`](https://openweathermap.org/api) was used to retrieve weather data for each city.
[`Geoapify's Places API`](https://www.geoapify.com) was used to retrieve hotels within a radius of the city latitude and longitude.

## Approach
### WeatherPy
1. Setup
    - Generate the cities list with the provided code.
    - Using the [`OpenWeatherMap API`](https://openweathermap.org/api), parse out the latitude, longitude, maximum temperature, humidity, cloudiness, wind speed, country, and date for each city.
2. Create the scatter plots
    - Using Pandas, create the plot, ensuring correct titles, and x- and y-labels.
    - Save each figure to the `output` directory.
    - Display the plot.
3. Compute linear regression
    - Create a function that will calculate the linear regression plot, with parameters for the equation coordinates to ensure it is placed in a readable manner.
    - Separate the data to Northern and Southern hemispheres.
    - Create the linear regression plot for each relationship, for both hemispheres.
    - Calculate the r-value.
    - For each relationship, discuss the linear relationship and any other observations made.

### VacationPy
1. Import the csv of cities from [`WeatherPy.ipynb`](https://github.com/alyssahondrade/python-api-challenge/blob/main/WeatherPy.ipynb).
2. Create a map that displays the point for each city, with the following conditions:
    - Point colour = city name
    - Point size = humidity
3. Narrow the list (10 or fewer cities) to find "ideal weather conditions", defined as:
    - Maximum temperature: 21 to 26 degrees Celsius
    - Maximum wind: 4.1 m/s
    - Cloud cover: 20% to 80%
    - Humidity: 20% to 80%
4. For each city, use the [`Geoapify's API`](https://www.geoapify.com) to find the first hotel location within `10,000 metres` of the city's coordinates.
5. Create a map of the final results, adding the hotel name and city as additional information for each data point.

## References
The code used to create the maps is derived from the Bootcamp Week 6 Day 3.

- [1] PyPlot Annotation [https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.annotate.html](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.annotate.html)

- [2] How to add bold annotated text to a plot [https://stackoverflow.com/questions/36162414/how-to-add-bold-annotated-text-to-a-plot](https://stackoverflow.com/questions/36162414/how-to-add-bold-annotated-text-to-a-plot)

- [3] Add an Empty Column to a DataFrame [https://sparkbyexamples.com/pandas/pandas-add-an-empty-column-to-dataframe/](https://sparkbyexamples.com/pandas/pandas-add-an-empty-column-to-dataframe/)

- [4] What is Latitude? [https://oceanservice.noaa.gov/facts/latitude.html](https://oceanservice.noaa.gov/facts/latitude.html)

- [5] Multiple Linear Regression made simple [https://statsandr.com/blog/multiple-linear-regression-made-simple/](https://statsandr.com/blog/multiple-linear-regression-made-simple/)
