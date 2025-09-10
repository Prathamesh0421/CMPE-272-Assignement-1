
```markdown
# Microservices Architecture Assignment (Python + Flask)

This repository contains a example of **Microservices Architecture** implemented using **Python** and **Flask**.  
The project demonstrates how two independent services can communicate with each other using HTTP.

---

## 📖 Assignment Description

The goal of this assignment is to understand the basics of microservices design.  
We build **two services**:

1. **User Service**  
   - Runs on port **5001**  
   - Manages user data (create, retrieve)  
   - Stores data in an in-memory dictionary  

2. **Order Service**  
   - Runs on port **5002**  
   - Manages order data (create, retrieve)  
   - Fetches user details from the User Service when retrieving an order  


## 📂 Project Structure
```

microservices-architecture-assignment/
├─ user\_service.py       # User Service (port 5001)
├─ order\_service.py      # Order Service (port 5002)
├─ requirements.txt      # Dependencies
└─ README.md             # Project documentation

````

---

## ⚙️ Environment Setup

Create a virtual environment and install dependencies:

```bash
# Create and activate virtual environment
python3 -m venv venv
source venv/bin/activate    # macOS/Linux
venv\Scripts\Activate.ps1   # Windows PowerShell

# Install dependencies
pip install -r requirements.txt
````

---

## ▶️ Running the Services

Open **two terminals** (one for each service).

### Terminal 1 – Start User Service

```
python3 user_service.py
```

Runs on: `http://localhost:5001`

<img width="989" height="185" alt="user_service_running" src="https://github.com/user-attachments/assets/08e1987f-f8a9-4480-a31b-cdc9cc39e4a8" />


### Terminal 2 – Start Order Service

```
python3 order_service.py
```

Runs on: `http://localhost:5002`

<img width="993" height="190" alt="order_service_running" src="https://github.com/user-attachments/assets/b048a74a-d8f2-40c0-b67a-a3cd88449000" />


---

## 📡 Example API Requests

### 🧑 User Service (Port 5001)

* **Get User**

```
curl http://localhost:5001/users/1
```


* **Create User**

```
curl -X POST -H "Content-Type: application/json" \
  -d '{"name":"Charlie","email":"charlie@example.com"}' \
  http://localhost:5001/users
```
```
curl http://localhost:5001/users/3
```

<img width="994" height="259" alt="user_service" src="https://github.com/user-attachments/assets/0c7d564a-7c06-448f-a105-aae02f92c4bb" />

---

### 📦 Order Service (Port 5002)

* **Get Order (with user details)**

```
curl http://localhost:5002/orders/1
```

* **Create Order**

```
curl -X POST -H "Content-Type: application/json" \
  -d '{"user_id":1,"product":"Tablet"}' \
  http://localhost:5002/orders
```
<img width="989" height="265" alt="order_service" src="https://github.com/user-attachments/assets/32727919-6fda-4f26-8dda-7ebc27eca867" />

---

