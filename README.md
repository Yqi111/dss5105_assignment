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


### **Run the container (choose an available port, e.g., 5151)**
docker run -p 5151:5151 causal-api

### Make sure your app.py ends with:
app.run(host="0.0.0.0", port=5151)


###  **Query the API Use curl or browser to test:**
curl "http://localhost:5151/predict?w=1&x=20"

# Troubleshooting
If you see an error like:

Bind for 0.0.0.0:5050 failed: port is already allocated


That means the port you're trying to use is already occupied by another process or container. To fix it:

Try a different port (e.g., 5151, 8081, 8888)

Update both:

**app.py: ** **app.run(host="0.0.0.0", port=5151)**


Your run command:
- **docker run -p 5151:5151 causal-api**
curl "http://localhost:5151/predict?w=1&x=20"


