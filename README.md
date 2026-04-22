# Project BlueBook II

### **Declassified. Documented. Discovered.**

Project BlueBook II is a full-stack Node.js application designed to collect, store, and stream UFO sightings in real time. Built from scratch without frameworks, it demonstrates core backend engineering principles, event-driven architecture, and live data streaming using Server-Sent Events (SSE).

![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![SSE](https://img.shields.io/badge/Real--Time-SSE-blue?style=for-the-badge)
![Event Driven](https://img.shields.io/badge/Architecture-Event--Driven-purple?style=for-the-badge)
![Sanitized](https://img.shields.io/badge/Security-sanitize--html-green?style=for-the-badge)
![No Framework](https://img.shields.io/badge/Backend-No%20Framework-red?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-black?style=for-the-badge)


## ⚙️ Features

### Sightings System
- Submit paranormal/UFO sightings through a structured form
- Data persisted in a JSON-based storage system
- Dynamic rendering of sightings as interactive cards

### Real-Time News Feed
- Live streaming of UFO-related news using **Server-Sent Events (SSE)**
- Updates pushed automatically every few seconds
- No polling, no refresh required

### Event-Driven Architecture
- Custom event emitter triggers alerts on new sightings
- Decoupled logic for scalability and clarity

### Input Sanitization
- User input sanitized using `sanitize-html`
- Protection against XSS and malicious payloads

### Custom HTTP Server
- Built using Node.js core modules (`http`, `fs`, `path`)
- No frameworks like Express used
- Manual routing and static file serving

---

## 🛠️ Tech Stack

- **Backend:** Node.js (Vanilla)
- **Frontend:** HTML, CSS, JavaScript
- **Architecture:** Event-driven (EventEmitter)
- **Real-time:** Server-Sent Events (SSE)
- **Security:** sanitize-html
- **Storage:** File-based JSON

---

## Project Structure
```text
project-bluebook-II/
│
├── assets/         # Screenshots of the website
├── public/         # Frontend files (HTML, CSS, JS, images)
├── data/           # JSON database
├── handlers/       # Route handlers
├── utils/          # Utility functions
├── events/         # Event emitter logic
├── server.js       # Entry point
├── package.json
├── package-lock.json
└── README.md
```


---

## How It Works

### 🔹 API Endpoints

| Method | Endpoint       | Description                     |
|--------|--------------|---------------------------------|
| GET    | `/api`        | Fetch all sightings            |
| POST   | `/api`        | Add a new sighting             |
| GET    | `/api/news`   | Live news stream (SSE)         |

---

### 🔹 Real-Time Streaming (SSE)

The `/api/news` endpoint keeps a persistent connection open and pushes updates:

```js
res.write(`data: ${JSON.stringify({...})}\n\n`)
```

Frontend listens using:

```js
const eventSource = new EventSource("/api/news")
```
## 📦 Installation and Setup:

### 1. Clone the repository
```bash
git clone https://github.com/your-username/project-bluebook-II.git
cd project-bluebook-II
```

### 2. Install dependencies
```bash
npm install
```

### 3. Run the server
```bash
node server.js
```

### 4. Open in browser
```bash
http://localhost:3000
```

## Key Highlights
* Built without Express or external frameworks
* Implements real-time updates using SSE
* Clean separation of concerns (routes, utils, events)
* Secure input handling
* Modular and scalable structure

## Future Enhancements
* Database integration (MongoDB / PostgreSQL)
* Authentication system
* Filtering and search for sightings
* Pagination and performance optimization
* WebSocket-based real-time expansion

## Screenshots/Demo
![Homepage Overview](assets/localhost_8000_ (2).png)
*Homepage*

![Sightings Overview](assets/localhost_3000_sightings.html.png)
*Sightings Page*

![Upload Sightings Page Overview](assets/localhost_3000_upload-sighting.html.png)
*Upload Sightings Page*

![Uplaod Sightings Overview](assets/localhost_8000_upload-sighting.html.png)
*Light Theme Form for Upload Sightings Page (beause I can't decide what to pick aaaaa)*

![News Page Overview](assets/news.html (1).png)
*Live News Page Preview 1*

![News Page Overview](assets/news.html (2).png)
*Live News Page Preview 2*

![News Page Overview](assets/news.html (3).png)
*Live News Page Preview 3*


## Final Note
This project reflects a deep focus on fundamentals — building systems from the ground up, understanding how things work under the hood, and designing with clarity and intent.

