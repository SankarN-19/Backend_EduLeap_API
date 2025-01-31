# EduLeap Backend

EduLeap is a backend API for an educational platform that enables user authentication, course management, and secure API interactions.

## Features
- User authentication (Register, Login, Profile Management)
- JWT-based security
- CRUD operations for courses
- RESTful API design
- Hosted on Vercel

## Tech Stack
- **Backend**: Node.js, Express.js
- **Database**: MongoDB (Mongoose ODM)
- **Authentication**: JSON Web Tokens (JWT)

## API Documentation

### User Endpoints
#### 1. Register a User
- **POST** `/api/users/register`
- **Request Body:**
  ```json
  {
    "username": "string",
    "email": "string",
    "password": "string"
  }
  ```
- **Response:**
  ```json
  {
    "message": "User registered successfully",
    "userId": "string"
  }
  ```

#### 2. User Login
- **POST** `/api/users/login`
- **Request Body:**
  ```json
  {
    "email": "string",
    "password": "string"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Login successful",
    "token": "string"
  }
  ```

#### 3. Get User Profile
- **GET** `/api/users/profile`
- **Headers:** `Authorization: Bearer <token>`
- **Response:**
  ```json
  {
    "userId": "string",
    "username": "string",
    "email": "string",
    "createdAt": "date-time"
  }
  ```

#### 4. Update User Profile
- **PUT** `/api/users/profile`
- **Headers:** `Authorization: Bearer <token>`
- **Request Body:**
  ```json
  {
    "username": "string",
    "email": "string"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Profile updated successfully"
  }
  ```

#### 5. Delete User Account
- **DELETE** `/api/users/profile`
- **Headers:** `Authorization: Bearer <token>`
- **Response:**
  ```json
  {
    "message": "User account deleted successfully"
  }
  ```

---

### Course Endpoints
#### 1. Create a Course
- **POST** `/api/courses`
- **Headers:** `Authorization: Bearer <token>`
- **Request Body:**
  ```json
  {
    "title": "string",
    "description": "string",
    "instructor": "string"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Course created successfully",
    "courseId": "string"
  }
  ```

#### 2. Get All Courses
- **GET** `/api/courses`
- **Response:**
  ```json
  [
    {
      "courseId": "string",
      "title": "string",
      "description": "string",
      "instructor": "string",
      "createdAt": "date-time"
    }
  ]
  ```

#### 3. Get Course by ID
- **GET** `/api/courses/:id`
- **Response:**
  ```json
  {
    "courseId": "string",
    "title": "string",
    "description": "string",
    "instructor": "string",
    "createdAt": "date-time"
  }
  ```

#### 4. Update Course
- **PUT** `/api/courses/:id`
- **Headers:** `Authorization: Bearer <token>`
- **Request Body:**
  ```json
  {
    "title": "string",
    "description": "string",
    "instructor": "string"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Course updated successfully"
  }
  ```

#### 5. Delete Course
- **DELETE** `/api/courses/:id`
- **Headers:** `Authorization: Bearer <token>`
- **Response:**
  ```json
  {
    "message": "Course deleted successfully"
  }
  ```

