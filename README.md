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
The server communicates with the client by reading from and writing to 
the new port. If other connection requests arrive, the server accepts them 
in the similar way creating a new port for each new connection. Thus, at 
any instant, the server must be able to communicate simultaneously with 
many clients and to wait on the same time for incoming requests on its 
specific server port. The communication with each client is done via the 
sockets created for each communication.
The java.net package in the Java development environment provides the 
class Socket that implements the client side and the class serverSocket
class that implements the server side socket.9
The client and the server must agree on a protocol. They must agree on 
the language of the information transferred back and forth through the 
socket. There are two communication protocols :
stream communication protocol and,
datagram communication protocol.
The stream communication protocol is known as TCP (transfer control 
protocol). TCP is a connection-oriented protocol. It works as described 
in this document. In order to communicate over the TCP protocol, a 
connection must first be established between two sockets. While one of
the sockets listens for a connection request (server), the other asks for a 
connection (client). Once the two sockets are connected, they can be 
used to transmit and/or to receive data. When we say "two sockets are 
connected" we mean the fact that the server accepted a connection. As it 
was explained above the server creates a new local socket for the new 
connection. The process of the new local socket creation, however, is 
transparent for the client.
The datagram communication protocol, known as UDP (user datagram 
protocol), is a connectionless protocol. No connection is established 
before sending the data. The data are sent in a packet called datagram. 
The datagram is sent like a request for establishing a connection. 
However, the datagram contains not only the addresses, it contains the 
user data also. Once it arrives to the destination the user data are read by 
the remote application and no connection is established. This protocol 
requires that each time a datagram is sent, the local socket and the 
remote socket addresses must also be sent in the datagram. These 
addresses are sent in each datagram.
The java.net package in the Java development environment provides 
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
