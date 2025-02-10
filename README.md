# Number Classification API
A simple API that classifies numbers based on mathematical properties and provides a fun fact using Flask and FastAPI.

## Features
- Check if a number is prime, perfect, or Armstrong.
- Determine if a number is odd or even.
- Calculate the digit sum of a number.
- Fetch a fun fact about the number from NumbersAPI.

## Technologies Used
- Python 3.9
- Flask (for development and debugging)
- FastAPI & Uvicorn (for production-ready deployment)
- Docker

## Getting Started

### Prerequisites
Ensure you have the following installed
- Python 3.8+
- Docker
- An AWS EC2 instance

### Installation
1. Clone the repository
``` bash
git clone https://github.com/theglad-x/Number-Classification-API.git
cd Number-Classification-API
```

2. Create a virtual environment
``` bash
python3 -m venv venv
source venv/bin/activate
```

3. Install dependencies:
``` bash
pip install -r requirements.txt
```

4. Run the application locally
``` bash
python app.py
```
The app will be running on http://localhost:5000

## Running with Docker

### Build and Run the Docker Container
1. Build the Docker image
``` bash
docker build -t number-classification-api .
```
2. Run the container:
``` bash
docker run -p 8000:8000 number-classification-api
```
The API will be available at http://localhost:8000

## Deploying on AWS EC2

### Steps:

1. SSH into your EC2 instance
``` bash
ssh -i your-key.pem ubuntu@your-ec2-instance-ip
```
2. Install Docker
``` bash
sudo apt update
sudo apt install docker.io -y
```

3. Clone the repository on the EC2 instance
``` bash
git clone https://github.com/theglad-x/Number-Classification-API.git
cd Number-Classification-API
```

4. Build and run the container on EC2
``` bash
docker build -t number-classification-api .
docker run -d -p 8000:8000 number-classification-api
```

5. Open port 8000 in your EC2 security group to allow access.

6. Access the API via
``` http://your-ec2-instance-ip:8000/api/classify-number?number=6 ```

## API Endpoints

### Classify a Number

Endpoint
``` bash
GET /api/classify-number?number=<num>
```

Example Request:
``` bash
GET http://localhost:8000/api/classify-number?number=6
```

Example Response:
``` bash
{
  "number": 6,
  "is_prime": false,
  "is_perfect": true,
  "properties": ["even"],
  "digit_sum": 6,
  "fun_fact": "6 is a perfect number because the sum of its divisors (1,2,3) equals 6."
}
```
