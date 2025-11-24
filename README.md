# Flask E-Commerce Store

A full-stack e-commerce web application built with Flask.  
Customers can browse products, search, add items to the cart, and go through a checkout flow, while administrators manage inventory and orders through the admin interface.  
This fork modernizes the original UI with a unified dark theme and updated styling, keeping the backend logic and project structure intact. 

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Flask](https://img.shields.io/badge/Flask-2.x-lightgrey)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5-7952B3)
![Status](https://img.shields.io/badge/status-learning%20project-success)

---

## Overview

This project is a learning-oriented e-commerce platform implemented with the Flask microframework.  
It includes a complete customer flow (authentication, browsing, cart, checkout) and an administrative workflow for managing products and orders.  
In this customized version, the original bright layout has been redesigned into a modern, dark, Amazon-inspired interface using updated HTML templates and CSS (`base.html`, `home.html`, `forms.css`, `style.css`).

---

## Features

### Customer features

- User registration and login
- Password reset / recovery flow 
- Product browsing with image gallery and basic search
- Product detail view with current and previous price
- Shopping cart management (add / remove / update quantities)
- Checkout flow with payment integration hook (payment gateway ready)
- Order history listing for authenticated users

### Admin features

- Secure admin access (via Flask admin views or dedicated routes)
- Create, update and delete products
- Manage stock levels and availability
- View and update customer orders and order status 

### UI / UX enhancements in this fork

- Dark, gradient-based color scheme using deep navy and indigo backgrounds
- Accent colors in cyan, teal and soft green for key actions and highlights
- Redesigned navigation bar and footer to match the new palette
- Updated category sidebar and promotional blocks on the home page
- Modernized auth forms with soft shadows, rounded corners and focus states
- Hover animations for buttons, product cards and links for a more dynamic feel

---

## Tech Stack

- **Backend**: Flask (Python)
- **Frontend**: HTML5, CSS3, Bootstrap 5
- **Database**: SQLite (default) via SQLAlchemy
- **Authentication**: Flask-Login
- **Other**: WTForms / Flask-WTF for forms, Jinja2 templates
- **Optional**: Dockerfile for containerized deployment (build & run locally)

---

## Getting Started

### Prerequisites

- Python **3.8+**
- `pip` (Python package manager)
- (Optional) Docker, if you want to run the app in a container

### 1. Clone the repository

```bash
  git clone https://github.com/<your-username>/<your-repo-name>.git
  cd <your-repo-name>
```

### 2. Create and activate a virtual environment

On Windows:

```bash
  python -m venv venv
  venv\Scripts\activate
```
On macOS / Linux:
```bash
  python3 -m venv venv
  source venv/bin/activate
```
### 3. Install dependencies
```bash
  pip install -r requirements.txt
```

### 4. Configure environment variables

Create a .env file (or set environment variables in your shell) with values like:
```env
FLASK_APP=main.py
FLASK_ENV=development
SECRET_KEY=your-secret-key
DATABASE_URL=sqlite:///instance/ecommerce.db
```

Adjust names/paths according to how you run the app locally.

### 5. Initialize the database

If the application does not create the database automatically on first run, you can use a small helper script or Flask shell to create all tables. For example:
```bash
  flask shell
  >>> from website import db
  >>> db.create_all()
  >>> exit()
```

### 6. Run the development server

```bash
  flask run
```

By default the app will be available at:
```text
http://127.0.0.1:5000
```

### Project Structure

The overall structure follows the original Flask-Ecommerce project, with a clear separation between application logic and presentation. 
GitHub
```text
.
├── main.py               # Application entry point (Flask app factory / run script)
├── requirements.txt      # Python dependencies
├── Dockerfile            # Optional Docker build configuration
├── instance/             # Instance-specific config & SQLite database
├── media/                # Uploaded product images and static media
└── website/
    ├── __init__.py       # App factory, extensions and configuration
    ├── models.py         # SQLAlchemy models (User, Product, Order, etc.)
    ├── forms.py          # WTForms / Flask-WTF form definitions
    ├── routes.py         # Main application routes and views
    ├── static/
    │   ├── css/
    │   │   ├── forms.css   # Custom styles for login / signup / profile forms
    │   │   └── style.css   # Global styles and home page / product styling
    │   ├── js/
    │   │   └── myScript.js # Frontend scripts (carousel, interactions)
    │   └── images/         # UI images, hero banners, icons, etc.
    └── templates/
        ├── base.html       # Base layout, navbar, footer (dark theme)
        ├── home.html       # Home page with categories, banners, product grid
        ├── cart.html       # Shopping cart page
        ├── product.html    # Product details page
        ├── login.html      # Login form
        ├── register.html   # Registration form
        ├── profile.html    # User profile / orders
        └── ...             # Additional templates
```

### Screenshots

You can add your own screenshots here after running the project locally.
```text
./screenshots/
    home-original.png
    home-dark-theme.png
    cart-dark-theme.png
```

Example:

- home-original.png – reference UI from the tutorial / original project
- home-dark-theme.png – your customized dark-themed home page
- cart-dark-theme.png – shopping cart with updated styling

### License

This project inherits the MIT license from the original repository.
You are free to use, modify and distribute it under the terms of the MIT License.