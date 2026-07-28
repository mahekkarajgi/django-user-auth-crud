# MyProject - Django Authentication & CRUD App

A simple Django application demonstrating user authentication (register, login, logout, profile) 
and CRUD operations, built with Django, SQLite, and Bootstrap 5.

## Project Structure

myproject/
├── manage.py
├── requirements.txt
├── myproject/
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
├── user/                  # Handles authentication & profile
│   ├── models.py
│   ├── forms.py
│   ├── urls.py
│   ├── views.py
├── myapp/                 # Handles CRUD operations
│   ├── models.py
│   ├── forms.py
│   ├── urls.py
│   ├── views.py
├── templates/
│   ├── base.html
│   ├── register.html
│   ├── login.html
│   ├── profile.html
│   ├── edit_profile.html
│   ├── create_update.html
│   ├── read.html

## Setup Instructions

1. Create a virtual environment and activate it:
   python -m venv venv
   source venv/bin/activate   (Linux/Mac)
   venv\Scripts\activate      (Windows)

2. Install dependencies:
   pip install -r requirements.txt

3. Create the Django project and apps (if starting from scratch):
   django-admin startproject myproject .
   python manage.py startapp user
   python manage.py startapp myapp

4. Copy the provided code into the respective files.

5. Create a `templates` folder at project root and add all template files.

6. Apply migrations:
   python manage.py makemigrations
   python manage.py migrate

7. Create a superuser (optional, for admin access):
   python manage.py createsuperuser

8. Run the development server:
   python manage.py runserver

9. Visit http://127.0.0.1:8000/register/ to create an account.

## Features

- User registration, login, logout
- User profile view and edit (bio, phone, address, profile picture)
- CRUD operations on "Item" model (Create, Read, Update, Delete)
- Items are scoped per logged-in user
- Bootstrap 5 styled UI with base.html template inheritance
- Django messages framework for user feedback

## Notes

- Uses SQLite (default Django DB) — no extra DB setup needed.
- Media files (profile pictures) are stored in the `media/` folder; ensure `MEDIA_URL`/`MEDIA_ROOT` are set in settings.py (included below).
- A Django signal automatically creates a `Profile` object whenever a `User` is created.
