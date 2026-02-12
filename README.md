# MyTalk

A modern real-time chat application built with React and Socket.io. Features multiple chat rooms, typing indicators, and online user tracking.

![React](https://img.shields.io/badge/React-18.3-blue) ![Socket.io](https://img.shields.io/badge/Socket.io-4.7-green) ![Node.js](https://img.shields.io/badge/Node.js-20+-green)

## Features

- **Real-time Messaging** - Instant message delivery using WebSockets
- **Multiple Chat Rooms** - Join different rooms (General, Technology, Random)
- **Create Custom Rooms** - Create your own chat rooms on the fly
- **Typing Indicators** - See when other users are typing
- **Online Users** - View who's currently in the room
- **System Messages** - Notifications when users join or leave
- **Message History** - See recent messages when joining a room
- **Responsive Design** - Works on desktop and mobile devices
- **Modern UI** - Clean interface built with Tailwind CSS

## Tech Stack

### Frontend
- React 18 with Hooks
- Socket.io Client for real-time communication
- Tailwind CSS for styling
- Lucide React for icons
- Vite for fast development

### Backend
- Node.js with Express
- Socket.io for WebSocket handling
- In-memory message storage

## Getting Started

### Prerequisites

- Node.js 18+ installed

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/sleeman01/mytalk.git
   cd mytalk
   ```

2. **Install backend dependencies**
   ```bash
   cd backend
   npm install
   ```

3. **Install frontend dependencies**
   ```bash
   cd ../frontend
   npm install
   ```

### Running the App

1. **Start the backend server** (Terminal 1)
   ```bash
   cd backend
   npm start
   ```
   Server runs on http://localhost:3002

2. **Start the frontend** (Terminal 2)
   ```bash
   cd frontend
   npm run dev
   ```
   App runs on http://localhost:5173

3. **Open in browser**
   - Go to http://localhost:5173
   - Enter your name and select a room
   - Start chatting!

### Testing Real-time Features

To test the real-time features, open the app in multiple browser tabs or windows:
1. Open http://localhost:5173 in Tab 1
2. Open http://localhost:5173 in Tab 2
3. Join the same room with different usernames
4. Send messages and see them appear instantly in both tabs!

## Project Structure

```
mytalk/
├── backend/
│   ├── index.js          # Express + Socket.io server
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── App.jsx       # Main React component
│   │   ├── main.jsx      # Entry point
│   │   └── index.css     # Tailwind & custom styles
│   ├── public/
│   ├── index.html
│   ├── vite.config.js
│   ├── tailwind.config.js
│   └── package.json
└── README.md
```

## Socket.io Events

### Client → Server

| Event | Payload | Description |
|-------|---------|-------------|
| `room:join` | `{ username, room }` | Join a chat room |
| `message:send` | `{ content }` | Send a message |
| `typing:start` | - | User started typing |
| `typing:stop` | - | User stopped typing |
| `room:create` | `roomName` | Create a new room |

### Server → Client

| Event | Payload | Description |
|-------|---------|-------------|
| `rooms:list` | `[{ name, userCount }]` | List of all rooms |
| `room:history` | `[messages]` | Message history for a room |
| `room:users` | `[usernames]` | Users in current room |
| `message:receive` | `message` | New message received |
| `typing:update` | `{ username, isTyping }` | Typing status update |

## Screenshots

### Login Screen
Modern login interface to enter username and select a room.

### Chat Room
Full-featured MyTalk interface with sidebar navigation and online users panel.

## Deployment

### Backend (Render/Railway)
1. Create a new Web Service
2. Connect your GitHub repo
3. Set root directory to `backend`
4. Build command: `npm install`
5. Start command: `npm start`

### Frontend (Vercel/Netlify)
1. Import your repo
2. Set root directory to `frontend`
3. Update the `SOCKET_URL` in App.jsx to your backend URL

## Future Improvements

- [ ] User authentication
- [ ] Private messaging
- [ ] File sharing
- [ ] Message reactions
- [ ] Persistent storage (MongoDB)
- [ ] User avatars

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT License - feel free to use this project for learning or as a portfolio piece.

## Author

**Sleeman** - [GitHub](https://github.com/sleeman01)

---

*Built as a portfolio project to demonstrate real-time web development skills with React, Node.js, and Socket.io.*
