Implement role-based authentication for user/admin login

This PR adds secure user authentication and role-based access control to the Mergington High School Activities API.

## Changes Made

### Backend (app.py)
- Added user authentication system with login/logout endpoints
- Implemented role-based access control (user vs admin roles)
- Protected signup endpoint to require user authentication
- Protected unregister endpoint to require admin role
- Added secure password hashing using passlib with PBKDF2
- Integrated session management with cookies using fastapi-login

### Frontend (index.html, app.js)
- Added login form in the header
- Display user info and role when logged in
- Hide signup form when not authenticated
- Show delete buttons only for admin users
- Updated signup to use authenticated user's email automatically
- Added logout functionality

### Dependencies
- Added fastapi-login and passlib to requirements.txt

## Security Features
- Password hashing with PBKDF2
- Session-based authentication with secure cookies
- Role-based permissions (admin vs user)
- Protected API endpoints

## Test Credentials
- Admin: admin@mergington.edu / adminpass
- User: student@mergington.edu / studentpass

## How to Test
1. Start the server: `uvicorn app:app --host 0.0.0.0 --port 8000`
2. Open the web app
3. Login with test credentials
4. Try signing up for activities (user role)
5. Try unregistering participants (admin role only)