# IMDB API Clone With DRF

<h3>🔗 Final Project Links (Arranged According To Usage)</h3>
<br>

<b>1. Admin Access</b>
<ul>
    <li>Admin Section: http://127.0.0.1:8000/dashboard/</li>
</ul>
<br>

<b>2. Accounts</b>
<ul>
    <li>Registration: http://127.0.0.1:8000/api/account/register/</li>
    <li>Login: http://127.0.0.1:8000/api/account/login/</li>
    <li>Logout: http://127.0.0.1:8000/api/account/logout/</li>
</ul>
<br>

<b>3. Stream Platforms</b>
<ul>
    <li>Create Element & Access List: http://127.0.0.1:8000/api/watch/stream/</li>
    <li>Access, Update & Destroy Individual Element: http://127.0.0.1:8000/api/watch/stream/&lt;int:streamplatform_id&gt;/</li>
</ul>
<br>

<b>4. Watch List</b>
<ul>
    <li>Create & Access List: http://127.0.0.1:8000/api/watch/</li>
    <li>Access, Update & Destroy Individual Element: http://127.0.0.1:8000/api/watch/&lt;int:movie_id&gt;/</li>
</ul>
<br>

<b>5. Reviews</b>
<ul>
    <li>Create Review For Specific Movie: http://127.0.0.1:8000/api/watch/&lt;int:movie_id&gt;/reviews/create/</li>
    <li>List Of All Reviews For Specific Movie: http://127.0.0.1:8000/api/watch/&lt;int:movie_id&gt;/reviews/</li>
    <li>Access, Update & Destroy Individual Review: http://127.0.0.1:8000/api/watch/reviews/&lt;int:review_id&gt;/</li>
</ul>
<br>

<b>6. User Review</b>
<ul>
    <li>Access All Reviews For Specific User: http://127.0.0.1:8000/api/watch/user-reviews/?username=example</li>
</ul>
<br>

## ⚙️ Setup Instructions

1. Clone the repo
```
git clone https://github.com/yourusername/watchmate.git
```

2. Create virtual environment
```
python -m venv venv
```

3. Activate venv
```
Windows:   venv\Scripts\activate
Mac/Linux: source venv/bin/activate
```

4. Install requirements
```
pip install -r requirements.txt
```

5. Create `.env` file in root folder (same level as manage.py)
```
SECRET_KEY=your-secret-key-here
```

6. Run migrations
```
python manage.py migrate
```

7. Create superuser (for admin access)
```
python manage.py createsuperuser
```

8. Run server
```
python manage.py runserver
```

9. Visit: http://127.0.0.1:8000/dashboard/

---

## 🛠️ Tech Stack
- Python 3.11
- Django 3.2
- Django REST Framework 3.12
- SQLite (Development)
- Token Authentication

---

## 🔐 Authentication
- Token based authentication using DRF authtoken
- Register to get your token
- Pass token in every request header:
```
Authorization: Token <your-token-here>
```

---

## ✅ Features
- User registration, login and logout
- Stream platform management (Admin only)
- Watchlist management (Admin only)
- Review system with ratings (1-5)
- Duplicate review prevention
- Average rating calculation
- User specific review filtering
- Throttling to prevent API abuse
- Token based authentication