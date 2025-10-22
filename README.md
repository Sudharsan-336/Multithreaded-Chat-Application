*COMPANY:* CODTECH IT SOLUTIONS

*NAME:* SUDHARSAN R

*INTERN ID:* CT06DY2993

*DOMAIN:* JAVA PROGRAMMMING

*DURATION:* 6 WEEKS

*MENTOR:* NEELA SANTHOSH

# Multithreaded Chat Application (Java)

A simple **Client-Server Chat Application** built using **Java Sockets** and **Multithreading**.  
Multiple clients can connect to a central server and communicate with each other in real time.

## Features
- Multi-user chat with real-time message broadcasting  
- Each client handled in a separate thread (multithreaded server)  
- Simple text-based interface using console  
- Graceful client disconnection handling  

##  Project Structure
├── ChatServer.java # Server-side code
└── ChatClient.java # Client-side code

## How It Works
1. **Server**  
   - Listens for incoming client connections using `ServerSocket`.  
   - Creates a new `ClientHandler` thread for each client.  
   - Broadcasts messages to all connected clients.  

2. **Client**  
   - Connects to the server using `Socket`.  
   - Runs two threads:
     - One for reading messages from the server.  
     - One for sending messages typed by the user.


