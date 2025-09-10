# Microservices Architecture Assignment (Python + Flask)

This repository contains a simple example of Microservices Architecture implemented using Python and Flask.  
The project demonstrates how two independent services can communicate with each other using HTTP.



---

## ⚙️ Environment Setup

Create a virtual environment and install dependencies:

```
# Create and activate virtual environment
python3 -m venv venv
source venv/bin/activate    # macOS/Linux

# Install dependencies
pip install -r requirements.txt
```

1. User Service
   ```
   python3 user_service.py
   ```
   
   - Runs on port 5001
     
     <img width="989" height="185" alt="user_service_running" src="https://github.com/user-attachments/assets/f10666ad-7664-4eb8-bba7-7490dfd47687" />

   - Manages user data (create, retrieve)  
   - Stores data in an in-memory dictionary


<img width="994" height="259" alt="user_service" src="https://github.com/user-attachments/assets/7947bc53-ea85-4a6b-a05d-00a35e624392" />

2. Order Service
   ```
   python3 order_service.py
   ```
   
   - Runs on port 5002
     
  <img width="993" height="190" alt="order_service_running" src="https://github.com/user-attachments/assets/8f0355cf-663a-4841-9083-7db49e6a3041" />
  
   - Manages order data (create, retrieve)  
   - Fetches user details from the User Service when retrieving an order
  
     <img width="989" height="265" alt="order_service" src="https://github.com/user-attachments/assets/c26fb25d-e016-416c-8df9-96a174ddd55d" />





