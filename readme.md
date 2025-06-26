# QuizCraft

> **Private repository** – Access governed by a signed NDA.


A web-based quiz application that allows users to create, host, and participate in live, gamified quizzes.

## Table of Contents
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Environment Variables](#environment-variables)
- [Running the Application](#running-the-application)
  - [Backend](#backend)
  - [Frontend](#frontend)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Features
- User signup and login with JWT authentication
- Create, read, update, and delete quizzes
- Host live quizzes and share a PIN with players
- Player participation with real-time answer submission and scoring
- Leaderboard and feedback on quiz results

## Tech Stack
- **Frontend**: Next.js, React, Axios
- **Backend**: Node.js, Express, JWT
- **Database**: MongoDB (Mongoose)
- **Authentication**: JSON Web Tokens (JWT)

## Prerequisites
- Node.js >= 14.x
- npm or Yarn
- MongoDB instance (local or Atlas)

## Installation
1. **Clone the private repository** (SSH access required)
   ```bash
   # Make sure you have SSH keys configured and permission to access the repo
   git clone git@github.com:<your-username>/QuizCraft.git
   cd QuizCraft
   ```

2. **Install dependencies**
   ```bash
   # Backend
   cd backend
   npm install

   # Frontend
   cd ../frontend
   npm install
   ```

## Environment Variables
Create a `.env` file in the `backend` directory with:

```dotenv
MONGODB_URI=<your_mongodb_connection_string>
JWT_SECRET=<your_jwt_secret>
PORT=4000
```

If the frontend requires any variables, add a `.env` file in `frontend` accordingly.

## Running the Application

### Backend

```bash
cd backend
npm run dev
```

Server will run on `http://localhost:4000`.

### Frontend

```bash
cd frontend
npm run dev
```

App will run on `http://localhost:3000`.

## Usage
1. **Sign up** for a new account.
2. **Log in** to access your quizzes.
3. **Create** a new quiz by specifying a name and adding questions.
4. **Host** a quiz and share the generated PIN with players.
5. **Players** join via PIN and submit answers in real time.
6. **View** results and leaderboard to see performance.

## API Endpoints

### Authentication
- `POST /api/register` – Register a new user.
- `POST /api/login` – Authenticate and receive a JWT.

### Quizzes
- `GET /api/quiz/all?username=<username>` – Get all quizzes for a user.
- `POST /api/quiz` – Create a new quiz.
- `PUT /api/quiz` – Update an existing quiz.
- `DELETE /api/quiz` – Delete a quiz.

### Live Quiz
- `POST /api/quiz/host` – Host view: fetch question and options.
- `POST /api/quiz/user` – Player view: fetch options for answering.
- `POST /api/quiz/answer` – Submit an answer and receive scoring.
- `GET /api/quiz/results` – Get quiz results and leaderboard.

## Project Structure
```
QuizCraft/
├── backend/
│   ├── controllers/
│   ├── middlewares/
│   ├── models/
│   ├── routes/
│   └── server.js
└── frontend/
    ├── pages/
    ├── components/
    └── public/
```

## Contributing
1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/my-feature`.
3. Commit changes: `git commit -m 'Add my feature'`.
4. Push to the branch: `git push origin feature/my-feature`.
5. Open a Pull Request.

## License
This project is licensed under the [MIT License](LICENSE).

