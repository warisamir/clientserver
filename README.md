<h1>Rescord — Real-Time Chat Application</h1>

<p>
  <img src="https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=white"/>
  <img src="https://img.shields.io/badge/Node.js-Express-339933?style=for-the-badge&logo=nodedotjs&logoColor=white"/>
  <img src="https://img.shields.io/badge/Socket.io-Real--Time-010101?style=for-the-badge&logo=socketdotio&logoColor=white"/>
  <img src="https://img.shields.io/badge/WebRTC-Video%20%26%20Screen-FF6B35?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/MongoDB-Mongoose-47A248?style=for-the-badge&logo=mongodb&logoColor=white"/>
</p>

<p>
  <a href="https://discord-ak-clone.netlify.app/">
    <img src="https://img.shields.io/badge/▶%20Live%20Demo-discord--ak--clone.netlify.app-4A90E2?style=for-the-badge&logo=netlify&logoColor=white"/>
  </a>
</p>

A **full-stack real-time chat application** inspired by Discord — featuring WebSocket-based
messaging, WebRTC video/screen sharing, JWT authentication, and multi-user meeting rooms.
Built with React on the frontend and Node.js + Express on the backend.

---

## ✨ Features

- 💬 **Real-time messaging** — instant chat via Socket.io WebSockets
- 📹 **Video calls + screen sharing** — peer-to-peer via WebRTC
- 👥 **Meeting rooms** — up to 4 participants per room
- 🔐 **JWT authentication** — secure login and protected routes
- 🗄️ **Message persistence** — chat history stored in MongoDB
- 📱 **Responsive UI** — works on desktop and mobile

---

## 🏗️ Architecture

    ┌─────────────────────────────────────────┐
    │           React Frontend (client/)      │
    │                                         │
    │  ┌──────────┐  ┌──────────┐   ┌───────┐ │
    │  │  Chat UI │  │ Video UI │   │ Auth  │ │
    │  └────┬─────┘  └────┬─────┘   └───┬───┘ │
    └───────┼─────────────┼─────────────┼─────┘
            │  Socket.io  │   WebRTC    │ REST
            │             │             │
    ┌───────▼─────────────▼─────────────▼─────┐
    │         Node.js + Express (backend/)    │
    │                                         │
    │  ┌──────────────┐   ┌─────────────────┐ │
    │  │  Socket.io   │   │   REST APIs     │ │
    │  │  (real-time) │   │  (auth, users)  │ │
    │  └──────┬───────┘   └────────┬────────┘ │
    └─────────┼────────────────────┼──────────┘
              │                    │
    ┌─────────▼────────────────────▼──────────┐
    │              MongoDB (Mongoose)         │
    │         Users · Messages · Rooms        │
    └─────────────────────────────────────────┘

---

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React.js, JavaScript, CSS |
| Backend | Node.js, Express.js |
| Real-time | Socket.io (WebSockets) |
| Video / Screen share | WebRTC (peer-to-peer) |
| Database | MongoDB + Mongoose |
| Auth | JWT (JSON Web Tokens) |
| Deployment | Netlify (frontend) |

---

## 🚀 Getting Started

### Prerequisites
- Node.js 16+
- MongoDB (local or Atlas)

### 1. Clone the repo
```bash
git clone https://github.com/warisamir/clientserver.git
cd clientserver
```

### 2. Setup Backend
```bash
cd backend
npm install
```

Create a `.env` file in `backend/`:
```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
```

```bash
npm start
```

### 3. Setup Frontend
```bash
cd client
npm install
npm start
```

App runs at `http://localhost:3000`

---

## 📁 Project Structure

    clientserver/
    ├── backend/
    │   ├── routes/          ← Auth + chat REST routes
    │   ├── models/          ← Mongoose schemas (User, Message, Room)
    │   ├── socket/          ← Socket.io event handlers
    │   └── server.js        ← Express + Socket.io entry point
    │
    └── client/
    ├── src/
    │   ├── components/  ← Chat, Video, Room components
    │   ├── pages/       ← Login, Register, Dashboard
    │   └── App.js
    └── public/

---

## 🔑 Key Technical Concepts

- **WebRTC signalling** — Socket.io used as the signalling server to exchange SDP and ICE candidates between peers before direct P2P connection
- **Room management** — server tracks active rooms and participants, enforces 4-member limit
- **JWT middleware** — all protected routes validate token before processing request
- **Event-driven backend** — Socket.io events handle join/leave room, message broadcast, and call initiation

---

## 👤 Author

**Waris Amir** — Java Backend Engineer, Bangalore
[LinkedIn](https://linkedin.com/in/waris-amir-0387461b3) 
· [Portfolio](https://portfolio-git-main-warisamirs-projects.vercel.app/)
· [GitHub](https://github.com/warisamir)
