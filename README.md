# Task 12 – Flask Login + Registration

**Repository Name:** 12-fsd-flask

This project implements a basic login and registration system using Flask, SQLite, SQLAlchemy, password hashing, and session-based authentication.

---

## Project Setup (Linux)

### 1) Navigate to the project folder
```bash
cd 12-fsd-flask
2) Create and activate virtual environment
bash
Copy code
python3 -m venv .venv
source .venv/bin/activate
3) Install dependencies
bash
Copy code
pip install -r requirements.txt
4) Run the application
bash
Copy code
python3 app.py
Open the browser and visit:

arduino
Copy code
http://127.0.0.1:5000/register
GET vs POST (Why POST for Credentials)
GET requests send data in the URL query string, which can expose sensitive information through browser history, server logs, or shared URLs.

POST requests send data in the request body, making it the correct and secure method for sending login and registration credentials.

Why Client-Side Validation Is Not Security
Client-side validation (HTML or JavaScript) can be bypassed easily by disabling JavaScript, modifying requests using tools like curl or Postman, or sending requests directly to the server.

Therefore, server-side validation is mandatory and is the real security control.

Password Hashing (Why It’s Required)
Storing plaintext passwords is dangerous because a database leak would expose all user passwords.

In this project:

Passwords are hashed using Werkzeug

Hashing is a one-way process

During login, the entered password is checked against the stored hash

Plaintext passwords are never stored in the database

What Is a Session (In This App)?
A session is used to remember that a user is logged in across multiple requests.

In this application:

After login, the user’s email is stored in the session

The /dashboard route checks if the session exists (protected route)

The /logout route clears the session to log the user out

Conclusion
This project demonstrates a secure authentication workflow using Flask with proper validation, password hashing, session handling, and protected routes.