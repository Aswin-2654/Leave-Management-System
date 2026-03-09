# Leave Management System

A comprehensive leave management application with role-based access control, built with FastAPI (backend) and React + TypeScript (frontend).

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [Testing](#testing)
- [API Documentation](#api-documentation)
- [User Roles](#user-roles)

## ✨ Features

- **Role-Based Access Control**: Admin, Manager, and Employee roles with specific permissions
- **Leave Management**: Submit, approve, and track leave requests
- **Authentication**: Secure user authentication with token-based authorization
- **Dashboard**: User-specific dashboards for different roles
- **Leave Tracking**: View leave history and balance
- **Admin Panel**: User and leave management capabilities
- **Manager Controls**: Approve/reject leave requests, view team information
- **Employee Portal**: Submit leave requests and track personal leave

## 🛠 Tech Stack

### Backend
- **Framework**: FastAPI
- **Database**: SQLAlchemy (ORM)
- **Authentication**: JWT tokens
- **Testing**: pytest
- **Python Version**: 3.9+

### Frontend
- **Framework**: React 18+
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **Build Tool**: Vite
- **HTTP Client**: Axios
- **State Management**: Zustand (via authStore)

## 📁 Project Structure

```
Leave-Management-System/
├── Backend/
│   ├── auth.py                 # Authentication logic
│   ├── database.py             # Database configuration
│   ├── main.py                 # FastAPI application entry point
│   ├── models.py               # Database models
│   ├── schemas.py              # Pydantic schemas
│   ├── routers/                # API route handlers
│   │   ├── admin_routes.py
│   │   ├── auth_routes.py
│   │   ├── employee_routes.py
│   │   └── manager_routes.py
│   └── tests/                  # Test suite
│       ├── test_admin.py
│       ├── test_auth.py
│       ├── test_employee.py
│       ├── test_manager.py
│       └── test_roles.py
│
├── Frontend/
│   ├── src/
│   │   ├── components/         # React components
│   │   ├── pages/              # Page components
│   │   │   ├── admin/
│   │   │   ├── manager/
│   │   │   └── employee/
│   │   ├── auth/               # Authentication components & store
│   │   ├── api/                # API client configuration
│   │   ├── types/              # TypeScript types
│   │   ├── App.tsx             # Root component
│   │   └── main.tsx            # Entry point
│   ├── public/                 # Static assets
│   ├── vite.config.ts          # Vite configuration
│   ├── tailwind.config.js      # Tailwind CSS configuration
│   ├── tsconfig.json           # TypeScript configuration
│   └── package.json            # Dependencies
│
└── README.md                   # This file
```

## 📦 Prerequisites

- Python 3.9 or higher
- Node.js 16.x or higher
- npm or yarn package manager
- Git

## 🚀 Installation

### Backend Setup

1. **Navigate to Backend directory**:
   ```bash
   cd Backend
   ```

2. **Create a virtual environment**:
   ```bash
   python -m venv venv
   ```

3. **Activate the virtual environment**:
   - On Windows:
     ```bash
     venv\Scripts\activate
     ```
   - On macOS/Linux:
     ```bash
     source venv/bin/activate
     ```

4. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

### Frontend Setup

1. **Navigate to Frontend directory**:
   ```bash
   cd Frontend
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

## ▶️ Running the Application

### Backend

1. **From the Backend directory** (with virtual environment activated):
   ```bash
   uvicorn main:app --reload
   ```
   The API will be available at `http://localhost:8000`

2. **Access API documentation**:
   - Swagger UI: `http://localhost:8000/docs`
   - ReDoc: `http://localhost:8000/redoc`

### Frontend

1. **From the Frontend directory**:
   ```bash
   npm run dev
   ```
   The application will be available at `http://localhost:5173` (default Vite port)

### Running Both Concurrently

From the root directory, run both servers in separate terminals or use a process manager like `concurrently`:

```bash
npm install -g concurrently
concurrently "cd Backend && uvicorn main:app --reload" "cd Frontend && npm run dev"
```

## 🧪 Testing

### Backend Tests

Run tests from the Backend directory:

```bash
# Run all tests
pytest

# Run with verbose output
pytest -v

# Run specific test file
pytest tests/test_auth.py

# Run with coverage
pytest --cov=.
```

**Test Files**:
- `test_auth.py` - Authentication endpoints
- `test_admin.py` - Admin functionality
- `test_manager.py` - Manager functionality
- `test_employee.py` - Employee functionality
- `test_roles.py` - Role-based access control

### Frontend Tests

```bash
# Run frontend tests (when configured)
npm run test
```

## 📚 API Documentation

The API documentation is automatically generated and available at:
- **Swagger UI**: `http://localhost:8000/docs`
- **ReDoc**: `http://localhost:8000/redoc`

### Key Endpoints

#### Authentication
- `POST /auth/login` - User login
- `POST /auth/register` - User registration
- `POST /auth/logout` - User logout

#### Admin Routes
- `GET /admin/users` - List all users
- `DELETE /admin/users/{user_id}` - Delete user

#### Manager Routes
- `GET /manager/leaves` - View leave requests
- `PUT /manager/leaves/{leave_id}` - Approve/reject leave

#### Employee Routes
- `POST /employee/leaves` - Submit leave request
- `GET /employee/leaves` - View personal leave history

## 👥 User Roles

The system supports three main roles:

1. **Admin**
   - Full system access
   - User management
   - Leave policy configuration
   - View all leave requests

2. **Manager**
   - Approve/reject employee leave requests
   - View team information
   - Generate reports

3. **Employee**
   - Submit leave requests
   - View personal leave balance and history
   - Track request status

## 🤝 Contributing

1. Create a feature branch (`git checkout -b feature/AmazingFeature`)
2. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
3. Push to the branch (`git push origin feature/AmazingFeature`)
4. Open a Pull Request


## 📞 Support

For issues or questions, please create an issue in the repository or contact the development team.