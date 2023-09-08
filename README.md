# sample-code-for-a-weather-using-the-open-weather-map-ai
# Sample code for a weather app using the OpenWeatherMap API
import requests

api_key = "YOUR_API_KEY"
city = input("Enter a city: ")

url = f"http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}"

response = requests.get(url)
data = response.json()

if data["cod"] == 200:
    temperature = data["main"]["temp"]
    weather = data["weather"][0]["description"]
    print(f"Weather in {city}: {weather}")
    print(f"Temperature: {temperature}°C")
else:
    print("City not found.")







