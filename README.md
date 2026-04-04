# Weather Detector

Weather Detector is a small Django app that lets a user search for a city and view live weather details from the OpenWeatherMap API.

## Features

- Search weather by city name
- Display country, coordinates, temperature, pressure, and humidity
- Rendered with a simple Django template and Bootstrap UI
- Uses SQLite for local development

## Project Structure

```text
.
├── manage.py
├── templates/
│   └── index.html
├── wheather_app/
│   ├── urls.py
│   └── views.py
└── wheather_core/
    ├── settings.py
    └── urls.py
```

## Requirements

- Python 3
- Django

## Setup

```bash
python3 -m venv venv
source venv/bin/activate
pip install django
python manage.py migrate
```

## Run The Project

```bash
python manage.py runserver
```

Open `http://127.0.0.1:8000/` in your browser.

## How It Works

- The home page is served from `wheather_app.views.index`
- Submitting the form sends a `POST` request with a city name
- The view calls the OpenWeatherMap current weather API
- The response data is shown in `templates/index.html`

## Important Note

The OpenWeatherMap API key is currently hardcoded in [wheather_app/views.py](wheather_app/views.py). For a real deployment, move that key into an environment variable and load it from settings instead of committing it in source code.
