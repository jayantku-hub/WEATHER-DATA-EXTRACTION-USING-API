# 🌦 Weather Data Extraction using API (Python)

A simple Python project to **fetch real-time weather data using an API**, parse JSON responses, and export the data to a **CSV file**. Built using **Google Colab** for beginners in data analysis and APIs.

---

## Features

* Fetch live weather data using API
* Parse JSON response
* Extract key weather metrics
* Export data to CSV

---

## Tech Stack

* Python
* Google Colab
* requests
* pandas
* WeatherAPI

---

## API Used

* **WeatherAPI**
* Endpoint:

```
http://api.weatherapi.com/v1/current.json
```

> Requires a free API key from WeatherAPI

---

## Data Extracted

* City
* Country
* Temperature (°C)
* Humidity
* Wind Speed
* Weather Condition
* Last Updated Time

---

## Example Code

```python
import requests, pandas as pd

API_KEY = "YOUR_API_KEY"
CITY = "Delhi"

url = "http://api.weatherapi.com/v1/current.json"
params = {"key": API_KEY, "q": CITY, "aqi": "no"}

data = requests.get(url, params=params).json()

df = pd.DataFrame([{
    "City": data["location"]["name"],
    "Country": data["location"]["country"],
    "Temperature_C": data["current"]["temp_c"],
    "Humidity": data["current"]["humidity"],
    "Wind_kph": data["current"]["wind_kph"],
    "Condition": data["current"]["condition"]["text"],
    "Last_Updated": data["current"]["last_updated"]
}])

df.to_csv("weather_data.csv", index=False)
```

---

## Output

* `weather_data.csv` (analysis-ready)

---

## Enhancements

* Multi-city support
* Error handling
* Automation & visualization

---

## Purpose

Ideal for **API learning**, **data analysis beginners**, and **portfolio projects**.


Just say 👍
