# Django E-Commerce Platform
https://img.shields.io/badge/Django-3.2-green
https://img.shields.io/badge/Python-3.8+-blue

A modular e-commerce platform built with Django, featuring product catalog, user management, and review system.

## Overview

This Django-powered e-commerce backend provides scalable and modular functionality for managing an online store. It supports dynamic product listings, category-based navigation, user-generated reviews, and an extensible admin interface suitable for real-world applications.

## Features

### Core Functionality
- Product catalog management
- Category organization
- User review system
- Admin dashboard with advanced controls

### Admin Interface Highlights
- **Category Management**:
  - Create/edit categories with automatic slug generation
  - View product counts per category
  - Inline product management
- **Product Management**:
  - Comprehensive product editing
  - Pricing and inventory control
  - Image uploads
- **Review System**:
  - Review moderation
  - User rating management
  - Comment previews

  ### 🔐 Authentication & User Management (Accounts App)
- Custom `User` model with email-based login
- JWT authentication using `djangorestframework-simplejwt`
- User registration via API
- Secure password hashing
- Optional fields: profile photo, date of birth, created_by

### 📦 Product Management (Products App)
- Product model with:
  - Title
  - Description
  - Price
  - Inventory
  - Slug (for SEO-friendly URLs)
- Auto slug generation based on product title
- Product listing & detail views via API
- Admin support for CRUD

---
## 🛠️ Tech Stack

- **Backend:** Django & Django REST Framework
- **Authentication:** JWT via `simplejwt`
- **Database:** SQLite (default) / PostgreSQL-ready
- **Language:** Python 3.11+
- **Environment Management:** `venv`

---

## 🧪 API Endpoints (WIP)

### Authentication
- `POST /api/auth/register/` – Register a new user
- `POST /api/auth/register/` – Register a new user
- `POST /api/token/` – Get access + refresh tokens
- `POST /api/token/refresh/` – Refresh access token

### Products
- `GET /api/products/` – List all products
- `GET /api/products/<slug>/` – Retrieve product detail

---

## Installation
### Prerequisites
- Python 3.8+
- PostgreSQL 12+
- pip 20+

### Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/project-nexus.git
   cd project-nexus
   ```

 2. **Set up virtual environment**:
 ```
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```

3. **Install dependencies**:
```
pip install -r requirements.txt
```

4. **Database setup**
```
python manage.py migrate
python manage.py createsuperuser
```

5. **Run development server**:
```
python manage.py runserver
```

---
### Configuration
1. **Environment variables**:
Create a `.env` file with:
```
    SECRET_KEY=your-secret-key-here
    DEBUG=True
    DB_NAME=djangocommerce
    DB_USER=postgres
    DB_PASSWORD=yourpassword
    DB_HOST=localhost
    DB_PORT=5432
```

2. **Media files**:
Add to settings.py:
- MEDIA_URL = '/media/'
- MEDIA_ROOT = os.path.join(BASE_DIR, 'media/')

## Admin Guide

### Accessing the Admin
- URL: `/admin/`  
- Use superuser credentials created during installation  

3. ### Key Admin Features

#### Categories
**Adding Categories**:
1. Navigate to Products → Categories  
2. Click "Add Category"  
3. Fill in name and description  
4. Slug auto-generates from name  
5. Save to create  

**Inline Products**:
- Add products directly when creating categories  
- Incomplete products are automatically filtered  

#### Products
**Product Fields**:

- Required: Name, Category, Price, Stock

- Optional: Description, Image

- Automatic: Created/Updated timestamps

#### Reviews
**Moderation**:

- Filter by rating

- Search by product or user

- View comment previews

#### Development Notes
**Models Overview**
- Category: Product grouping with slug URLs

- Product: Core item with pricing/inventory

- Review: User feedback system

**Custom Admin Features**
- Product count per category

- Description/comment previews

- Smart form validation

- Organized field sets

#### Troubleshooting
**Common Issues**:

1. **Missing database columns**:
```
python manage.py makemigrations
python manage.py migrate
```

2. **Admin validation errors**:

- Ensure all required fields are complete

- Check model definitions match database

3. **Image uploads not working**:

- Verify MEDIA settings

- Check directory permissions