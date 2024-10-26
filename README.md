# Real-Time-Data-Processing-System-for-Weather-Monitoring-with-Rollups-and-Aggregates

This project is a web-based weather monitoring application that retrieves and displays current weather conditions and forecasts for selected cities. Built with Flask, the app integrates with the OpenWeatherMap API to fetch real-time weather data. Key features include displaying current weather, forecast information, and generating alerts based on specific weather conditions. 

## Real-Time-Data-Processing-System-for-Weather-Monitoring-with-Rollups-and-Aggregates
```bash
Real-Time-Data-Processing-System-for-Weather-Monitoring-with-Rollups-and-Aggregates
├── app
│   ├── __init__.py
│   ├── alerting.py
│   ├── config.py
│   ├── data_processing.py
│   ├── data_retrieval.py
│   ├── models.py
│   ├── visualizations.py
│   ├── static
│   │   └── styles.css
│   ├── templates
│   │   └── index.html
│   └── tests
│       ├── __init__.py
│       └── test_data_retrieval.py
├── apikey.txt
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
└── run.py
```
## Getting Started

### Prerequisites


Python 3.8 or higher
Docker (optional, for container deployment)
OpenWeatherMap API key (store in apikey.txt)

### Installing Dependencies

Install the required Python packages using pip:
```bash
    pip install -r requirements.txt
```
## Configuration

Configure application settings in app/config.py or via environment variables:

SQLALCHEMY_DATABASE_URI: Database connection string (default: SQLite)
OPENWEATHERMAP_API_KEY: API key for OpenWeatherMap (store in apikey.txt)
WEATHER_UPDATE_INTERVAL: Weather data update interval (in seconds)
ALERT_THRESHOLD_TEMP: Temperature threshold for alerts (in Celsius)
ALERT_CONSECUTIVE_COUNT: Number of consecutive updates triggering alerts

## Running the Application

To run the application locally:
```bash
    python run.py
```

The application will be accessible at http://127.0.0.1:5000/.

## Running with Docker

To build and run the application using Docker, use the following commands:
```bash
    docker-compose build
    docker-compose up
```
This will start the application and PostgreSQL database in separate containers. Access the application at http://127.0.0.1:5000/.

## Testing

Unit tests are located in the tests/ directory. To run the tests:
```bash
    python -m unittest discover -s tests
```
## Usage

- Home Page: Enter the city name and select the temperature unit (Celsius, Fahrenheit, Kelvin) to get the current weather and forecast.
- Weather Data: The app fetches and displays current temperature, weather description, humidity, and wind speed.
- Forecast Data: Displays a forecast summary for the next few intervals (e.g., 3-hour intervals).

## Files and Modules
app/__init__.py: Initializes the Flask app and database.
app/alerting.py: Handles alert logic based on weather conditions.
app/config.py: Holds configuration settings, including API keys and thresholds.
app/data_processing.py: Processes and summarizes weather data.
app/data_retrieval.py: Manages data retrieval from OpenWeatherMap API.
app/models.py: Database models for weather data storage.
app/visualizations.py: (Optional) Visualization module for weather data.
static/styles.css: CSS styling for the app.
templates/index.html: HTML template for the main interface.
tests/test_data_retrieval.py: Unit tests for data retrieval and processing.

## Acknowledgements
-Thanks to OpenWeatherMap for providing the weather API, and to Flask, SQLAlchemy, and other open-source tools used in this application.