
# Museum Trip Planner API

This is a Flask-based API that helps plan a trip to museums in various cities. It allows users to input a list of cities and a starting location (either "current location" or a specific museum) and returns a sorted list of museums by their distance from the starting location.

## Features

- Fetch museums from specified cities.
- Plan a trip starting from either the current location or a specific museum.
- Calculate distances using geodesic measurements.
- Sort museums by their distance from the starting location.

## Endpoints

### `POST /plan_trip`

**Description:** Plans a trip to museums based on the provided cities and starting location.

**Request Body:**
```json
{
  "cities": ["City1", "City2","..."],
  "start_location": "current location" // or a specific museum name
}
```

**Response:**
```json
{
  "trip_plan": [
    {
      "name": "Museum Name",
      "latitude": 12.34,
      "longitude": 56.78,
      "city": "CityName",
      "imageUrl": "http://example.com/image.jpg",
      "distance": 10.5
    },
    ...
  ]
}
```

### `POST /show_museums`

**Description:** Shows all museums in the provided cities.

**Request Body:**
```json
{
  "cities": ["City1", "City2",...]
}
```

**Response:**
```json
[
  {
    "name": "Museum Name",
    "latitude": 12.34,
    "longitude": 56.78,
    "city": "CityName",
    "imageUrl": "http://example.com/image.jpg"
  },
  ...
]
```

## Setup

### Prerequisites

- Python 3.8 or higher
- Flask 3.0.3
- Flask-CORS 4.0.1
- Flask-RESTX 1.3.0
- Geopy 2.4.1
- Requests 2.32.3

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/museum-trip-planner.git
   cd museum-trip-planner
   ```

2. Create a virtual environment and activate it:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Running the Application

1. Start the Flask application:
   ```bash
   gunicorn --bind 0.0.0.0:8080 run:app
   ```

2. The API should now be accessible at `http://localhost:8080`.

### Deploying on Render

1. Create an account on [Render](https://render.com/).
2. Create a new Web Service on Render.
3. Connect your GitHub repository to Render.
4. Set the build and start commands:
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `gunicorn --bind 0.0.0.0:8080 run:app`
5. Deploy the service.

### Note

Make sure to set the appropriate environment variables and configurations on Render to match your local setup.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Flask
- Flask-RESTX
- Geopy
- Render

## API Link

The API is hosted at: [https://trip-planner-flask.onrender.com](https://trip-planner-flask.onrender.com)
