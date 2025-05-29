# Campus Compass AI Chatbot

> A college inquiry chatbot for Shri Ramdeobaba College of Engineering and Management (RCOEM), now Ramdeobaba University Nagpur (RBU).

Campus Compass is an AI-powered chatbot that answers student queries about admissions, courses, campus facilities, and more. It uses a Flask backend with pre-defined intents, a transformer-based semantic search as fallback, and OpenAI’s GPT-4o for dynamic responses. The frontend is built with React and Vite.

---

## Table of Contents

1. [Features](#features)
2. [Tech Stack](#tech-stack)
3. [Prerequisites](#prerequisites)
4. [Installation](#installation)

   * [Backend Setup](#backend-setup)
   * [Frontend Setup](#frontend-setup)
5. [Configuration](#configuration)
6. [Running the App](#running-the-app)
7. [API Reference](#api-reference)
8. [File Structure](#file-structure)
9. [Contributing](#contributing)
10. [License](#license)

---

## Features

* 📚  **Predefined Intents**: Answers common college queries via JSON intents.
* 🔍  **Semantic Search Fallback**: Uses Sentence-Transformers for best-match patterns.
* 🤖  **OpenAI Integration**: Leverages GPT-4o for unanswered or low-confidence queries.
* 🗄️  **MongoDB**: Stores user accounts and feedback.
* 🔐  **Authentication**: Signup, login, logout flows.
* 💬  **User Feedback**: Prompt for satisfaction and collect feedback via email.
* 🌐  **CORS Enabled**: Frontend and backend communicate seamlessly.

## Tech Stack

* **Backend**: Python, Flask, PyMongo, Transformers, OpenAI API
* **Frontend**: React, Vite, Tailwind CSS
* **Database**: MongoDB Atlas
* **Models**: `sentence-transformers/all-MiniLM-L6-v2`, GPT-4o

## Prerequisites

* Node.js >= 16
* Python >= 3.10
* MongoDB Atlas account
* OpenAI API key

## Installation

### Backend Setup

1. Navigate to the `server/` directory:

   ```bash
   cd server
   ```
2. Create and activate a virtual environment:

   ```bash
   python -m venv venv
   source venv/bin/activate   # on macOS/Linux
   venv\Scripts\activate    # on Windows
   ```
3. Install Python dependencies:

   ```bash
   pip install -r requirements.txt
   ```

### Frontend Setup

1. Navigate to the `client/` directory:

   ```bash
   cd client
   ```
2. Install Node.js packages:

   ```bash
   npm install
   ```

## Configuration

1. Copy `.env.example` to `.env` in the `server/` folder.
2. Set the following environment variables:

   ```env
   OPENAI_API_KEY=your_openai_api_key
   MONGODB_URI=your_mongo_connection_string
   SECRET_KEY=your_flask_secret_key
   ```

## Running the App

### Start backend

```bash
cd server
source venv/bin/activate
python app.py
```

### Start frontend

```bash
cd client
npm run dev
```

Open your browser at `http://localhost:5173` to interact with Campus Compass.

## API Reference

### `POST /ask`

* **Body**: `{ inputValue: string }`
* **Response**: `{ response: string, satisfaction: string }`

### `POST /feedback`

* **Body**: `{ satisfied: boolean, email?: string }`
* **Response**: `message` confirming feedback capture.

### `POST /login`

* **Body**: `{ username: string, password: string }`
* **Response**: Login status message.

### `POST /signup`

* **Body**: `{ first-name, last-name, email, password }`
* **Response**: Account creation status.

## File Structure

```
chatBot-main-main/
├─ client/       # React frontend
├─ server/       # Flask backend
│  ├─ app.py
│  ├─ About us.json
│  ├─ users.json
│  └─ .gitignore
└─ README.md     # Project overview
```

## Contributing

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

MIT © \[Your Name]
