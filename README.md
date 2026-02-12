Smart Shop — Unified Smartphone Platform

(Phone Finder, Sales Prediction, Comparison, Buy & Sell, Reviews, Upcoming Phones)

Smart Shop is a modular, web-based smartphone platform that combines multiple smartphone-related services into a single dashboard. Each feature runs as an independent Flask module, while a unified launcher connects them through a central homepage.

The project is designed as an academic and learning-focused system, demonstrating full-stack development, modular backend design, and practical Machine Learning integration.

Modules Included

Smart Shop consists of the following independently running modules:

Module	Description	Port
Phone Finder	Search and filter smartphones by specs	5000
Sales Prediction	ML-based smartphone sales forecasting	5001
Buy & Sell Used Phones	Local marketplace for used phones	5002
Compare Phones	Side-by-side phone comparison	5003
Upcoming Phones	View upcoming releases and timelines	5004
Reviews	Submit and browse user reviews	5005

The main dashboard (launcher) connects all modules from a single UI.

Buy & Sell Used Phones Module

This module implements a simple local marketplace for used smartphones.

Features

Post SELL listings with required details (name, contact, phone model, condition, price, city, state)

Post BUY requests (optional fields)

Search listings by text, city, state, type (buy/sell)

Contact seller via displayed phone number

Sellers can mark listings as SOLD

No authentication (demo purpose only)

Files (Buy & Sell Module)

app.py — Flask backend

GET /api/listings

POST /api/listings

POST /api/mark_sold

static/used.html — UI and forms

static/app.js — frontend logic

static/styles.css — UI styling

data/listings.json — demo data

System Architecture

Each feature runs as a separate Flask server

The main dashboard is a static launcher page

Clicking an icon opens the corresponding module in a new tab

Modules communicate only through URLs (loosely coupled design)

This structure keeps the system easy to understand, test, and extend.

Technology Stack
Frontend

HTML5

CSS3

JavaScript (ES6)

Backend

Python

Flask

Machine Learning (Sales Prediction)

Pandas

NumPy

Scikit-learn

Matplotlib / Seaborn

Data Storage

CSV files

JSON

SQLite (optional)

How to Run (Quick Method)
Step 1: Install dependencies
pip install flask pandas numpy

Step 2: Serve the main dashboard
python -m http.server --directory main 8000


Open in browser:

http://127.0.0.1:8000/

Step 3: Run modules (separately)

Each module must be running before clicking icons.

Example:

cd buy_sell
python app.py

Run All Modules Together (Recommended)
Option 1: Using provided scripts

Linux / macOS

./run_all.sh


Windows

run_all.bat


These scripts start all Flask modules automatically.

Unified Launcher Changes

The following updates were made to support the unified dashboard:

main/index.html

Added data-url attributes for each feature icon

main/script.js

Updated click handling to open module URLs in new tabs

Backup files preserved:

index.original.html

script.original.js

Added:

run_all.sh

run_all.bat

Module URLs
Feature	URL
Phone Finder	http://127.0.0.1:5000

Sales Prediction	http://127.0.0.1:5001

Buy & Sell	http://127.0.0.1:5002

Compare Phones	http://127.0.0.1:5003

Upcoming Phones	http://127.0.0.1:5004

Reviews	http://127.0.0.1:5005
Notes

If a port is already in use, change the port in that module’s app.py

Modules must be running before clicking icons in the dashboard

This design intentionally avoids tight coupling between services

Future Improvements

Merge all modules into a single Flask app (optional)

Add authentication and authorization

Replace JSON/CSV with PostgreSQL or MySQL

Add image uploads for listings

Add real-time APIs for prices and availability

Implement notifications (email/SMS)

Add pagination and map-based search

Project Status

Academic project built for learning and demonstration purposes.
Designed to be extendable into a production-ready system.

Author

Bhavina Parmar
B.Tech Computer Science and Engineering

GitHub: https://github.com/Bhavina-parmar

License

This project is intended for educational and non-commercial use.