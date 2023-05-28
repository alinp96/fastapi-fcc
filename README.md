# Project Name

The project is an API written in FASTAPI that provides various functionalities such as authentication, posts, user creation, and voting. It utilizes SQLAlchemy for interacting with the database and implements OAuth2 with bearer token for authentication. The project also supports Docker Compose for easy deployment. Additionally, Swagger UI is implemented, and it can be accessed at the "/docs" path.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Endpoints](#endpoints)
- [Authentication](#authentication)
- [Deployment with Docker Compose](#deployment-with-docker-compose)

## Introduction

The API is designed to provide a platform where users can interact by creating posts, voting on posts, and performing user-related actions. It offers a secure authentication mechanism using OAuth2 with bearer token and leverages SQLAlchemy for efficient and reliable database operations.

## Features

- User Registration: Users can create accounts by providing necessary information and credentials.
- Authentication: The API uses OAuth2 with bearer token for secure authentication and authorization of user actions.
- Post Manipulation: Authenticated users can create new posts, get all posts, get one post, delete own post or update own post by providing the required details.
- Voting System: Users can cast their votes on posts to express their preferences.
- User Management: The API provides endpoints to manage user accounts, including updating user information and retrieving user details.

## Installation

To set up the project locally, follow these steps:

1. Clone the repository:

    ```
    git clone https://github.com/alinp96/fastapi-fcc.git
    ```
2. Navigate to the project directory:
    ```
    cd fastapi-fcc
    ```
3. Create a virtual environment:
    ```
    py -3 -m venv venv
    ```
4. Activate the virtual environ
* For Windows
    ```
    venv\Scripts\activate.bat
    ```
* For Unix/macOs
    ```
    source venv/bin/activate
    ```
5. Install the required dependencies:
    ```
    pip install -r requirements.txt
    ```
6. Start the API server:
    ```
    uvicorn app.main:app
    ```
7. The API should now be accessible at http://localhost:8000. You can use an API testing tool like Postman or cURL to interact with the endpoints.

## Usage
To interact with the API, you need to authenticate and obtain a bearer token. Once you have the token, include it in the Authorization header of each request as follows:
> Authorization: Bearer [token]

Refer to the [Authentication](#authentication) section for more details on obtaining and using the bearer token.

Make requests to the various endpoints provided by the API to perform user-related actions, create posts, and cast votes.

## Endpoints
The following endpoints are available in the API:
* **POST /users/**: Create a new user account and obtain a bearer token by providing valid credentials.
* **GET /users/**: Optain information about a specific user.
* **GET /posts/**: Get all posts.
* **POST /posts/**: Create posts.
* **GET /posts/{id}**: Get a specific post.
* **PUT /posts/**: Update a specific post.
* **DELETE /posts/**: Delete a specific post.
* **POST /login/**: Login into account
* **POST /vote/**: Vote a specific post
* **GET /**: Root message.

Refer to the API documentation or consult the codebase for detailed information on request payloads, responses, and any additional endpoints. You can find the documentation on http://localhost:8000/docs or http://localhost:8000/redoc.

## Authentication
The API uses OAuth2 with bearer token for authentication. To obtain a bearer token, follow these steps:
1. Send a **POST** request to **/login/** endpoint with valid credentials.
2. If the credentials are correct, the server will respond with a bearer token.
3. Include the bearer token in the **Authorization** header of subsequent requests.

Example request:
```
POST /login
{
  "username": "example_user_or_email",
  "password": "password123"
}
```
Example response:
```
{
  "access_token": "your-bearer-token",
  "token_type": "bearer"
}
```
## Deployment with Docker Compose
To deploy the application using Docker Compose, make sure Docker and Docker Compose are installed on your system, and then follow these steps:
1. Clone the repository:
```
git clone https://github.com/alinp96/fastapi-fcc.git
```
2. Navigate to the project directory:
```
cd fastapi-fcc
```
3. Customize the Docker Compose configuration if needed.

4. Build and start the Docker containers:
```
docker-compose up -d
```
The API should now be running and accessible. You can use the configured port to access the API, e.g., http://localhost:8000.


### Enjoy