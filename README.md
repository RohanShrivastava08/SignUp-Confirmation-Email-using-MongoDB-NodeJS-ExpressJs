# Signup with Email Confirmation Documentation

## Table of Contents
-  Overview
- Prerequisites
- Getting Started
- Clone the Repository
- Install Dependencies
- Set Up Environment Variables
- Running the Application
- Start MongoDB
- Start the Server
- Usage
- API Endpoints
- Signup
- Email Confirmation
- Example
- Troubleshooting
- Email Not Received
- Server Issues
- Conclusion
- Contact

## Overview
- This documentation provides step-by-step instructions for setting up a Node.js application that supports user signup with email confirmation.
- The application uses Express for the server, MongoDB for data storage, and Nodemailer for sending confirmation emails.

## Prerequisites
- Before you begin, ensure you have the following installed on your machine:

- Node.js: Download and install Node.js from nodejs.org.
- MongoDB: Install MongoDB and ensure it's running locally or on a server accessible from your Node.js application.

## Getting Started
- Clone the Repository
- Clone the project repository from GitHub or your version control system:

```sh
git clone <repository-url>
cd signup-email-confirmation
```

### Install Dependencies
- Install the necessary Node.js packages using npm:

```sh
npm install
```

### Set Up Environment Variables
- Create a .env file in the root directory of the project. 
- Add the following environment variables:

```sh
PORT=1400
MONGODB_URI=your_mongodb_connection_string
EMAIL_USER=your_email@example.com
EMAIL_PASS=your_email_password
```

- Replace your_mongodb_connection_string with your MongoDB connection string.
- Replace your_email@example.com with your email address and your_email_password with your email password.

## Running the Application
### Start MongoDB
- Ensure your MongoDB server is running:

```sh
mongod
```

### Start the Server
- Run the Node.js application:

```sh
node server.js
```

- You should see Server running on port 1400 logged to the console.

## Usage

### API Endpoints

#### Signup
- Endpoint: /api/signup
- Method: POST
- Request Body:
```json
{
    "name": "John Doe",
    "email": "john.doe@example.com",
    "password": "your_password"
}
```

- Response:
```json

{
    "message": "Registration successful! Please check your email for the confirmation link."
}
```

#### Email Confirmation
- Endpoint: /api/confirm/:confirmationCode
- Method: GET
- Response:

```json
{
    "message": "Email confirmed successfully"
}
```

### Example

#### Signup a User:

- Send a POST request to http://localhost:1400/api/signup with the JSON body as shown above using tools like Postman or cURL.

- Example using cURL:

```sh
curl -X POST http://localhost:1400/api/signup -H "Content-Type: application/json" -d '{"name": "John Doe", "email": "john.doe@example.com", "password": "your_password"}'
```

#### Confirm Email:

- After signing up, check your email inbox for a confirmation email.
- Click on the confirmation link provided in the email.

## Troubleshooting

### Email Not Received
- Check your spam/junk folder.
- Verify email settings and credentials in .env.
- Ensure email service provider settings allow sending from your application.

### Server Issues
- Ensure MongoDB is running.
- Check .env for typos or missing variables.

## Conclusion
- You have successfully set up a Node.js application for user signup with email confirmation using Nodemailer and MongoDB.
- For any further assistance or issues, feel free to contact us at your_contact_email@example.com.

## Contact
For support or inquiries, please contact:

- Email: rohansh0808@gmail.com

- GitHub: RohanShrivastava08
