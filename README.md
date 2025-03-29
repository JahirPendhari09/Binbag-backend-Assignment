
# User Profile Management API

# Overview

This is a RESTful API for user profile management with authentication. Users can register, log in, and manage their profiles securely. Authentication is implemented using JWT (JSON Web Token

## Tech Stack
- **Backend**: Express.js
- **Database**: MongoDB
- **Authentication**: JWT (JSON Web Token)

# How to Run <br/>
 

   Clone the repository:   ``` git clone https://github.com/JahirPendhari09/Binbag-backend-Assignment.git  ``` <br/>
   Install the dependencies:   ``` npm install ``` <br/>
   Start the development server:   ``` npm run serrver ``` <br/>
   Open your browser and visit:   ``` http://localhost:4500 ``` <br/>

 # Environment Variables
 
  Create a .env file in the root directory and configure it:

  ```
   PORT=5000
   MONGO_URI=mongodb://127.0.0.1:27017/userprofiledb
   JWT_SECRET=your_secret_key
  ```
   

   ## Features 
   
  - Register & Login
  - JWT Auth & Protected Routes
  - Profile Retrieval & Update
  - Error Handling


   # Endpoints

   <h3>User Registration</h3>
   
   Endpoint: POST <pre>{{baseurl}}/users/Register</pre>
   
   Request Body:
   
   ```
    {
      "name": "John Doe",
      "email": "john@example.com",
      "address": "123 Main St",
      "password": "password123",
      "bio": "Software Developer",
      "profilePicture": "https://example.com/profile.jpg"
    }
   ```
   
   Response:
   
   ```
    {
      "success": true,
      "data": {
        "_id": "user_id",
        "name": "John Doe",
        "email": "john@example.com"
      },
      "message": "User registered successfully"
    }
   ```

   <h3>User Login</h3>
   
   Endpoint: POST <pre>{{baseurl}}/users/login</pre>
   
   Request Body:
   
   ```
    {
      "email": "john@example.com",
      "password": "password123"
    }
   ```
   
   Response:
   
   ```
    {
      "success": true,
      "data": {
        "_id": "user_id",
        "name": "John Doe",
        "email": "john@example.com",
        "token": "jwt_token"
      },
      "message": "Login successful"
    }
   ```

   <h3>Get User Profile (Protected Route)</h3>
   
   Endpoint: GET <pre>{{baseurl}}/users/profile</pre>
   
   Headers:
   
   ```
    {
      "Authorization": "Bearer jwt_token"
    }
   ```
   
   Response:
   
   ```
    {
      "success": true,
      "data": {
         "_id": "user_id",
         "name": "John Doe",
         "email": "john@example.com",
         "address": "123 Main St",
         "bio": "Software Developer",
         "profilePicture": "https://example.com/profile.jpg"
      }
    }
   ```

   <h3>Update User Profile (Protected Route)</h3>
   
   Endpoint: PUT <pre>{{baseurl}}/users/profile</pre>
   
   Headers:
   
   ```
    {
      "Authorization": "Bearer jwt_token"
    }
   ```

   Request Body (Optional fields):

   ```
    {
      "name": "John Updated",
      "address": "456 Elm St",
      "bio": "Senior Developer",
      "profilePicture": "https://example.com/new-profile.jpg"
    }
   ```
   
   Response:
   
   ```
    {
      "success": true,
      "data": {
        "_id": "user_id",
        "name": "John Updated",
        "email": "john@example.com",
        "token": "new_jwt_token"
       },
       "message": "Profile updated successfully"
    }
   ```

   # Postman Documentation

   

 
   # Credits <br/>
   This project was developed by ```Jahir Pendhari```.

   <p>Feel free to explore and integrate these endpoints into your application.</p>
