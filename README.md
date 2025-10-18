# MyBlogApp

> A simple, elegant, and responsive blog platform built with Django

![Django](https://img.shields.io/badge/Django-5.2.7-darkgreen?style=flat-square&logo=django)
![Python](https://img.shields.io/badge/Python-3-blue?style=flat-square&logo=python)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square)

## Overview

**MyBlogApp** is a lightweight, feature-rich blogging platform built with Django. Inspired by the Django Girls tutorial, it provides an intuitive interface for creating, managing, and sharing blog posts. Whether you're a beginner learning Django or looking for a minimalist blogging solution, MyBlogApp is the perfect starting point.

## Features

✨ **Core Features:**
- 📝 **Create & Manage Posts** - Easily create, edit, and publish blog posts
- 📅 **Publication Control** - Draft and schedule posts with precise publication dates
- 👤 **User Attribution** - Posts are linked to their authors via Django's User model
- 🎨 **Responsive Design** - Beautiful, mobile-friendly interface built with Bootstrap 5
- ⚡ **Fast & Lightweight** - Minimal dependencies, optimized for performance
- 🔐 **Admin Panel** - Powerful Django Admin interface for content management

## Tech Stack

| Technology | Purpose |
|-----------|---------|
| **Django 5.2.7** | Backend web framework |
| **Python 3** | Programming language |
| **SQLite3** | Database |
| **Bootstrap 5.3.3** | CSS framework & responsive design |
| **HTML5 Templates** | Template rendering |

## Quick Start

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)
- Virtual environment (recommended)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/DRAGOON21S/myblogapp.git
   cd myblogapp
   ```

2. **Create and activate virtual environment**
   ```bash
   # Windows
   python -m venv venv
   venv\Scripts\activate

   # macOS/Linux
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run migrations**
   ```bash
   python manage.py migrate
   ```

5. **Create superuser (admin account)**
   ```bash
   python manage.py createsuperuser
   ```

6. **Start the development server**
   ```bash
   python manage.py runserver
   ```

7. **Access the application**
   - Blog: http://localhost:8000
   - Admin Panel: http://localhost:8000/admin

## Usage

### Creating a Blog Post

1. Navigate to the admin panel at `/admin`
2. Log in with your superuser credentials
3. Click "Posts" → "Add Post"
4. Fill in the title and content
5. Set the publication date
6. Save the post

### Publishing a Post

Posts are automatically published when their `published_date` is before the current time. You can:
- **Schedule posts** by setting a future publication date
- **Draft posts** by leaving the published_date empty initially
- **View all published posts** on the homepage, ordered by newest first

## Project Structure

```
myblogapp/
├── README.md                 # Project documentation
├── manage.py                 # Django CLI
├── requirements.txt          # Python dependencies
├── db.sqlite3               # SQLite database
│
├── mysite/                  # Django project configuration
│   ├── settings.py         # Project settings & configuration
│   ├── urls.py             # URL routing
│   ├── asgi.py             # ASGI configuration
│   └── wsgi.py             # WSGI configuration
│
└── blog/                    # Main blog application
    ├── models.py           # Post model definition
    ├── views.py            # View logic (post_list, post_detail)
    ├── urls.py             # Blog URL patterns
    ├── forms.py            # Post form for creating/editing
    ├── admin.py            # Admin interface configuration
    ├── apps.py             # App configuration
    │
    ├── migrations/         # Database migrations
    │   └── 0001_initial.py # Initial schema
    │
    ├── templates/blog/     # HTML templates
    │   ├── base.html       # Base template with navigation
    │   ├── post_list.html  # Homepage (all posts)
    │   └── post_detail.html # Individual post view
    │
    └── static/css/         # Static assets
        └── blog.css        # Custom styling
```

## Configuration

### Settings (mysite/settings.py)

- **DEBUG**: Set to `False` in production
- **ALLOWED_HOSTS**: Update with your domain in production
- **TIME_ZONE**: Set to `Asia/Kolkata` (customize as needed)
- **DATABASES**: Using SQLite (update for production)

### Environment Setup

For production deployment, consider:
- Using environment variables for sensitive settings
- Setting `DEBUG=False`
- Using a production database (PostgreSQL recommended)
- Configuring proper ALLOWED_HOSTS
- Setting up HTTPS/SSL certificates

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | Homepage - displays all published posts |
| `/post/<id>/` | GET | View individual post details |
| `/admin/` | GET | Django admin panel |

## Dependencies

```
Django==5.2.7
asgiref==3.10.0
sqlparse==0.5.3
tzdata==2025.2
requests==2.32.5
```

See `requirements.txt` for complete list with versions.

## Contributing

Contributions are welcome! Here's how to get started:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Learning Resources

- 📚 [Django Official Documentation](https://docs.djangoproject.com/)
- 📖 [Django Girls Tutorial](https://tutorial.djangogirls.org/)
- 🎓 [Django for Beginners](https://djangoforbeginners.com/)
- 🚀 [Full Stack Python - Django](https://www.fullstackpython.com/django.html)

## Roadmap

- [ ] User authentication & registration
- [ ] Comments on posts
- [ ] Search functionality
- [ ] Tags & categories
- [ ] Email notifications
- [ ] API endpoints (Django REST Framework)
- [ ] Dark mode toggle
- [ ] Social media sharing

## Troubleshooting

### Database errors
```bash
# Reset database (WARNING: deletes all data)
python manage.py migrate zero blog
python manage.py migrate
```

### Static files not loading
```bash
python manage.py collectstatic
```

### Port already in use
```bash
python manage.py runserver 8001
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Created by [Dragoon21S](https://github.com/DRAGOON21S)

## Support

If you have any questions or need help, feel free to:
- Open an issue on GitHub
- Check the Django documentation
- Visit the Django Girls tutorial

---

**Happy blogging!** ✍️

*Made with ❤️ by Django enthusiasts*
