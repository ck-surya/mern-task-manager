
# MERN Task Manager

A full-stack task management application built using MongoDB, Express, React, and Node.js (MERN).

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [Environment Variables](#environment-variables)
- [Project Structure](#project-structure)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)

## Features

- Create, edit, delete, and view tasks
- Set task status and priorities
- Assign tasks to multiple assignees

## Installation

### Prerequisites

- Node.js (v14 or higher)
- Yarn package manager

### Clone the Repository

```bash
git clone https://github.com/yourusername/mern-task-manager.git
cd mern-task-manager
```

### Install Dependencies

Install server dependencies:

```bash
yarn install-server
```

Install client dependencies:

```bash
yarn install-client
```

## Running the Application

### Start Both Client and Server

To start both the client and server simultaneously, use the following command:

```bash
yarn start
```

This command will run both the client and server using `concurrently`.

### Start Server Only

```bash
yarn start-server
```

### Start Client Only

```bash
yarn start-client
```

## Environment Variables

Create a `.env` file in the root of your project and add the following environment variables:

```bash
MONGODB_URI=mongodb+srv://<username>:<password>@<cluster-name>.mongodb.net/<database-name>?retryWrites=true&w=majority
PORT=5000
```

Replace `<username>`, `<password>`, `<cluster-name>`, and `<database-name>` with your MongoDB Atlas credentials.

## Project Structure

```
mern-task-manager/
├── client/
│   ├── public/
│   └── src/
│       ├── components/
│       ├── hooks/
│       ├── App.js
│       ├── index.js
│       └── ...
├── Server/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── server.js
│   └── ...
├── .env
├── .gitignore
├── package.json
├── README.md
└── ...
```

## API Endpoints

### Get All Tasks

**GET** `/api/tasks`

#### Response

```json
[
  {
    "_id": "60d21b4667d0d8992e610c85",
    "name": "Task 1",
    "endDate": "2024-06-30",
    "status": "Not Started",
    "priority": "High",
    "assignees": ["John Doe", "Jane Doe"],
    "progress": "0%"
  },
  ...
]
```

### Create a New Task

**POST** `/api/tasks`

#### Request Body

```json
{
  "name": "New Task",
  "endDate": "2024-07-01",
  "status": "In Progress",
  "priority": "Medium",
  "assignees": ["John Doe"],
  "progress": "50%"
}
```

### Update a Task

**PUT** `/api/tasks/:id`

#### Request Body

```json
{
  "name": "Updated Task",
  "endDate": "2024-07-10",
  "status": "Completed",
  "priority": "Low",
  "assignees": ["Jane Doe"],
  "progress": "100%"
}
```

### Delete a Task

**DELETE** `/api/tasks/:id`

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. Make sure to follow the code style and add tests for new features or bug fixes.

### Steps to Contribute

1. Fork the repository
2. Create a new branch (`git checkout -b feature-branch`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature-branch`)
5. Open a pull request


### Notes:

1. Replace `https://github.com/yourusername/mern-task-manager.git` with the actual URL of your repository.
2. Adjust the project structure and paths if your actual project structure is different.
3. Add more details to the features, installation steps, or any other section as needed.
4. Ensure that the endpoints described in the API Endpoints section match the actual routes and data structure of your project.

This `README.md` provides a comprehensive overview of the project, how to set it up, run it, and contribute to it. You can expand it with more details or sections based on your project's requirements.
