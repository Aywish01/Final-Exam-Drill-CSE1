# Project Title: Electives Final Project

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Authentication](#authentication)
- [Testing](#testing)
- [Additional Information](#additional-information)

## Installation

To install and set up the project, follow these steps:

1. Clone the repository:

    ```bash
    git clone https://github.com/Aywish01/Final-Exam-Drill-CSE1.git
    cd your-repository
    ```

2. Create a virtual environment:

    ```bash
    python -m venv venv
    source venv/bin/activate  # For Windows: .\venv\Scripts\activate
    ```

3. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

4. Set up the database:

    - Ensure MySQL server is installed and running.
    - Create a database and import the SQL dump provided in the `db_dump` directory.

5. Configure environment variables:

    Create a `.env` file in the project root and set the following variables:

    ```env
    FLASK_APP=your_flask_app.py
    FLASK_ENV=development
    JWT_SECRET_KEY=your_jwt_secret_key
    DATABASE_URL=mysql+mysqlconnector://username:password@localhost:3306/database_name
    ```

    Replace `your_jwt_secret_key`, `username`, `password`, and `database_name` with your actual values.

6. Run the application:

    ```bash
    flask run
    ```

## Usage

To use the application, follow the steps below:

1. Describe how to use your application, including any specific steps or details users need to know.

## API Endpoints

The application provides the following API endpoints:

### GET /users

- Description: Get a list of all users.
- Parameters: None.
- Response:
  - JSON format: `{ "users": [...] }`
  - XML format: `<users><user>...</user></users>`

### GET /users/<user_id>

- Description: Get details of a specific user.
- Parameters: `format` (optional, default is JSON).
- Response:
  - JSON format: `{ "user": {...} }`
  - XML format: `<user>...</user>`

### POST /users

- Description: Create a new user.
- Parameters: User data in the request body.
- Response: `{ "message": "User created successfully" }`

### PUT /users/<user_id>

- Description: Update details of a specific user.
- Parameters: User data in the request body.
- Response: `{ "message": "User updated successfully" }`

### DELETE /users/<user_id>

- Description: Delete a specific user.
- Parameters: None.
- Response: `{ "message": "User deleted successfully" }`

## Authentication

To access protected routes, you need to obtain a JWT token by making a POST request to `/login`. Use the obtained token in the `Authorization` header for requests to protected routes.

Example:
   ```http
   POST /login
   Content-Type: application/json

   {
     "username": "your_username",
     "password": "your_password"
   }
