# Flutter Weather App

## 🗺️ Overview of What We're Building

A **basic weather app** that:

- Takes a city name as input
- Calls the **OpenWeatherMap API**
- Displays temperature, humidity, and weather description[^1]


***

## Get Your API Key

Before writing any Flutter code, you need a free API key from OpenWeatherMap.[^2][^1]

**Steps:**

1. Go to [openweathermap.org](https://openweathermap.org)
2. Click **Sign Up** → create a free account
3. Go to **API Keys** tab in your dashboard
4. Copy your key — it looks like: `a1b2c3d4e5f6...`

> ⚠️ The free key may take **10–15 minutes** to activate after signup.

**Test your key in the browser first:**

```
https://api.openweathermap.org/data/2.5/weather?q=Manila&appid=YOUR_KEY&units=metric
```

You should see a **JSON response** with weather data. This confirms your key works before touching Flutter at all.[^1]

***

## Understand the pubspec.yaml (Dependencies)

Since you're on **zapp.run with Flutter 3.7.3**, you only need **one package** — `http` — to make API calls.[^1]

Open your `pubspec.yaml` and find the `dependencies:` section. Add this **one line**:

```yaml
dependencies:
  flutter:
    sdk: flutter
  http: ^0.13.6      # ← ADD THIS LINE ONLY
```

**Why `http`?**

- It allows your app to send a GET request to the weather API URL
- `^0.13.6` means "version 0.13.6 or any compatible newer version"

> 🧪 **Test this stage:** After saving `pubspec.yaml` on zapp.run, the packages should auto-resolve. You'll see no red errors in the editor if the dependency loaded correctly.

***

## Understand the API Response (JSON)

Before coding the UI, study what the API actually returns. When you open that browser URL from Stage 1, you'll get JSON like:[^1]

```json
{
  "name": "Manila",
  "main": {
    "temp": 31.5,
    "humidity": 78
  },
  "weather": [
    { "description": "scattered clouds" }
  ]
}
```

**What each field means:**


| JSON Key | What It Holds |
| :-- | :-- |
| `name` | City name |
| `main.temp` | Temperature in °C (because we added `units=metric`) |
| `main.humidity` | Humidity percentage |
| `weather[^0].description` | Short weather text |

> 🧪 **Test this stage:** Manually read the JSON in your browser. Identify where `temp`, `humidity`, and `description` are located — you'll need this when parsing in Dart.

***


[^1]: https://www.linkedin.com/pulse/building-weather-app-flutter-using-rest-apis-durga-jayasai-pillagolla-1tlgc

[^2]: https://openweathermap.org/api

[^3]: https://www.youtube.com/watch?v=6wTl0yqgBzU

[^4]: https://www.youtube.com/watch?v=ITY5MowgDYg

[^5]: https://digitalcurry.in/flutter-recipe-create-a-weather-app-in-flutter-integrating-apis-and-handling-data-0c4649ba4db1

[^6]: https://www.youtube.com/watch?v=_83MVDtZbzg

[^7]: https://github.com/bizz84/open_weather_example_flutter

[^8]: https://www.youtube.com/watch?v=6Xa4ejr57OM

[^9]: https://flutterawesome.com/a-simple-weather-app-using-openweathermap-api-and-flutter/

[^10]: https://www.youtube.com/watch?v=aPc9ZaRe2nI

[^11]: https://www.youtube.com/watch?v=ufRNzt2DhmA

[^12]: https://www.youtube.com/watch?v=msoKuk-5QFg

[^13]: https://www.youtube.com/watch?v=MMq4wkeHkPc

[^14]: https://flutlab.io/docs/work-with-rest-apis-in-flutter-weatherapp-example

[^15]: https://bloclibrary.dev/tutorials/flutter-weather/


