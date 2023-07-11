# chat-server

# Introduction:
The created chat client-server application contains two python files: one for the server and 
the other for the client. The server python file is run in a command prompt, this results in 
a connection open in the host address of 127.0.0.1 in the port 55555. Multiple client files 
are run in unique command prompts according to the number of clients that are to be 
connected to the server using the TCP socket connection and joining the chat server. The 
basic functionality of the chat server is to create a network of users by connecting them all 
to the site hosted by the server and all the intra communications within the network are 
maintained and passed between the clients by the server using the TCP protocol. A total of 
five commands or actions can be performed by the clients that are connected to the server. 
These basic functionalities that can be performed by the client are help, broadcast, direct 
message, and quit.

# Background work done:
The whole task of creating the chat server application is divided into two subsections, 
which are creating the python scripts for the server and client. The main tasks that have to 
be done in the subsections are as follows:
Server: 
1. Starting the server in an IP address, in this case (127.0.0.1), and hosting this server in 
a port (55555).
2. Maintaining the list of all the users that join the server and maintaining the unique 
identity of the thread on which the client has been instantiated. 
3. Receiving messages from the clients and sending back the messages to the clients 
accordingly.
4. Make sure that the server is always in the listening mode and receiving the request 
messages from the clients that are connected to the server.
5. Writing handler functions to the commands that have been received from the clients by 
decoding the message received.
Client:
1. Connecting to the port hosted by the server.
2. Creating two threads instances, one for the writing part of the client and the other for 
the reading part of the client. 
3. Always be in the listening mode to read the input from the clients and send these 
messages to the server for performing actions accordingly.
All these tasks are divided among the group members and each module is combined to
create the chat server application. The outputs and the expected behaviors of the 
application are tested accordingly, to make sure that all the functionalities of the application 
are maintained properly.
# Implementation details:
The host and port address are determined, and a server is started on this port that starts 
listening for the clients. Every client is assigned an alias name and separate threads for 
listening and writing are initialized with a unique identification whenever a new client is 
started. In this way, each client’s individuality is maintained and this helps us in achieving 
the task of sending personal messages between two clients through the server. For each
command, the handler functions are maintained in the server Python script that takes the 
command sent by the client as input. By decoding this input, the server gets to know what 
type of message or action the respective client wants to perform, and the respective calls 
for the handler functions are made accordingly. In this way, using multithreading, a 
separate thread is maintained for each client, and using this identity of the thread the intra-communication among the clients in the network of the chat server application is 
maintained successfully.
# The command sends the list of users only to the client that has requested for the users.
/dm: dm stands for direct message. This command can be used to send a direct message to 
one of the clients that are connected to the chat server application.
The structure of the command is as follows:
/dm [client that receives the message] [the message that must be sent]
The sample command that can be used in the command prompt where the client is 
initiated:
/dm user2 “hello from the user1 to user2”

/bm: bm stands for the broadcast message. This command can be used to send a message 
to all the clients that are connected to the chat server application.
The structure of the command is as follows:
/bm [the message that must be sent]
The sample command that can be used in the command prompt where the client is 
initiated:
/bm “hello from the user1 to user2”


/help: This command can be used by any client that is connected to the chat server 
application to get a description of all the commands that can be used.
The sample command that can be used in the command prompt where the client is 
initiated:
/help

/quit: This command can be used by the client to quit the chat application server. 
After the 
execution of this command sends a broadcast message to all the users in the connection.
The sample command that can be used in the command prompt where the client is 
initiated:
/quit
