Problem statement: Weather Forecasting Tool -

Create a command line tool that accepts a city's name and returns the current weather forecast. Leverage OpenWeatherMap API to fetch weather data and parse it using Python. Your solution should demonstrate how GitHub Copilot can help you with API usage, data parsing, and error handling.# Team-DGNI
Weather Forecasting Tool

solution of this problem in code


import requests

def get_weather(api_key, city):
    url = f"http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}"
    response = requests.get(url)
    weather_data = response.json()

    if weather_data["cod"] != "404":
        # Extract relevant information from the response
        temperature = weather_data["main"]["temp"]
        humidity = weather_data["main"]["humidity"]
        description = weather_data["weather"][0]["description"]

        # Convert temperature from Kelvin to Celsius
        temperature_celsius = temperature - 273.15

        # Display the weather information
        print(f"Weather in {city}:")
        print(f"Temperature: {temperature_celsius:.2f}°C")
        print(f"Humidity: {humidity}%")
        print(f"Description: {description}")
    else:
        print("City not found.")

# Replace 'YOUR_API_KEY' with your actual API key
api_key = 'e135ef9b2e4db60b0b36573754d593b5'
city = input("Enter city name: ")

get_weather(api_key,city)

 In this we use Api key
