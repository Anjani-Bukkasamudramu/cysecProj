01 . TCP SERVER 

TCP (transimission control protocol) - a protocol or rules for how data is sent reliably between 2 devices , slow but not missing any message.

TCP server - a program that listens on a TCP port and accepts TCP connection from clients.
ex- a webserver listening on TCP port 80 , ssh server listening on TCP port 22.

IN TASK :

python server.py - starting a server , when we run this , it opens a port , waiting for someone to connect.

python client.py - starting a client , connects to server , sends a message.

sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM) - creating socket means asking the kernel of the device where you are running if in laptop (windows or linux kernel ) if in cloud VM ( VM kernel ) . so kernel implements this , creates a object first whith just ip and port , no values are here yet.

socket.AF_INET - use ipv4 , socket.SOCK_STREAM - reliable stream which is TCP.

Internally a socket structure is created - so far no ip , no port , no connection only an object. Like an empty TCP endpoint.



