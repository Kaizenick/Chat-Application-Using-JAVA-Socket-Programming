# Chat-Application-Using-JAVA-Socket-Programming

## ABSTRACT

* A socket is the one end-point of a two-way communication link between 
two programs running over the network. Running over the network means 
that the programs run on different computers, usually referred as the local 
and the remote computers. However one can run the two programs on the 
same computer. Such communicating programs constitutes a client/server 
application. The server implements a dedicated logic, called service. The 
clients connect to the server to get served, for example, to obtain some data 
or to ask for the computation of some data. Different client/server 
applications implement different kind of services.
A socked is a complex data structure that contains an internet address and a 
port number. 
* A socket, however, is referenced by its descriptor, like a file 
which is referenced by a file descriptor. That is why, the sockets are 
accessed via an application programming interface (API) similar to the file 
input/output API. This makes the programming of network applications 
very simple. The two-way communication link between the two programs 
running on different computers is done by reading from and writing to the 
sockets created on these computers. The data read from a socked is the data 
wrote into the other socket of the link. And reciprocally, the the data wrote 
into a socket in the data read from the other socket of the link. These two 
sockets are created and linked during the connection creation phase. The 
link between two sockets is like a pipe that is implemented using a stack of 
protocols. This linking of the sockets involves that internally a socket has a 
much more complex data structure, or more precisely, a collaboration of 
data structures. Thus, a socket data structure is more than just an internet 
address and a port number. You have to imagine a socket as a data structure 
that contains at least the internet address and the port number on the local 
computer, and the internet address and the port number on the remote 
computer.

## OBJECTIVES AND GOALS
Sockets provide the communication mechanism between two computers 
using TCP. A client program creates a socket on its end of the 
communication and attempts to connect that socket to a server. When the 
connection is made, the server creates a socket object on its end of the 
communication. The client and server can now communicate by writing 
to and reading from the socket. The java.net.Socket class represents a 
socket, and the java.net.ServerSocket class provides a mechanism for the 
server program to listen for clients and establish connections with them.

* In this Project we built a Chat application using Multi thread ClientServer Architecture. The IDE we used for java socket programming is 
ECLIPSE .

## APPLICATIONS
With the help of our prototype we can create the same thing on large 
scale which will connect multiple user simultaneously, Just the same way 
as our messaging app works like WhatsApp, Messanger which can send 
file as well as the messages.

## COMPONENTS/SOFTWARE REQUIRED
Our project is completely software based, the software used is Eclipse for 
compilation code other than that we are using inbuilt API of java i.e, 
Java.net.* which is for creating socket and Java.awt.* this API provide 
classes for text field, Label, TextArea ,Button etc

### Chat Application
Chat application called ‘Anonymous Chat Application’ has been created with graphic user interface (GUI) capable of exchanging text chat between two or multiple computers over the network using java socket programming and JavaFX has been created. This application will let the user connect to the chat server or chat room with unique user name and will let user see who is online at the same chat room or server. This application has separated server and client application and as socket programming require server to be present for client to connect, server application called ‘ChatServer’ need to be run first before running ‘ChatClient’.

## Logic
The logic of the application is explained below in bullet point.

As server is required to relay the message between the clients, this application has a ‘ChatServer’ component which need to be executed first.
After ‘ChatServer’ is running, client application called ‘ChatClient’ can be executed.
As the client application is the only way the user can send and receive the messages, a user name needs to create before message can be send.
This is performed by sending the user name to the server to check whether the server contain any user with same name, if the user name is accepted, then the user is able to start receiving the message from the server which include the active user list and any message send by user there afterwards, if the user name was unaccepted, the user is asked to enter the user name again till it satisfy the criteria.
This is done to prevent two users with same name, which will confuse all the user participating in the chat room.
Once user compose and press send message, the server receives the message and broadcast to all the user to the chat room.
Multiline text input has been provided to user by using the text area.
A lot of error handling has been performed so that when user exit or close the application, the server receives the socket close notification, closing the user socket and removing it from the current user list so that the user name is available for future connection.
As the server side is always listening for the connection request in a loop and once socket is created, a thread is created to communicate with the given client, many clients can create a connection and exchange messages between them.

## Input: -
The server must be running for the user input to be processed, once the server is running the user can user the text field, buttons and text area to provide input to the system.

The user can use text field labelled name to input the user name.
The user can then press join to send the user name to the server to be processed.
If the name is accepted by server, then the user can use text area labelled compose to compose the message to be send to all the people joining the chat room/server.
Once the chat is composed, the user can press send button to send the message to the server for it to be broadcasted to everyone joining in the chat server.
The user can press exit to terminate the connection and close the application.
Same task can be performed by pressing the cross button in the Windows UI.
Processing: -
As this application has two components: server and client, these components will process different data differently.

## Server:
The server will receive the connection request from the server and will assign a unique socket for the client to connect and create a thread to communicate with the client.
When the client side connect for the first time, it can send the server its user name.
Once the user name is received by the server, the server checks the internal user list to check whether there is a user with same user name. If the user exists, it will send username and if does not exist then will add the username to the user list and dispatch message to all the user letting them know that the new user has joined the chat and send client with accepted message and updated user list.
Once the user is accepted, it will also receive the list of users as a string, this string is reprocessed to add to the active user list view.
The user can then send the message to the server.
Once the server receives the message, it broadcast the message to everyone in the chat server.
If the client terminates the application, the server sends a notification to all user letting them know that the user has left the client with updated user list.
Output: -
Server:
The server application will present the user with the information regarding the number of connections made and the user activity.

List view of log labelled log show all the activity that is happening in the server.
List view labelled active user shows the current active user connected to the server.

## Client:
The client will present user with the active user list in the chat server as well as messages that been shared by users as well as notification send by server to let users know of new user joining or leaving the chat.

List view labelled messages shows all the user’s message as well as notification send by server regarding user leaving and joining the chat server.
List view labelled active users shows all the user connected to the server excluding itself.

## DESIGN

### HOW CAN YOU CREATE A NETWORK CONNECTION?
A network connection is initiated by a client program when it creates a 
socket for the communication with the server. To create the socket in 
Java, the client calls the Socket constructor and passes the server 
address and the the specific server port number to it. At this stage the 
server must be started on the machine having the specified address and 
listening for connections on its specific port number.
The server uses a specific port dedicated only to listening for 
connection requests from clients. It cannot use this specific port for data 
communication with the clients because the server must be able to 
accept the client connection at any instant. So, its specific port is 
dedicated only to listening for new connection requests. The server side 
socket associated with specific port is called server socket. When a 
connection request arrives on this socket from the client side, the client 
and the server establish a connection. This connection is established as 
follows:

1. When the server receives a connection request on its specific server 
port, it creates a new socket for it and binds a port number to it.
2. It sends the new port number to the client to inform it that the 
connection is established.
3. The server goes on now by listening on two ports:
it waits for new incoming connection requests on its specific port, and
it reads and writes messages on established connection (on new port) with 
the accepted client.
4. The server communicates with the client by reading from and writing to 
the new port. If other connection requests arrive, the server accepts them 
in the similar way creating a new port for each new connection. Thus, at 
any instant, the server must be able to communicate simultaneously with 
many clients and to wait on the same time for incoming requests on its 
specific server port. The communication with each client is done via the 
sockets created for each communication.
5. The java.net package in the Java development environment provides the 
class Socket that implements the client side and the class serverSocket
class that implements the server side socket.9
The client and the server must agree on a protocol. They must agree on 
the language of the information transferred back and forth through the 
socket. There are two communication protocols :
stream communication protocol and,
datagram communication protocol.
The stream communication protocol is known as TCP (transfer control 
protocol).
6. TCP is a connection-oriented protocol. It works as described 
in this document. In order to communicate over the TCP protocol, a 
connection must first be established between two sockets. While one of
the sockets listens for a connection request (server), the other asks for a 
connection (client). Once the two sockets are connected, they can be 
used to transmit and/or to receive data. When we say "two sockets are 
connected" we mean the fact that the server accepted a connection. As it 
was explained above the server creates a new local socket for the new 
connection. The process of the new local socket creation, however, is 
transparent for the client.
7. The datagram communication protocol, known as UDP (user datagram 
protocol), is a connectionless protocol. No connection is established 
before sending the data. The data are sent in a packet called datagram. 
The datagram is sent like a request for establishing a connection. 
However, the datagram contains not only the addresses, it contains the 
user data also. Once it arrives to the destination the user data are read by 
the remote application and no connection is established. This protocol 
requires that each time a datagram is sent, the local socket and the 
remote socket addresses must also be sent in the datagram. These 
addresses are sent in each datagram.
8. The java.net package in the Java development environment provides 
theclass DatagramSocket for programming datagram communications.
UDP is an unreliable protocol. There is no guarantee that the datagrams 
will be delivered in a good order to the destination socket. For, example, 
a long text, split in several pages and sent one page per datagram, can be 
received in a different page order. On the other side, TCP is a reliable 
protocol. TCP guarantee that the pages will be received in the order in 
which they are sent. When programming TCP and UDP based 10
applications in Java, different types of sockets are used. These sockets 
are implemented in different classes. The classes ServerSocket and 
Socket implement TCP based sockets and the class DatagramSocket
implements UDP based sockets as follows:
Stream socket to listen for client requests (TCP): the class ServerSocket.
Stream socket (TCP): the class Socket.
Datagram socket (UDP): the class 
DatagramSocket. 
This project shows TCP based client/server applications

![image](https://user-images.githubusercontent.com/56361650/124974916-02dae100-e04b-11eb-8838-0fb20ebbedce.png)

![image](https://user-images.githubusercontent.com/56361650/124974963-12f2c080-e04b-11eb-8a24-5634f764b5bf.png)

Link for demonstration of the project:
https://youtu.be/emC8PZTdKRQ

## CONCLUSION AND INFERENCE
* CONCEPT LEARNED:
A socket is one endpoint of a two-way communication link between two 
programs running on the network. Socket is bound to a port number so 
that the TCP layer can identify the application that data is destined to be 
sent.
* CHALLENGES FACED:
While working on the project we need to have a good command java 
language and API We faced lot of problems while creating the GUI other 
than that we faced trouble while selecting the port number for the machine as 
there are some port numbers which are granted for different protocols.
* CONCLUSION:
In java socket programming, we learnt how to write java socket server and 
java socket client program and implemented using data communication 
concepts of transferring the data (messages) among the server and group 
clients. We also learnt how server client program read and write data on 
socket. We also learnt how server client program read and write data on 
socket and use of GUI to provide customer better experience while using the 
application.
