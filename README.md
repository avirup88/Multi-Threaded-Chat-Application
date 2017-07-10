
# Single Server Multi-Client Chat Application including File Transfer

This application consists of a server.java and a client.java files representing the client and server programs of the chat application.  Server program uses TCP connection protocol to listen for clients connecting to its socket using the port specified by the user. If the user doesn't specify any port then the server runs on port 1234.

## Execution Steps for Server.java

1. Open Command Line and navigate to the folder where the file Server.java is present.
2. Type the command javac Server.java for compilation of the the Server.
3. Type the command java Server 1233 to execute the program where 1233 is the port.
4. The server displays a message "Server is running using specified port number=1233". 
   This message proves that the server program is running and is waiting for clients 
   to connect to this server. 
5. If the user doesn’t specify any port, then the Server uses default port of 1234.

## Execution Steps for Client.java

1. Open Command Line and navigate to the folder where the file Client.java is present.
2. Type the command javac Client.java for compilation of the the Server.
3. Type the command java Client localhost 1233 to execute the program where 
   localhost is the server name and 1233 is the port.
4. The client program prompts for the username.
5. Once the client enters the name and hits enter, the server displays a message
   "Client 1 is connected!" confirming that the Client1 is connected to the server.
6. Also, the client is prompted as 
```
		*** Welcome Client1 to our chat room ***
		Enter /quit to leave the chat room
		New Receiving file directory for this client created!!
		Please Enter command:
```
7. Similarly, other clients can be connected to the server using the same Client.java
   program. Please note that if the testing of the program is done in a single machine,
   then there should be separate folders created for server and each clients.
8. If the user doesn’t specify any port, then the Client uses localhost and 
   default port of 1234.
   
  
## Functionalities performed by this application

### 1. Broadcast : 
This feature enables a user to send a message or a file to all other clients connected to the server. For sending file a keyword sendfile is used followed by the filename.
```               
               Example for sending message:
               ——————————————————————————————
               Please Enter command:
	       Hello

	       Example for sending file:
               ——————————————————————————————
               Please Enter command:
	       sendfile test.pdf			   
			   
```			   
### 2. Unicast :   
This feature enables a user to send a message or a file to a particular client connected to the server. 
```
               For sending message the following format should be followed:- 
               ——————————————————————————————————————————————————————————————
               
               		@<TargetUsername>:<your message>
               
               For sending file the following format should be followed:- 
               ——————————————————————————————————————————————————————————————
               
               		@<TargetUsername>:sendfile <your filename with path or without path>
               		
               
               Example for sending message:
               ——————————————————————————————
               Please Enter command:
	       @Client1:Hello

	       Example for sending file:
               ——————————————————————————————
               Please Enter command:
	       @Client1:sendfile test.pdf	
```			   
### 3. BlockCast : 
This feature enables a user to send a message or a file to a all clients except a particular client connected to the server. 
```
               For sending message the following format should be followed:- 
               ——————————————————————————————————————————————————————————————
               
               		!<TargetUsername>:<your message>
               
               For sending file the following format should be followed:- 
               ——————————————————————————————————————————————————————————————
               
               		!<TargetUsername>:sendfile <your filename with path or without path>
               		
               
               Example for sending message:
               ————————————————————————————
               Please Enter command:
	       !Client1:Hello

	       Example for sending file:
               ————————————————————————————
               Please Enter command:
	       !Client1:sendfile test.pdf	
```			   


## Important Notes:- 
The server program should be running before running any client program. The application has been tested for transferring any type of file upto a size of 250MB. Any file over this size may or may not support due to availability of java heap size.
In case of issues, the heap size should be increased or file should be broken into smaller chunks in order to transfer bigger files. 

## References:- 

1. http://java.sun.com/docs/books/tutorial/networking/sockets/
2. http://makemobiapps.blogspot.com/p/multiple-client-server-chat-programming.html

## Acknowledgements : 
Thank you very much to the professor and the TAs for their continued Support.
