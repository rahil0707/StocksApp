# StocksApp
This web application can monitor and share stock portfolios efficiently with friends. The app should include the ability to monitor investments in order to help investors decide the next steps.

# DevProjects - Favorite stocks watcher

This is an open source project from [DevProjects](http://www.codementor.io/projects). Feedback and questions are welcome!
Find the project requirements here: [Favorite stocks watcher](https://www.codementor.io/projects/web/favorite-stocks-watcher-b0wexig802)

## Tech/framework used
Built with Python, Django, React and PostgreSQL

## License
[MIT](https://choosealicense.com/licenses/mit/)

---

# Stock Portfolio Monitoring and Sharing Application

## Overview

This project aims to create an application for monitoring and sharing stock portfolios efficiently with friends. The app will help users track their investments and make informed decisions.

## Table of Contents

- [Project Overview](#project-overview)
- [Planning](#planning)
- [Analysis](#analysis)
- [Design](#design)
- [Development Environment Setup](#development-environment-setup)
- [Initial Setup](#initial-setup)

## Planning

### Objectives

- **User Authentication**: Enable users to create and log in to their accounts. Display user information upon login.
- **User Interface**: Develop a UI to input and display favorite stocks and their current prices.
- **Stock Monitoring**: Fetch and update stock prices every minute using an API service.
- **Stock Sharing**: Allow users to share stock lists with friends.

### Technology Stack

- **Front-end**: React.js
- **Back-end**: Django (Python)
- **Database**: PostgreSQL
- **API Service**: Finnhub (or similar)
- **Development Environment**: Visual Studio Code
- **Database Administration**: DBeaver

### Project Milestones

1. Setup Development Environment
2. Implement User Authentication
3. Design and Develop UI Components
4. Implement Stock Monitoring and Updating
5. Implement Stock Sharing Feature

## Analysis

### Functional Requirements

1. **User Authentication**
   - Register new users.
   - Authenticate existing users.
   - Display user details when logged in.

2. **Favorite Stocks Management**
   - Input favorite stocks by their symbol.
   - Store favorite stocks in the database.

3. **Stock Monitoring**
   - Fetch current stock prices using an API service.
   - Update stock prices every minute.

4. **Stock Sharing**
   - Enable users to share their stock lists with friends.

### Non-functional Requirements

1. **Performance**: The app should fetch and update stock prices without noticeable delay.
2. **Usability**: The UI should be intuitive and user-friendly.
3. **Scalability**: The system should handle an increasing number of users and stock data efficiently.
4. **Security**: User data and authentication should be secure.

## Design

### System Architecture

1. **Front-end (React.js)**:
   - **Components**:
     - Header: Display user info or login/register buttons.
     - Login: User login form.
     - Register: User registration form.
     - Dashboard: Display favorite stocks and their prices.
     - StockForm: Input form for adding favorite stocks.
   - **Services**:
     - API: Axios service for making HTTP requests to the back-end.

2. **Back-end (Django)**:
   - **Apps**:
     - Accounts: Handle user authentication.
     - Stocks: Manage stock data and interactions with the API.
   - **Database**:
     - PostgreSQL: Store user data and favorite stocks.
   - **API Endpoints**:
     - User registration and login.
     - CRUD operations for favorite stocks.
     - Fetching stock prices.

### Database Design

1. **User Table**:
   - id (Primary Key)
   - username
   - email
   - password (hashed)

2. **Stock Table**:
   - id (Primary Key)
   - user_id (Foreign Key to User Table)
   - stock_symbol
   - current_price

### User Interface Design

- **Header Component**: 
  - Display login/register buttons or user info (name, email, username) when logged in.
- **Dashboard**: 
  - Display list of favorite stocks and their current prices.
  - Menu to navigate to stock input form.
- **Stock Input Form**: 
  - Input field for stock symbol.
  - Button to add stock to the list.

## Development Environment Setup

### Front-end Setup (React)

```bash
npm create vite@latest frontend -- --template react
cd frontend
npm install axios react-router-dom jwt-decode
```

### Run Front-end (Django)

```bash
npm install
npm run dev
```

### Back-end Setup (Django)

```bash
python3 -m venv env
source/env/bin/activate
pip install -r requirements.txt
django-admin startproject backend
cd backend
python manage.py startapp api
```

### Back-end migrations (use these commands when there are any significant changes involving the data model) (Django)

```bash
python manage.py makemigrations
python manage.py migrate
```

### Run Back-end server (Django)

```bash
python manage.py runserver
```

### Database (PostgreSQL)

- Install PostgreSQL and set up a new database for the project.
- Configured Django to use PostgreSQL in `settings.py`.
- PostgreSQL managed by choreo.dev website

## Initial Setup

### Project Structure (Potential)

**Front-end**:

```
stock-portfolio-app/
├── public/
│   ├── index.html
├── src/
│   ├── components/
│   │   ├── Header.js
│   │   ├── Login.js
│   │   ├── Register.js
│   │   ├── Dashboard.js
│   │   ├── StockForm.js
│   ├── services/
│   │   ├── api.js
│   ├── App.js
│   ├── index.js
```

**Back-end**:

```
stock_portfolio_backend/
├── stock_portfolio_backend/
│   ├── settings.py
│   ├── urls.py
├── accounts/
│   ├── models.py
│   ├── views.py
│   ├── serializers.py
│   ├── urls.py
│   ├── tests.py
├── stocks/
│   ├── models.py
│   ├── views.py
│   ├── serializers.py
│   ├── urls.py
│   ├── tests.py
```

## Contributing

1. Fork repository.
2. Create a new branch using `git checkout -b feature-branch`.
3. Make your changes.
4. Add all changes using `git add .`.
5. Commit your changes using `git commit -m 'Add new feature'`.
6. Push to the branch `git push origin feature-branch`.
7. Create a new Pull Request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---
