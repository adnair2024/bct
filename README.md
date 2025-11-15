# 📘 **BCT — Better Content Tracker**

[![Made with Flask](https://img.shields.io/badge/Flask-2.0+-black?logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![Built with Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://www.python.org/)
[![Database: SQLite3](https://img.shields.io/badge/SQLite-3-lightgrey?logo=sqlite&logoColor=003B57)](https://sqlite.org/)
[![API: AniList](https://img.shields.io/badge/API-AniList-02A9FF?logo=data:image/png;base64,iVBORw0KGgo=)](https://anilist.co/)
[![API: MangaDex](https://img.shields.io/badge/API-MangaDex-F78C6C)](https://mangadex.org/)
[![API: Google Books](https://img.shields.io/badge/API-Google%20Books-4285F4?logo=google)](https://developers.google.com/books)

A minimal, dark-themed **personal media library** built with **Python, Flask, and SQLite3**.  
BCT lets you track **anime, manga, and books** in one unified interface, with metadata pulled from external APIs.

⭐ **One app for all your content.**  
🎨 **Minimal black & gray UI.**  
🗄️ **Local SQLite database.**  
🔍 **Search + Add via APIs.**  
📚 **Track progress, status, and favorites.**

---

## 🚀 Features

### **✔ Unified Library**
Track:
- Anime  
- Manga  
- Books  

### **✔ API-Powered Search**
Fetch metadata using:
- **AniList** (Anime)  
- **MangaDex** (Manga)  
- **Google Books** (Books)  

BCT automatically pulls:
- Cover art  
- Titles  
- Descriptions  
- Episode/chapter/page counts (when available)

### **✔ Local Progress Tracking**
Store personalized progress:
- Chapters read  
- Episodes watched  
- Pages read  

And organize each item by:
- **Status:** reading, completed, dropped, plan  
- **Favorites:** simple 1-click toggle

### **✔ Simple, Fast, Fully Local**
- No accounts  
- No third-party server  
- SQLite only  
- Full offline functionality after adding items

### **✔ Minimal Dark UI**
Based on:
- Deep black background  
- Soft gray panels  
- Clean white/gray text  
- No frontend frameworks required


---

## 🧩 Project Structure (Overview)

```
bct/
│
├── app.py # Main Flask app (routes, auth, library logic)
├── database.py # DB connection + initialization + migrations
├── models.py # CRUD helpers for users + media
│
├── api_clients/ # External API integration layer
│ ├── anilist.py # AniList API (anime)
│ ├── mangadex.py # MangaDex API (manga)
│ └── google_books.py # Google Books API (books)
│
├── auth/ # Authentication module
│ ├── init.py
│ ├── routes.py # /login, /register, /logout
│ └── utils.py # password hashing, login_required decorator
│
├── templates/ # Jinja2 template files
│ ├── base.html # shared layout (navbar, theme)
│ ├── login.html # user login form
│ ├── register.html # user registration form
│ ├── library.html # main library dashboard (per user)
│ ├── search.html # search media via APIs
│ ├── detail.html # item detail + progress/favorite/status
│ └── edit.html # edit item metadata
│
├── static/
│ ├── style.css # main CSS file
│ └── dark.css # color theme variables (black/gray look)
│
├── migrations/
│ ├── create_users.sql # schema for users table
│ └── update_media_user.sql # migration adding user_id to media table
│
├── library.db # SQLite database (ignored until created)
└── README.md # project documentation
```
