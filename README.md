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
