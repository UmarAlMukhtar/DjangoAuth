# Django Authentication Project

A clean and modern Django authentication system with user registration, login, logout, and protected pages.

## 🚀 Features

- **User Registration**: New users can create accounts with username and password confirmation
- **User Login**: Secure authentication with error handling for invalid credentials
- **User Logout**: Safe logout with confirmation page
- **Protected Pages**: Access-controlled content for authenticated users only
- **Responsive Design**: Clean, minimal UI that works on all devices
- **Form Validation**: Password confirmation and error messaging

## 📁 Project Structure

```
authProject/
├── authProject/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── authApp/
│   ├── migrations/
│   ├── static/
│   │   └── styles/
│   │       └── styles.css
│   ├── templates/
│   │   ├── accounts/
│   │   │   ├── login.html
│   │   │   ├── logout.html
│   │   │   └── register.html
│   │   ├── auth1_app/
│   │   │   └── home.html
│   │   └── registration/
│   │       └── protected.html
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── form.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── db.sqlite3
├── manage.py
└── README.md
```

## 🛠️ Technologies Used

- **Django 5.2.4**: Web framework
- **Python**: Backend programming language
- **SQLite**: Database (default Django database)
- **HTML5**: Template structure
- **CSS3**: Modern styling with minimal design
- **JavaScript**: Not required for basic functionality

## ⚙️ Installation & Setup

### Prerequisites

- Python 3.8+
- pip (Python package manager)
- Virtual environment (recommended)

### 1. Clone or Download the Project

```bash
# If using git
git clone <repository-url>
cd authProject

# Or download and extract the ZIP file
```

### 2. Create Virtual Environment

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install django
# Or if you have a requirements.txt:
pip install -r requirements.txt
```

### 4. Database Setup

```bash
# Apply migrations
python manage.py makemigrations
python manage.py migrate

# Create superuser (optional)
python manage.py createsuperuser
```

### 5. Run the Development Server

```bash
python manage.py runserver
```

The application will be available at `http://127.0.0.1:8000/`

## 🎯 Usage

### User Registration

1. Navigate to `/accounts/register/`
2. Fill in username, password, and confirm password
3. Submit the form to create a new account
4. Automatically redirected to home page upon successful registration

### User Login

1. Navigate to `/accounts/login/` or click "Login" link
2. Enter your username and password
3. Submit the form to authenticate
4. Redirected to home page or originally requested page

### User Logout

1. Click "Logout" button on any authenticated page
2. Confirm logout on the confirmation page
3. Redirected to login page

### Protected Pages

- Access `/protected/` to view content only available to logged-in users
- Automatically redirected to login page if not authenticated

## 🗂️ URL Patterns

| URL                   | View            | Description                |
| --------------------- | --------------- | -------------------------- |
| `/`                   | `home_view`     | Home page (login required) |
| `/accounts/login/`    | `login_view`    | User login page            |
| `/accounts/logout/`   | `logout_view`   | User logout confirmation   |
| `/accounts/register/` | `register_view` | User registration page     |
| `/protected/`         | `ProtectedView` | Protected content page     |
| `/admin/`             | Django Admin    | Admin interface            |


## 🔧 Configuration

### Settings

Key settings in `settings.py`:

- `LOGIN_REDIRECT_URL = 'home'`: Redirect after login
- `STATICFILES_DIRS`: Static files configuration
- `INSTALLED_APPS`: Includes `authApp`

### Forms

Custom registration form in `form.py`:

- Username field
- Password field
- Password confirmation field
- Password matching validation

### Views

- **Function-based views**: Login, logout, register, home
- **Class-based view**: Protected page with login requirement
- **Authentication decorators**: `@login_required` for protected content


## 🚀 Deployment

For production deployment:

1. **Set DEBUG = False** in settings.py
2. **Configure allowed hosts** in `ALLOWED_HOSTS`
3. **Use environment variables** for secret keys
4. **Set up proper database** (PostgreSQL recommended)
5. **Configure static file serving**
6. **Set up HTTPS**

---

**Built with ❤️ using Django**
