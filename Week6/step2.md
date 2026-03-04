# Writing the API Service Class

***

## Create the File

In zapp.run, create a new file inside `lib/` folder:

```
lib/weather_service.dart
```

> This file will be responsible for **only one thing** — fetching weather data. Keeping it separate from your UI is good practice (called **Separation of Concerns**).

***

## Line 1: Import the `http` Package

Type this as the very first line:

```dart
import 'package:http/http.dart' as http;
```

**What this means, word by word:**


| Word | Meaning |
| :-- | :-- |
| `import` | Bring in an external tool |
| `'package:http/http.dart'` | The http package you added in pubspec.yaml |
| `as http` | Give it a nickname so you call it as `http.get(...)` later |

> 🧪 **Test:** Save the file. No red underlines = import is working.

***

## Line 2: Import `dart:convert`

On the next line, add:

```dart
import 'dart:convert';
```

**Why?**

- The API returns raw **text** (a JSON string)
- `dart:convert` gives you `jsonDecode()` to turn that text into a **Dart Map** you can read like `data['main']['temp']`

***

## Define the Class

```dart
class WeatherService {

}
```

**What this means:**

- `class` = a blueprint / container for related code
- `WeatherService` = the name (capital first letter is Dart convention)
- Everything inside `{ }` belongs to this class

***

## Add Your API Key \& Base URL (Inside the class)

```dart
  final String apiKey = 'YOUR_API_KEY_HERE';
  final String baseUrl = 'https://api.openweathermap.org/data/2.5/weather';
```

**Word by word:**


| Word | Meaning |
| :-- | :-- |
| `final` | This value will **never change** after being set |
| `String` | The data type — it holds text |
| `apiKey` | Variable name (camelCase is Dart convention) |

> ⚠️ Replace `YOUR_API_KEY_HERE` with the key you got in Stage 1.

***

## Write the Fetch Function (The Big One)

Add this inside the class, below the variables:

```dart
  Future<Map<String, dynamic>> fetchWeather(String city) async {
    final url = Uri.parse('$baseUrl?q=$city&appid=$apiKey&units=metric');
    final response = await http.get(url);

    if (response.statusCode == 200) {
      return jsonDecode(response.body);
    } else {
      throw Exception('Failed to load weather');
    }
  }
```

Let's break this down **line by line:**

### Line A — The Function Signature

```dart
Future<Map<String, dynamic>> fetchWeather(String city) async {
```

| Part | Meaning |
| :-- | :-- |
| `Future<...>` | This function will return data **eventually** (not instantly — it waits for internet) |
| `Map<String, dynamic>` | The data it returns — a key-value structure like `{"temp": 31}` |
| `fetchWeather` | The function name |
| `String city` | It accepts one input — a city name as text |
| `async` | Marks the function as asynchronous (it can wait/pause) |

### Build the URL

```dart
final url = Uri.parse('$baseUrl?q=$city&appid=$apiKey&units=metric');
```

- `$baseUrl`, `$city`, `$apiKey` = **string interpolation** — Dart inserts the variable values
- `Uri.parse()` = converts your text URL into a proper URI object that `http.get` understands


### Make the API Call

```dart
final response = await http.get(url);
```

- `await` = **pause here and wait** until the internet responds
- `http.get(url)` = sends a GET request to the weather server
- `response` = stores everything the server sends back


### Check if it Worked

```dart
if (response.statusCode == 200) {
```

- `statusCode == 200` means **success** (like a green light from the server)
- Any other code (404, 401, etc.) means something went wrong


### Return the Data

```dart
return jsonDecode(response.body);
```

- `response.body` = the raw JSON text string from the server
- `jsonDecode(...)` = converts that text into a Dart Map you can use

***

## 🧪 Your Complete `weather_service.dart` So Far

```dart
import 'package:http/http.dart' as http;
import 'dart:convert';

class WeatherService {
  final String apiKey = 'YOUR_API_KEY_HERE';
  final String baseUrl = 'https://api.openweathermap.org/data/2.5/weather';

  Future<Map<String, dynamic>> fetchWeather(String city) async {
    final url = Uri.parse('$baseUrl?q=$city&appid=$apiKey&units=metric');
    final response = await http.get(url);

    if (response.statusCode == 200) {
      return jsonDecode(response.body);
    } else {
      throw Exception('Failed to load weather');
    }
  }
}
```


