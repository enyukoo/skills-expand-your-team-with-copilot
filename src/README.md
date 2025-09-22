# Mergington High School Activities

A comprehensive web application that allows teachers to manage student registrations for extracurricular activities at Mergington High School. The system provides an intuitive interface for viewing activities, managing student enrollments, and filtering activities by various criteria.

## Features

### For Students & Public Viewing
- View all available extracurricular activities with detailed information
- Browse activities by category (Sports, Arts, Academic, Community, Technology)
- Filter activities by day of week and time slots
- Search activities by name or description
- View activity schedules, participant counts, and available spots

### For Teachers (Authentication Required)
- Secure login system for teacher accounts
- Register students for activities using student email addresses
- Unregister students from activities when needed
- Access to all activity management functions
- Session management with persistent login

### Activity Management
- **Comprehensive Activity Catalog**: Over 13 different activities including:
  - Weekday activities (Chess Club, Programming Class, Soccer Team, etc.)
  - Weekend activities (Robotics Workshop, Science Olympiad, Chess Tournament)
  - Morning and afternoon time slots
  - Various categories: Sports, Arts, Academic, Community, Technology

### User Interface Features
- **Advanced Filtering System**:
  - Category filters (All, Sports, Arts, Academic, Community, Technology)
  - Day filters (Monday through Sunday, including weekends)
  - Time range filters (Morning, Afternoon, Weekend)
- **Search functionality** with real-time activity filtering
- **Responsive design** that works on desktop and mobile devices
- **Modal dialogs** for registration and login processes
- **Interactive authentication system** with login/logout functionality

### Technical Features
- **MongoDB Database Integration**: Persistent data storage (not in-memory)
- **FastAPI Backend**: RESTful API with automatic documentation
- **Password Security**: Argon2 password hashing for teacher accounts
- **Session Management**: Client-side session persistence
- **Real-time Updates**: Activity participant counts update dynamically

## Technology Stack

- **Frontend**: HTML5, CSS3, JavaScript (Vanilla)
- **Backend**: Python FastAPI framework
- **Database**: MongoDB with PyMongo driver
- **Security**: Argon2 password hashing
- **Server**: Uvicorn ASGI server

## API Endpoints

| Method | Endpoint | Description | Authentication |
|--------|----------|-------------|----------------|
| GET | `/activities` | Get all activities with filtering options | Public |
| GET | `/activities/days` | Get list of available activity days | Public |
| POST | `/activities/{activity_name}/signup` | Register a student for an activity | Teacher Required |
| POST | `/activities/{activity_name}/unregister` | Remove a student from an activity | Teacher Required |
| POST | `/auth/login` | Authenticate teacher login | None |
| GET | `/auth/check-session` | Validate teacher session | None |

## Sample Teacher Accounts

The system comes with pre-configured teacher accounts for testing:

- **Username**: `mrodriguez` | **Password**: `art123` | **Role**: Art Teacher  
- **Username**: `mchen` | **Password**: `chess456` | **Role**: Chess Teacher
- **Username**: `principal` | **Password**: `admin789` | **Role**: Principal

## Data Persistence

> [!IMPORTANT]
> Unlike earlier versions, this application now uses **MongoDB for persistent data storage**. All activity registrations, teacher accounts, and system data persist between server restarts.

## Development Guide

For detailed setup and development instructions, please refer to our [Development Guide](../docs/how-to-develop.md).
