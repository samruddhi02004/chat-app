# Chat App

A simple real-time chat application built with React, Vite, Tailwind CSS, Express, and Socket.IO.

## Project Structure

```text
chat-app-master/
|-- client/   # React + Vite frontend
|-- server/   # Express + Socket.IO backend
`-- README.md
```

## Tech Stack

- Frontend: React, Vite, Tailwind CSS, Socket.IO Client
- Backend: Node.js, Express, Socket.IO

## Prerequisites

Before starting, make sure you have these installed:

- Node.js 18 or later
- npm 9 or later

Check your versions:

```bash
node -v
npm -v
```

## Clone The Repository

```bash
git clone https://github.com/samruddhi02004/chat-app.git
cd chat-app-master
```

## Install Dependencies

This project does not use a root `package.json`, so install dependencies separately for the frontend and backend.

### 1. Install backend dependencies

```bash
cd server
npm install
cd ..
```

### 2. Install frontend dependencies

```bash
cd client
npm install
cd ..
```

## Run The Project

You need two terminals: one for the backend and one for the frontend.

### Terminal 1: Start the backend server

```bash
cd server
npm start
```

The backend starts on `http://localhost:5000`.

### Terminal 2: Start the frontend

```bash
cd client
npm run dev
```

Vite usually starts the frontend on `http://localhost:5173`.

## How It Works

- The frontend connects to the backend with Socket.IO.
- Messages are emitted from the client to the server.
- The server broadcasts each message to all connected clients in real time.

## Important Notes

- The frontend currently connects to a hardcoded Socket.IO server URL: `http://localhost:5000`.
- There is no `.env` setup in the current version of the project.
- The backend `dev` script uses `nodemon`, but `nodemon` is not listed in `server/package.json`.

If you want to use the backend development script, install `nodemon` first inside the `server` folder:

```bash
cd server
npm install --save-dev nodemon
npm run dev
```

## Available Scripts

### Backend (`server`)

- `npm start` - starts the backend with Node.js
- `npm run dev` - starts the backend with Nodemon after it is installed

### Frontend (`client`)

- `npm run dev` - starts the Vite development server
- `npm run build` - creates a production build
- `npm run preview` - previews the production build locally
- `npm run lint` - runs ESLint

## Production Build

To create a production build for the frontend:

```bash
cd client
npm run build
```

The output is generated in `client/dist`.

## Troubleshooting

### Port `5000` is already in use

Stop the process using port `5000`, or update the port in `server/server.js`.

### Frontend cannot connect to the backend

Make sure:

- the backend is running on port `5000`
- the frontend is running on port `5173`
- the URL in `client/src/components/Chat.jsx` matches the backend address

## Current Status

- Frontend production build passes successfully
- Backend source passes a Node.js syntax check
