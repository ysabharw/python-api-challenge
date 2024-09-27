# python-api-challenge

# WeatherPy

## Overview

WeatherPy is a Python project designed to analyze the relationship between various weather parameters (temperature, humidity, cloudiness, and wind speed) and the latitude of cities around the globe. The project uses the OpenWeatherMap API to retrieve weather data for over 600 cities, processes the data, and visualizes the results through scatter plots and linear regression analysis.

## Technologies Used

* **Python** : The main programming language for data collection and analysis.
* **OpenWeatherMap API** : Provides real-time weather data for cities around the world.
* **Pandas** : A powerful data manipulation library for Python, used to handle and process data.
* **NumPy** : A library used for mathematical and array operations.
* **Matplotlib** : A data visualization library used to generate scatter plots.
* **SciPy** : Used for performing linear regression analysis (specifically, `scipy.stats.linregress`).
* **Citipy** : A Python library used to determine city names based on geographic coordinates.

## Project Workflow

1. **Generating Random Geographic Coordinates:**
   * Random geographic coordinates (latitude and longitude) are generated within specified ranges using NumPy.
   * The `citipy` library is used to map these coordinates to the nearest city.
2. **Retrieving Weather Data:**
   * The OpenWeatherMap API is used to fetch current weather data for each city. The weather data points retrieved include:
     * Maximum Temperature
     * Humidity
     * Cloudiness
     * Wind Speed
     * Latitude/Longitude
3. **Visualizing Relationships:**
   * Scatter plots are generated to examine the relationships between:
     * Latitude vs. Temperature
     * Latitude vs. Humidity
     * Latitude vs. Cloudiness
     * Latitude vs. Wind Speed
   * Linear regression is performed separately for cities in the Northern and Southern Hemispheres for each weather variable.
4. **Data Export:**
   * The processed data is exported into a CSV file for future analysis.

## Key Findings

* **Temperature vs. Latitude:**
  * There is a noticeable linear correlation between latitude and temperature in both hemispheres. As latitude increases in the Northern Hemisphere, temperature decreases, and in the Southern Hemisphere, temperature increases as you move closer to the equator. The R-squared values show a strong correlation.
* **Humidity vs. Latitude:**
  * There is no strong linear correlation between humidity and latitude in either hemisphere, as indicated by very low R-squared values.
* **Cloudiness vs. Latitude:**
  * Similar to humidity, the relationship between cloudiness and latitude does not exhibit a significant linear correlation in either hemisphere.
* **Wind Speed vs. Latitude:**
  * Wind speed also shows weak correlations with latitude. The R-squared values for both hemispheres indicate that wind speed is not strongly dependent on latitude.

## Resources Used

* **OpenWeatherMap API** : [https://openweathermap.org/api]()
  Used to fetch real-time weather data for cities.
* **OpenWeatherMap FAQ (Error 401)** : [https://openweathermap.org/faq#error401](https://openweathermap.org/faq#error401)
  Documentation for resolving the common API authentication error 401 encountered during data retrieval.
* **Citipy** : [https://pypi.org/project/citipy/](https://pypi.org/project/citipy/)
  Used to map latitude and longitude coordinates to city names.
* **Pandas Documentation** : [https://pandas.pydata.org/docs/]()
  Official documentation for the Pandas library, used for data manipulation.
* **Matplotlib Documentation** : [https://matplotlib.org/stable/index.html]()
  Official documentation for creating visualizations and scatter plots.
* **SciPy Documentation** : [https://docs.scipy.org/doc/scipy/]()
  Official documentation for performing statistical analysis, specifically linear regression.
* **Stack Overflow** : [https://stackoverflow.com/](https://stackoverflow.com/)
  Used to troubleshoot various issues, such as API key errors and general coding queries.
* **Python** : [https://www.python.org/](https://www.python.org/)
  Official Python documentation and installation guidelines.

## Data and Visualizations

### Scatter Plots:

* Scatter plots were created to visualize the relationship between weather variables and latitude. These plots are saved in the `output_data` folder:
  * `Fig1.png`: Latitude vs. Temperature
  * `Fig2.png`: Latitude vs. Humidity
  * `Fig3.png`: Latitude vs. Cloudiness
  * `Fig4.png`: Latitude vs. Wind Speed

### Linear Regression:

* Linear regression plots were generated for both the Northern and Southern Hemispheres for each weather variable. These plots can be found in the `output_data` folder:
  * `NH_Temp_vs_Latitude.png`: Northern Hemisphere: Temperature vs. Latitude
  * `SH_Temp_vs_Latitude.png`: Southern Hemisphere: Temperature vs. Latitude
  * `NH_Humidity_vs_Latitude.png`: Northern Hemisphere: Humidity vs. Latitude
  * `SH_Humidity_vs_Latitude.png`: Southern Hemisphere: Humidity vs. Latitude
  * `NH_Cloudiness_vs_Latitude.png`: Northern Hemisphere: Cloudiness vs. Latitude
  * `SH_Cloudiness_vs_Latitude.png`: Southern Hemisphere: Cloudiness vs. Latitude
  * `NH_WindSpeed_vs_Latitude.png`: Northern Hemisphere: Wind Speed vs. Latitude
  * `SH_WindSpeed_vs_Latitude.png`: Southern Hemisphere: Wind Speed vs. Latitude


## Conclusion

* **Temperature** has the strongest linear relationship with latitude.
* **Humidity, cloudiness, and wind speed** show weak or no linear correlations with latitude.
* This project highlights how temperature trends are directly influenced by latitude, while other weather variables seem less impacted.

## Acknowledgements

This project was created as part of a Python-based data analytics bootcamp. Special thanks to the following resources:

* **Bootcamp Starter Code** : Provided by the instructors for initializing the data analysis workflow.
* **OpenWeatherMap** : For access to real-time weather data via API.
* **Python Documentation** : For providing extensive resources and guides on data manipulation and analysis.
* **Stack Overflow** : For helping troubleshoot issues encountered during the project.

# VacationPy

## Overview

VacationPy is a Python-based project designed to help users find ideal vacation spots based on specific weather conditions and visualize these cities on a map. It uses APIs to gather weather data and hotel information, then displays the results on an interactive map.

## Libraries and APIs Used

* **Pandas** : For data manipulation and analysis.
* **Geoapify Places API** : To search for hotels around the ideal vacation cities based on latitude and longitude.
* **HvPlot** : For generating interactive maps with geographic plotting capabilities.
* **Requests** : For handling API requests.
* **Matplotlib** : For generating basic plots.
* **NumPy** : For numerical operations.
* **Cartopy** : For adding geographic projection support.

## How the Program Works

1. **Load City Data** : The program loads weather data from a CSV file generated in  **WeatherPy** .
2. **Filter Cities** : Filters cities based on user-specified weather conditions (e.g., temperature, humidity, cloudiness).
3. **Hotel Search** : The Geoapify Places API is used to search for the nearest hotel for each city.
4. **Interactive Map** : An interactive map is generated using HvPlot, where each point on the map represents a city, and hovering over a city shows its name, country, and nearby hotel.

## External Resources Used

As a student unfamiliar with Python map generation, API handling, and data filtering, the following resources were crucial:

1. **General Python Help** :

* **Stack Overflow** : To search for issues related to Pandas, API handling, and plotting errors.
  * [Using HvPlot with Pandas](https://stackoverflow.com)
  * [API Requests in Python](https://stackoverflow.com)
* **W3Schools** : For basic Python syntax and understanding Pandas and Matplotlib functions.
  * [Pandas DataFrames]()
  * [Matplotlib Plotting]()

1. **API-Specific Resources** :

* **OpenWeatherMap API Documentation** : To understand how to correctly use the OpenWeatherMap API, including setting up API keys and handling different responses.
  * [OpenWeatherMap API Docs]()
  * [OpenWeatherMap Error 401 FAQ](https://openweathermap.org/faq#error401)
* **Geoapify Places API Documentation** : To learn how to search for places (e.g., hotels) using latitude and longitude coordinates.
  * [Geoapify API Docs]()

1. **Mapping and Plotting Resources** :

* **HvPlot Documentation** : HvPlot’s official documentation helped in understanding how to create interactive geographic plots.
  * [HvPlot Docs]()
  * [HvPlot for Geographic Data]()
* **Cartopy and GeoViews** : These libraries helped configure geographic projections for maps, enabling better visualization of cities around the globe.
  * [Cartopy Documentation]()
  * [GeoViews Documentation](https://geoviews.org/)
* **Matplotlib** : Used to understand basic plotting features and how to apply them when working with data visualization.
  * [Matplotlib Color Customization]()

1. **Data Filtering and Cleaning** :

* **Pandas Documentation** : For understanding how to manipulate, clean, and filter data using DataFrames.
  * [Pandas Docs]()
  * [Pandas: Drop Null Values]()
* **Real Python** : A tutorial-based website providing articles and guides for using Python in data analysis.
  * [Real Python: Data Manipulation with Pandas]()

1. **Color and Style Customization** :

* **Color Brewer 2** : For choosing color schemes suitable for geographic and data visualizations.
  * [Color Brewer 2](https://colorbrewer2.org/)
* **HTML Color Codes** : To select and apply the right colors to map points, backgrounds, and labels.
  * [HTML Color Codes](https://htmlcolorcodes.com/)
* **Coolors.co** : A palette generator tool used to decide on suitable colors for the maps.
  * [Coolors Color Palette Generator](https://coolors.co/)

1. **General Python Learning Resources** :

* **Python Docs** : For learning the fundamental Python syntax and libraries.
  * [Python Documentation](https://docs.python.org/3/)
* **GeeksforGeeks** : For guides on Python programming and working with libraries like Pandas and NumPy.
  * [GeeksforGeeks: Data Analysis with Pandas]()

1. **Google Search** :

* **Searching StackOverflow** for common programming challenges related to APIs and interactive plotting, such as handling errors in requests, customizing map outputs, and using color schemes effectively.

## Notes on Color Customization

* **Color Palettes** : Various color codes were used from resources like HTML Color Codes and Color Brewer 2 to ensure clear and visually appealing maps.
* **Dark Background** : In this project, the map’s background was customized to a darker theme to ensure better contrast with city points. The background color was selected based on resources like Color Brewer and HTML Color Codes.
