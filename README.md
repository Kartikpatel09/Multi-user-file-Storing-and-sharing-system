# Multi-User File Storing and Sharing System

A robust client-server application written in C that allows multiple users to store, retrieve, share, and manage files securely. The system supports concurrent user access, file permission management, client-side caching, and user authentication.

## Features

*   **User Authentication:** Secure Signup and Login functionality.
*   **File Management:**
    *   Create and upload new files.
    *   Open and edit files (Read/Write mode).
    *   View files (Read-only mode).
    *   Delete and Rename files.
*   **Permission System:**
    *   Grant or revoke **Read** or **Write** permissions to specific users.
    *   Owners maintain control over their files.
*   **Concurrency:** Multi-threaded server capable of handling multiple clients simultaneously using `pthread`.
*   **Performance:** Implements client-side caching to reduce server load and latency for frequently accessed files.
*   **File Locking:** Ensures data integrity by locking files during write operations.

## Prerequisites

*   **Operating System:** Linux (or WSL on Windows).
*   **Compiler:** GCC (GNU Compiler Collection).
*   **Libraries:** Standard C libraries (`pthread` is required for threading).

## Directory Structure

*   **Server/**: Contains server source code, headers, and storage directories (`_data_` for files, `_metadata_` for logs/permissions).
*   **Client1/2/3/**: Directories simulating different client machines.
*   **Test Client/**: Contains scripts for load testing and performance analysis.

## Compilation Instructions

You need to compile the server and the client separately. Open your terminal and navigate to the project root directory.

### 1. Compile the Server

Navigate to the Server directory and compile the source code:

```bash
cd Server
gcc server.c -o server -lpthread
```
### 2. Compile the Client
You can compile the client code in any of the Client directories (e.g., Client1).
```bash
cd ../Client1
gcc client.c login.c -o client
```
## Running Instructions
### Step 1: Start the Server
Run the server by specifying a port number (e.g., 8080).
```bash
./server 8080
```
The server will start waiting for connections.
### Step 2: Start the Client
Open a new terminal window (keep the server running). Navigate to the Client directory where you compiled the binary and run it by specifying the Server IP and Server Port.
```bash
./client 127.0.0.1 8080
```
