# Real-Time Chat Application

A full-featured chat application with WebSocket support, room management, and user authentication.

![Chat App Screenshot](screenshots/chat-preview.png)

## Features

- **Real-Time Messaging**: Instant message delivery with Socket.io
- **Chat Rooms**: Create, join, and manage multiple chat rooms
- **Message History**: Persisted chat history with MongoDB
- **User Authentication**: JWT-based secure authentication
- **Responsive Design**: Works on desktop and mobile devices
- **Typing Indicators**: See when others are typing
- **Online Status**: Real-time user presence information

## Technologies

### Frontend
- React.js with Hooks
- Socket.io client
- Context API for state management
- CSS Modules for styling

### Backend
- Node.js with Express
- Socket.io server
- MongoDB with Mongoose
- JWT authentication
- RESTful API

## Architecture

```mermaid
sequenceDiagram
    participant Client
    participant Server
    participant Database
    
    Client->>Server: HTTP: Authenticate
    Server->>Database: Verify credentials
    Database-->>Server: User data
    Server-->>Client: JWT token
    
    Client->>Server: WebSocket: Connect
    Client->>Server: WebSocket: Join room
    Server->>Database: Load message history
    Database-->>Server: Last 50 messages
    Server-->>Client: Message history
    
    Client->>Server: WebSocket: Send message
    Server->>Database: Save message
    Server->>Client: Broadcast message to room# Real-time-chat-application
