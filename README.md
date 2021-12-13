# World_Weather_Analysis
API Project

**Project Overview**
The purpose of this project is to create a Python script for a imaginary travel company that will use input  to filter potential travel destinations worldwide. After selecting four cities to create a travel itinerary, Google Maps Platform APIs are used to create travel routes and a markup map.

**Software and APIs**
Software: Python 3.7, Anaconda, Jupyter Notebook.

**Google Maps Platform: Directions API, Places API.**
To set up a new gmap API key, click here (https://mapsplatform.google.com/) and select "Get Started."

**OpenWeatherMap: Current Weather Data.**
To set up a new OpenWeatherMap API key, click here (https://openweathermap.org/) to create a free account.

With respect to this project, its critical to create a config.py file with your specific API key information, please see the example below. Do not upload or share your API key information with anyone. It is recommended to add "config.py" to the gitignore to keep your key information private.
                 weather_api_key="your-weather-api-key-here"
                 g_key="your-google-maps-api-key-here"
                 
**Gatering City and Weather Data**
To start this project, it was necessary to create a data file with city information; weather and location data. I started by generating a random set of 2,000 latitude and longitude combinations using the NumPy .random.uniform() method. These coordinates are then used with citipy to get the nearest city. If an insufficient number of cities are generated, rerun the code or expand the size of the random search. I then performed an API call using OpenWeatherMap (Current Weather Data) and parsed the JSON for the needed data. After looping through all of the cities, the data is added to a DataFrame and it is then exported into a .csv file as required for further analysis. 

**Generating a Worldwide Travel Map**
The user will be asked for the minimum and maximum temperature they would like for thier trip. With the .csv file generated in the previous section, the Pandas .loc[] method is used to filter the data based on the user input. Using the Google Places API, a hotel is found that is within or more than  5,000 meters of each city by iterating through the DataFrame with the given parameters. This new DataFrame is used to create an updated .csv file with Hotel generated data. Using a customized info box, gmaps marker_layer, and heat_layer, the user is presented with an interactive map to look search for travel destinations. Please see the refer to World_Weather_Analysis/ Vacation_Itinerary/.... to see screen shots of these data. 
