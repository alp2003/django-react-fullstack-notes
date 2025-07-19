# 🧰 Django + React Full Stack App

This project demonstrates a basic full stack application using **Django** for the backend and **React (Vite)** for the frontend.

---

## 🔧 Backend Setup (Django)

### 📦 Virtual Environment (macOS)
```bash
python3 -m venv env
source env/bin/activate
```

### 📥 Install Dependencies
```bash
pip install -r requirements.txt
```

### 📚 Python Package Descriptions
```
asgiref – ASGI utilities and reference implementation for async support  
Django – High-level Python web framework  
django-cors-headers – Handle Cross-Origin Resource Sharing  
djangorestframework – Web API toolkit for Django  
djangorestframework-simplejwt – JWT auth for DRF  
PyJWT – JSON Web Token support  
pytz – Timezone definitions  
sqlparse – SQL formatting and parsing  
psycopg2-binary – PostgreSQL adapter  
python-dotenv – Loads environment variables from .env
```

---

## 🚀 Start Django Project
```bash
django-admin startproject backend
cd backend
python manage.py startapp api
```

---

## ⚙️ Django Configuration

### settings.py changes

#### ➕ Add at the top:
```python
from datetime import timedelta
from dotenv import load_dotenv
import os

load_dotenv()
```

#### 🌐 Allow All Hosts:
```python
ALLOWED_HOSTS = ["*"]
```

#### 🔐 JWT & REST Framework:
```python
REST_FRAMEWORK = {
    "DEFAULT_AUTHENTICATION_CLASSES": (
        "rest_framework_simplejwt.authentication.JWTAuthentication",
    ),
    "DEFAULT_PERMISSION_CLASSES": [
        "rest_framework.permissions.IsAuthenticated",
    ],
}

SIMPLE_JWT = {
    "ACCESS_TOKEN_LIFETIME": timedelta(minutes=30),
    "REFRESH_TOKEN_LIFETIME": timedelta(days=1),
}
```

#### 🧩 Installed Apps:
```python
INSTALLED_APPS = [
    "api",
    "rest_framework",
    "corsheaders",
]
```

#### 🔄 CORS Settings:
```python
CORS_ALLOW_ALL_ORIGINS = True
CORS_ALLOWS_CREDENTIALS = True
```

---

## 🔄 Migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

---

## 🖥 Run Development Server
```bash
python manage.py runserver
```

---

## 🔐 User Authentication Flow

1. Register a user:  
   [http://127.0.0.1:8000/api/user/register/](http://127.0.0.1:8000/api/user/register/)

2. Get access/refresh tokens:  
   [http://127.0.0.1:8000/api/token/](http://127.0.0.1:8000/api/token/)

3. Refresh the access token:  
   [http://127.0.0.1:8000/api/token/refresh/](http://127.0.0.1:8000/api/token/refresh/)

---

## 📦 Move requirements.txt
Move the file inside the `backend/` directory.

---

## ⚛️ Frontend Setup (React + Vite)

### Create Vite App
```bash
npm create vite@latest frontend -- --template react
cd frontend
```

---

## 📌 TODO

- Add React routing & views
- Connect frontend to backend
- Handle auth tokens on frontend
- Add protected routes

---


---

## 🖥 Source Video and Code

1. Source:  
   [Django-React-Full-Stack-App](https://github.com/techwithtim/Django-React-Full-Stack-App)

2. Video Source:
    [https://www.youtube.com/watch?v=c-QsfbznSXI](https://www.youtube.com/watch?v=c-QsfbznSXI)

---

