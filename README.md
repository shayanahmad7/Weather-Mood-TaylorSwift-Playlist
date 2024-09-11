# Taylor Swift Weather-Based Playlist Generator

## Overview

This project is a Python-based tool that generates a customized **Taylor Swift playlist** based on the weather in any given city. It uses two APIs, **OpenWeatherMap** and **Spotify**, to fetch current weather data and generate a playlist of Taylor Swift songs that match the mood inferred from the weather.

## Features

- Fetches real-time weather data for any city in the world.
- Infers the user's mood based on the current weather conditions (e.g., clear skies, rain, snow, temperature).
- Matches the mood with Taylor Swift songs based on their audio features (e.g., energy, valence).
- Returns a randomly selected playlist of 10-15 songs that match the mood.

## APIs Used

### 1. OpenWeatherMap API
- **Purpose**: To get the current weather data of any city provided by the user.
- **Data Fetched**: Temperature, weather condition (e.g., clear sky, rain, snow).

### 2. Spotify API
- **Purpose**: To fetch Taylor Swift's albums and songs and retrieve the audio features (energy, valence) to match the user's mood.
- **Data Fetched**: Songs, albums, and their audio features.

## How It Works

1. The user enters the name of a city.
2. The script fetches the current weather conditions using the OpenWeatherMap API.
3. Based on the weather, the script determines the user's mood. For example:
   - **Sunny and warm** = Happy
   - **Cloudy** = Reflective
   - **Rainy** = Melancholic
4. The Spotify API is then used to fetch Taylor Swift's songs.
5. Songs are filtered based on audio features (like energy and valence) to match the mood.
6. A playlist of 10-15 songs is randomly selected and returned to the user, along with direct Spotify links.

## How to Set Up

### Prerequisites

1. You need API keys for both OpenWeatherMap and Spotify:
   - [OpenWeatherMap API Key](https://home.openweathermap.org/users/sign_up)
   - [Spotify Developer API Key](https://developer.spotify.com/dashboard/applications)

### Using Google Colab Secrets for API Keys

In **Google Colab**, you can store and retrieve your API keys using the built-in Secrets feature, which securely handles your credentials.

Here’s how to set it up:

1. Click on the **secrets** tab in the left sidebar in Google Colab.
2. Set your keys like this:
   - `WEATHER_API_KEY`: Your OpenWeatherMap API Key
   - `SPOTIFY_CLIENT_ID`: Your Spotify Client ID
   - `SPOTIFY_CLIENT_SECRET`: Your Spotify Client Secret

3. After setting up the secrets, your code can access them as environment variables directly.

### Setup Instructions

1. Clone the repository to your local machine or open it in Google Colab.

2. Make sure to define the secrets in Colab as described above. In your code, you can access these secrets using the following environment variables:

```bash
# Example of accessing secrets stored in the Google Colab secrets tab:
os.environ['WEATHER_API_KEY']
os.environ['SPOTIFY_CLIENT_ID']
os.environ['SPOTIFY_CLIENT_SECRET']
```

3. Run the code in the notebook or your local environment.

4. Enter a city name when prompted, and the tool will generate a playlist based on the current weather.


### Error Handling

    If the weather API fails (e.g., city not found), the code will return an error message.
    If the Spotify API call fails (e.g., rate limit exceeded), it will print an error message.

### Example

    Input: New York City
    Output: Playlist of 15 Taylor Swift songs matching the "calm" mood, including:
        Song: "Invisible String" (Album: folklore)
        Song: "Daylight" (Album: Lover)
        Song: "The Archer" (Album: Lover)

### Future Improvements

    Add more artists to match different moods beyond just Taylor Swift.
    Implement more advanced filtering based on additional weather conditions like wind speed or humidity.
    Add an option to generate playlists from other genres.

### Resources

    OpenWeatherMap API Documentation
    Spotify API Documentation
    Google Colab Documentation

### License

This project is licensed under the MIT License - see the LICENSE file for details.
