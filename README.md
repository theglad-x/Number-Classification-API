# Number Classification API

## Overview
This API classifies a given number based on its mathematical properties and provides a fun fact about it.

## Features
- Determines if a number is prime, perfect, or an Armstrong number.
- Classifies numbers as odd or even.
- Computes the digit sum of the number.
- Retrieves a fun fact using the Numbers API.
- Returns responses in JSON format.
- Handles invalid input gracefully.
- Supports CORS for cross-origin requests.

## Technologies Used
- Python
- Flask
- Flask-CORS
- Requests Library

## API Endpoint
### **GET** `/api/classify-number?number=<value>`
#### **Request Parameters**
| Parameter | Type | Description |
|-----------|------|-------------|
| `number`  | int  | The number to classify |

#### **Success Response (200 OK)**
```json
{
    "number": 371,
    "is_prime": false,
    "is_perfect": false,
    "properties": ["armstrong", "odd"],
    "digit_sum": 11,
    "fun_fact": "371 is an Armstrong number because 3^3 + 7^3 + 1^3 = 371"
}
```

#### **Error Response (400 Bad Request)**
```json
{
    "number": "invalid",
    "error": true
}
```

## Installation & Setup
### **1. Clone the Repository**
```sh
git clone https://github.com/theglad-x/Number-Classification-API.git
cd Number-Classification-API
```

### **2. Create a Virtual Environment & Install Dependencies**
```sh
python -m venv venv
source venv/bin/activate 
pip install -r requirements.txt
```

### **3. Run the API Locally**
```sh
python app.py
```
The API will be available at `http://localhost:5000/api/classify-number?number=371`
