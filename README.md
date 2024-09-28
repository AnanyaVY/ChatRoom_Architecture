# PyconChat: A Multi-Client Chatroom Architecture

## Project Overview

PyconChat is a multi-client chatroom application built using Python's socket programming and threading capabilities. 
The project includes both server and client components, enabling real-time communication between multiple users in a 
structured chatroom environment. The server manages multiple groups, handles client connections, and supports several 
admin-level operations such as approving join requests, transferring admin privileges, and managing file transfers.

This application provides a simple yet effective way to understand client-server communication, threading, and basic 
group management within chat applications.


## Features

1. Multi-client Chatroom: Allows multiple clients to join chat groups simultaneously and interact with each other.
   
2. Group Management: Users can create or join groups. Admins have the authority to approve or reject join requests and can also manage group members.
   
3. Real-time Messaging: Clients can send messages to other group members with real-time updates.
   
4. Admin Control: Group admins can approve join requests, transfer admin privileges, and even kick members from the group.
 
5. File Transfer: Supports file sharing among group members. Files are broadcasted to all online users.
    
6. Offline Message Handling: Keeps track of messages for members who are temporarily offline.

## Technologies Used

1. Python Sockets: Enables TCP/IP communication between the server and multiple clients.
2. Threading: Handles simultaneous client connections and ensures concurrent processing without blocking.
3. Pickle: Serializes and deserializes Python objects to facilitate data transmission between server and client.
4. OS: Manages file operations like saving and deleting files on the server.

## File Descriptions

### client.py:
The client script establishes a connection with the server, allows users to join groups, and send/receive messages. 
It supports various commands for group management and message handling.

### server.py:
The server script manages group creation, handles client requests, and broadcasts messages between clients in 
real-time. It also supports admin-level commands for managing the group.

## How To Run
1. Clone the respository

```bash 
git clone https://github.com/yourusername/pyconchat.git cd pyconchat
``` 

2. Start the Server

```bash 
python server.py
```

3. Start the Client(s)

```bash
python client.py
```

4. Interacting in the Chatroom:

When the client script runs, it will prompt the user for a username and group name.
If the group does not exist, a new group will be created with the user as the admin.
Admins can approve/reject join requests, transfer admin privileges, kick members, and view the list of online or all members.

## Commands Supported

The following commands can be used by clients in the chatroom:

/viewRequests - View pending join requests (Admin only).
/approveRequest - Approve join requests (Admin only).
/disconnect - Disconnect from the chatroom.
/allMembers - View all group members.
/onlineMembers - View currently online group members.
/changeAdmin - Transfer admin privileges to another member (Admin only).
/whoAdmin - Check the current group admin.
/kickMember - Kick a member from the group (Admin only).
/fileTransfer - Upload a file to the group.
