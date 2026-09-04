# 🎬 Watchmate — IMDB API Clone

A production-ready REST API built with Django REST Framework, featuring token authentication, review system, throttling, Docker containerization, and CI/CD automation with GitHub Actions.

---

## 🛠️ Tech Stack

- **Python 3.11**
- **Django 3.2**
- **Django REST Framework 3.12**
- **DRF Token Authentication** — Token based authentication
- **SQLite** — Development database
- **Docker** — Containerization
- **GitHub Actions** — CI/CD pipeline

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
- Dockerized for easy deployment
- Automated CI/CD — tests run and image is pushed to Docker Hub on every push to main

---

## 🐳 Run with Docker (Quickest Way)

Make sure Docker is installed, then:

```bash
docker pull kulasekhar08/watchmate
```

Create a `.env` file:

```
SECRET_KEY=your-secret-key-here
```

Run the container:

```bash
docker run -p 8000:8000 --env-file .env kulasekhar08/watchmate
```

Visit: http://localhost:8000/api/watch/

---

## ⚙️ Local Setup (Without Docker)

1. Clone the repo

```bash
git clone https://github.com/kulasekharreddy-dev/watchmate-.git
```

2. Create and activate virtual environment

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Mac/Linux
source venv/bin/activate
```

3. Install dependencies

```bash
pip install -r requirements.txt
```

4. Create `.env` file in root folder (same level as manage.py)

```
SECRET_KEY=your-secret-key-here
```

5. Run migrations

```bash
python manage.py migrate
```

6. Create superuser (for admin access)

```bash
python manage.py createsuperuser
```

7. Run server

```bash
python manage.py runserver
```

Visit: http://127.0.0.1:8000/dashboard/

---

## 🔐 Authentication

Token based authentication using DRF authtoken.

Register to get your token, then pass it in every request header:

```
Authorization: Token <your-token-here>
```

---

## 🔗 API Endpoints

### Admin
| Endpoint | Description |
|----------|-------------|
| `/dashboard/` | Admin panel |

### Accounts
| Endpoint | Description |
|----------|-------------|
| `/api/account/register/` | Register new user |
| `/api/account/login/` | Login and get token |
| `/api/account/logout/` | Logout |

### Stream Platforms
| Endpoint | Description |
|----------|-------------|
| `/api/watch/stream/` | List all / Create (Admin only) |
| `/api/watch/stream/<id>/` | Retrieve, Update, Delete |

### Watchlist
| Endpoint | Description |
|----------|-------------|
| `/api/watch/` | List all / Create (Admin only) |
| `/api/watch/<id>/` | Retrieve, Update, Delete |

### Reviews
| Endpoint | Description |
|----------|-------------|
| `/api/watch/<id>/reviews/create/` | Create review for a movie |
| `/api/watch/<id>/reviews/` | All reviews for a movie |
| `/api/watch/reviews/<id>/` | Retrieve, Update, Delete review |
| `/api/watch/user-reviews/?username=example` | All reviews by a user |

---

## 🔄 CI/CD Pipeline

This project uses GitHub Actions for automated testing and deployment.

**On every push to main:**
1. Runs the full test suite on a fresh Ubuntu server
2. If all tests pass — builds the Docker image
3. Pushes the latest image to Docker Hub automatically

**Docker Hub:** https://hub.docker.com/r/kulasekhar08/watchmate
