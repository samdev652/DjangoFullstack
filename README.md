# 📝 Django Fullstack Notes Application

A modern fullstack web application for creating and managing personal notes, built with Django REST Framework and React. 

![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)

## ✨ Features

- 🔐 **Secure Authentication** - JWT-based authentication with access and refresh tokens
- 📝 **CRUD Operations** - Create, read, and delete notes seamlessly
- 🛡️ **Protected Routes** - Secure routes with automatic token refresh
- ⚡ **Modern Frontend** - Built with React 19 and Vite for lightning-fast development
- 🎨 **Responsive Design** - Clean and intuitive user interface
- 🔄 **Real-time Updates** - Dynamic note management without page reloads

## 🏗️ Architecture

### Backend (Django REST Framework)
- RESTful API endpoints for notes management
- JWT authentication using Django REST Framework SimpleJWT
- User registration and login system
- SQLite database (easily configurable for PostgreSQL/MySQL)

### Frontend (React + Vite)
- Modern React 19 with hooks
- React Router v7 for navigation
- Axios for API communication
- JWT token management with automatic refresh
- Protected route components
- Loading indicators and error handling

## 🛠️ Tech Stack

### Backend
- **Django** - Python web framework
- **Django REST Framework** - API toolkit
- **SQLite** - Database (default)

### Frontend
- **React 19.1** - UI library
- **Vite 7. 1** - Build tool and dev server
- **React Router 7.8** - Client-side routing
- **Axios 1.11** - HTTP client
- **jwt-decode 4.0** - JWT token decoder

## 📦 Installation

### Prerequisites
- Python 3.8+
- Node.js 16+
- npm or yarn

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/samdev652/DjangoFullstack.git
   cd DjangoFullstack
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   cd backend
   pip install -r requirements.txt
   ```

4. **Run migrations**
   ```bash
   python manage.py migrate
   ```

5. **Create superuser (optional)**
   ```bash
   python manage.py createsuperuser
   ```

6. **Start the Django server**
   ```bash
   python manage.py runserver
   ```

   The API will be available at `http://127.0.0.1:8000`

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure environment variables**
   
   Create a `.env` file in the `frontend` directory:
   ```env
   VITE_API_URL="http://127.0.0.1:8000"
   ```

4. **Start the development server**
   ```bash
   npm run dev
   ```

   The app will be available at `http://localhost:5173`

## 🚀 Usage

1. **Register** - Create a new account at `/register`
2. **Login** - Sign in with your credentials at `/login`
3. **Create Notes** - Add new notes with title and content
4. **View Notes** - See all your notes on the home page
5. **Delete Notes** - Remove notes you no longer need
6. **Logout** - Securely logout at `/logout`

## 📁 Project Structure

```
DjangoFullstack/
├── backend/                 # Django REST API
│   ├── api/                # API app
│   ├── backend/            # Django project settings
│   ├── manage.py
│   └── requirements.txt
│
└── frontend/               # React application
    ├── src/
    │   ├── components/     # Reusable components
    │   │   ├── Form.jsx
    │   │   ├── Note.jsx
    │   │   ├── ProtectedRoute.jsx
    │   │   └── LoadingIndicator.jsx
    │   ├── pages/          # Page components
    │   │   ├── Home.jsx
    │   │   ├── Login.jsx
    │   │   ├── Register.jsx
    │   │   └── NotFound.jsx
    │   ├── styles/         # CSS files
    │   ├── api. js          # Axios configuration
    │   ├── constants.js    # App constants
    │   ├── App.jsx         # Main app component
    │   └── main.jsx        # Entry point
    ├── package.json
    └── vite.config. js
```

## 🔒 API Endpoints

### Authentication
- `POST /api/user/register/` - Register new user
- `POST /api/token/` - Login and get JWT tokens
- `POST /api/token/refresh/` - Refresh access token

### Notes
- `GET /api/notes/` - Get all notes for authenticated user
- `POST /api/notes/` - Create a new note
- `DELETE /api/notes/delete/{id}/` - Delete a note

## 🎨 Key Components

### ProtectedRoute
Wraps protected pages and ensures users are authenticated.  Automatically refreshes expired JWT tokens.

### Form
Reusable authentication form component used for both login and registration.

### Note
Displays individual note with title, content, created date, and delete functionality.

## 🔧 Configuration

### Environment Variables

**Frontend (. env)**
```env
VITE_API_URL="http://127.0.0.1:8000"
```

### Token Management
- Access tokens are stored in localStorage
- Automatic token refresh on expiration
- Secure Bearer token authentication

## 🧪 Development

### Frontend Development
```bash
npm run dev      # Start dev server
npm run build    # Build for production
npm run preview  # Preview production build
npm run lint     # Run ESLint
```

### Backend Development
```bash
python manage.py runserver    # Start Django server
python manage. py makemigrations  # Create migrations
python manage.py migrate      # Apply migrations
python manage.py test         # Run tests
```

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 👤 Author

**samdev652**
- GitHub: [@samdev652](https://github.com/samdev652)

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/samdev652/DjangoFullstack/issues).

## ⭐ Show your support

Give a ⭐️ if this project helped you! 

---

**Note**:  This is a development setup. For production deployment, ensure you:
- Use environment variables for sensitive data
- Configure CORS properly
- Use a production-ready database (PostgreSQL/MySQL)
- Enable HTTPS
- Set DEBUG=False in Django settings
- Use a production-ready server (Gunicorn/uWSGI)
