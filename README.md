# Real Estate Price Prediction

A property-price prediction demonstration connecting a saved regression model to a Flask API and an HTML/CSS/JavaScript client.

## Why this project matters

The project illustrates a complete inference path: collect property attributes, encode them for a model, return an estimate, and present it through a browser interface.

## Implementation

- `Realestate/Model/realestate.ipynb`: modeling notebook
- `Realestate/Server/server.py`: Flask routes
- `Realestate/Server/util.py`: feature preparation and artifact loading
- `Realestate/Server/artifacts/`: model and column metadata
- `Realestate/Client/`: browser interface
- `Realestate/Real_Estate_Price_Prediction.mp4`: demonstration video

## Run the backend

```bash
git clone https://github.com/Arjun1443/RealestatePricePridiction.git
cd RealestatePricePridiction
python -m pip install flask flask-cors numpy scikit-learn
cd Realestate/Server
python server.py
```

The server must start from its own directory because artifact paths are relative. Serialized model compatibility may require matching the training environment.

## API

- `GET /get_location_names`: supported locations
- `POST /predict_home_price`: JSON or form fields `total_sqft`, `location`, `bhk`, and `bath`

Open `Realestate/Client/app.html` after checking that `app.js` points to your local backend.

## Technical focus

Python · Flask · NumPy · model serialization · feature encoding · HTML/CSS/JavaScript

## Limitations

This is a demonstration estimate, not a property valuation service. Review the training notebook for dataset provenance, target units, and evaluation before interpreting prices. Server error responses currently return JSON without explicitly setting an error status.
