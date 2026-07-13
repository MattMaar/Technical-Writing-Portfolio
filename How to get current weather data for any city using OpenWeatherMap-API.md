"How to get current weather data for any city using OpenWeatherMap-API"

**Prerequisites**:
- Browser
- An account on https://openweathermap.org/
- Your own API-Key


In this guide you will learn how to get weather data for your city (or any city) using OpenWeatherMap - all without the ability to program or any computer background.
After registering a free account on the website https://openweathermap.org/ in order to generate your API-Key, you can use it to create the weather data for the city of your choosing.

1. Create an Account
   In a first step, open the website https://openweathermap.org/ and click on "Register/Login" at the top right. You will then be asked to create an account (or log in if you already have an account). Fill in the fields and confirm you are not a bot. This will send an E-Mail to your connected mail address in order to verify your account. Click on the link in the E-mail you have been sent in order to finish setting up your account.

2. Get your API key
   Next, in order to get your API-key you can either go to the website and click onto your name in the top right, which brings up a drop down menu; here, select "My API keys", which will open a webpage with your API keys. Another way to get this first API key, is to wait a bit and receive an E-mail with this API key after your account has been created. On the webpage with your API keys, you can also create more keys.

3. Make your first request
   Activation of your API key can take a couple minutes up to a few hours. Once your API key is activated, you can go to https://api.openweathermap.org/data/2.5/weather?q=Innsbruck&appid=YOUR_API_KEY&units=metric (fill in your key where it say "YOUR_API_KEY"). This will give you an output with your weather data of your chosen city in the form of a JSON file. Below you can find an example output:


**Understanding the response**

Output
```{"coord":{"lon":11.3945,"lat":47.2627},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04d"}],"base":"stations","main":{"temp":33.96,"feels_like":33.99,"temp_min":30.71,"temp_max":33.96,"pressure":1017,"humidity":34,"sea_level":1017,"grnd_level":860},"visibility":10000,"wind":{"speed":2.79,"deg":27,"gust":2.64},"clouds":{"all":89},"dt":1783956900,"sys":{"type":2,"id":2003135,"country":"AT","sunrise":1783913472,"sunset":1783969720},"timezone":7200,"id":2775220,"name":"Innsbruck","cod":200}```

The following is a breakdown of some important terms you may find:

- "name" is the name of the city you have chosen
- "weather.main" is the current weather at your chosen location
- "main.temp" is the current temperature at your chosen location
- "main.feels_like" is the "Feels-like-temperature" at your chosen location
- "main.humidity" is the current humidity at your chosen location

**Changing the city**

You can request weather data for any city by changing the name in the URL. 
However, if the city name is made up of multiple words, you will have to use "%20" instead of a space (e.g., New York is New%20York); using a space or an underscore will result in an error message stating ``cod: 404`` "city not found"; compare this to the correct message which gives a ``code 200``message. If you want to see the weather for a city that exists multiple times, simply append the country after a comma (e.g., Vienna,AT).

**Troubleshooting/Common Errors**

-  If you immediately use the API key, you might come across an error message ``401``. This means you have an invalid API key and guides you to a webpage for more information. Invalid API key in this case, however, only means, that your API key has not been activated yet and you might have to wait a few more minutes (up to a few hours) in order for it to work properly.
