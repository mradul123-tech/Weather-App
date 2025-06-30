Overview:
The Weather App is a simple yet powerful web application built using HTML, CSS, and JavaScript. It allows users to enter the name of a city and get real-time weather information like temperature, weather condition, humidity, and wind speed using an external weather API.

🔹 Features:

✅ Search weather by city name

🌡 Displays current temperature

🌧 Shows weather conditions (like cloudy, sunny, rainy)

💨 Shows wind speed and humidity

🎨 Responsive and modern UI design

⚡ Real-time data using API (like OpenWeatherMap)


🔹 Technologies Used:

HTML: Structure of the app (input field, buttons, and result display)

CSS: Styling of the weather card, layout, colors, and icons

JavaScript:

Fetching real-time data from the weather API

Handling user input and displaying results dynamically



🔹 How it Works (Process Flow):

1. User enters a city name in the input field.


2. On clicking the "Search" button, JavaScript triggers an API call to fetch weather data.


3. Data is processed and displayed on the screen, including:

Temperature in °C

Weather condition (like Clear, Cloudy)

Humidity (%)

Wind speed (Km/h)




🔹 Sample Tech Stack:

<!-- HTML -->
<input type="text" id="cityInput" placeholder="Enter city">
<button onclick="getWeather()">Search</button>
<div id="weatherResult"></div>

/* CSS */
body {
  background: linear-gradient(to top, #6dd5ed, #2193b0);
  font-family: Arial, sans-serif;
  text-align: center;
}

// JavaScript
async function getWeather() {
  let city = document.getElementById("cityInput").value;
  let apiKey = "YOUR_API_KEY";
  let response = await fetch(`https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`);
  let data = await response.json();
  document.getElementById("weatherResult").innerHTML = `Temperature: ${data.main.temp}°C`;
}
