# **Causal Effect Estimation API**

This project implements a simple Flask API that estimates stakeholder engagement scores using a linear regression model trained on corporate sustainability data. The model predicts outcomes based on treatment status (`w`) and sustainability spending (`x`), following the Rubin Causal Model framework.

## **Files Overview**

- **`app.py`**: Hosts a Flask server with a `/predict` endpoint. It trains a linear regression model on provided data and returns predicted engagement scores based on user input (`w`, `x`).
- **`Dockerfile`**: Defines the containerized environment with Python 3.10 and all dependencies. It ensures consistent behavior across machines by isolating the environment.
- **`requirements.txt`**: Lists all required Python packages (`flask`, `scikit-learn`, `numpy`) to run the API inside Docker.

## How to Run

### **Build the Docker image**

```bash
docker build -t causal-api .


### ** Run the container (use port 5050 if port 5000 is unavailable)**
docker run -p 5050:5050 causal-api

###  **Query the API Use curl or browser to test:**
curl "http://localhost:5050/predict?w=1&x=20"


