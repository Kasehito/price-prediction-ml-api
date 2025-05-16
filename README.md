# Machine Learning Prediction API

A Flask-based REST API that serves a custom-trained Gradient Boosting Regressor model for making predictions.

## Project Overview

This project implements a web API that exposes a trained machine learning model through HTTP endpoints. The model is a Gradient Boosting Regressor that has been custom-trained to make predictions based on specific input features.

## Features

- RESTful API built with Flask
- Custom-trained Gradient Boosting Regressor model
- JSON-based request/response format
- Easy-to-use prediction endpoint
- Model persistence using joblib

## Technical Stack

- Python
- Flask (Web Framework)
- scikit-learn (Machine Learning Library)
- joblib (Model Serialization)

## Installation

1. Clone the repository or download the project files

2. Install the required dependencies:
```bash
pip install flask scikit-learn joblib
```

## Usage
1. Start the server:
```
python testing_deploy.py
```
2. The API will be available at http://localhost:5000
3. To make predictions, send a POST request to the /predict endpoint with your data:
```
import requests
import json

# Example request
data = {
    'data': [[feature1, 
    feature2, ...]]  # 
    Replace with your actual 
    feature values
}

response = requests.post
('http://localhost:5000/
predict', json=data)
prediction = response.json()
['prediction']
```
## API Endpoints
### POST /predict
Makes predictions using the trained Gradient Boosting Regressor model.

Request Format:

```
{
    "data": [[feature1, 
    feature2, ...]]
}
```
Response Format:

```
{
    "prediction": 
    [predicted_value]
}
```
Important Notes:

- The input data must be a 2D array, even for single predictions
- Make sure to provide all required features in the correct order
- All features should be properly scaled/preprocessed as per the training data
## Model Information
The project uses a custom-trained Gradient Boosting Regressor model that has been saved using joblib serialization ( gbr_model.joblib ). The model must be present in the project directory for the API to function correctly.

## Development Mode
The API runs in debug mode by default, which provides detailed error messages and auto-reloading capabilities. For production deployment, it's recommended to disable debug mode and implement proper security measures.

## Security Considerations
When deploying to production:

1. Disable debug mode
2. Implement proper input validation
3. Add authentication if needed
4. Use HTTPS
5. Set appropriate CORS policies
## Error Handling
The API will return appropriate error messages if:

- The request format is incorrect
- Required features are missing
- The input data type is invalid
## Contributing
Feel free to submit issues, fork the repository, and create pull requests for any improvements.


## Author
- [Kasehito](https://github.com/Kasehito)

## Acknowledgments
- Thanks to scikit-learn for the machine learning framework
- Flask team for the web framework
- and Dicoding for help me learn the fundamental
