01 . TCP SERVER 

TCP (transimission control protocol) - a protocol or rules for how data is sent reliably between 2 devices , slow but not missing any message.

TCP server - a program that listens on a TCP port and accepts TCP connection from clients.
ex- a webserver listening on TCP port 80 , ssh server listening on TCP port 22.

TCP socket  - one endpoint of a TCP connection. IP address + port + TCP = TCP socket.

Server has 2 sockets:
1. listening socket = sock = socket.socket(...)
sock.bind(...)
sock.listen(...)
only waits doesnot send data.

2. connection socket =connection, addr = sock.accept()
actual communication , send and receive happens here.

Client has only 1 socket: sock.connect(...) sending and receiving.

IN TASK :

python server.py - starting a server , when we run this , it opens a port , waiting for someone to connect.

python client.py - starting a client , connects to server , sends a message.

sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM) - creating socket means asking the kernel of the device where you are running if in laptop (windows or linux kernel ) if in cloud VM ( VM kernel ) . so kernel implements this , creates a object first whith just ip and port , no values are here yet.

socket.AF_INET - use ipv4 , socket.SOCK_STREAM - reliable stream which is TCP.

Internally a socket structure is created - so far no ip , no port , no connection only an object. Like an empty TCP endpoint.

sock.bind(('localhost', 10000)) - listen on this machine , on port 10000.

sock.listen(1) - listen and 1 connection at a time.

connection, client_address = sock.accept() - client connecting , server  accepting.

data = connection.recv(16) -  receive upto 16 bytes .. so the message might be divided.

FLOW:
1. creating a socket 
2. bind it to localhost 
3. find server , perform handshake
4. send data , receive response
5. close it 

PROCEDURE:
1. go to command prompt : python --version
2. choose where to do and clone it that place like that in powershell but path in quotes -  cd "C:\Users\bsaiv\OneDrive\Desktop\cysecProj"
3. clone the repo: git clone https://github.com/kurogai/100-redteam-projects
4. then: cd 100-redteam-projects
5. check files: dir
6. : cd 100-redteam-projects
7. : cd 0_TCP_server
8. open terminal 1 : go to your projects folder on powershell cd "C:\Users\bsaiv\OneDrive\Desktop\cysecProj\100-redteam-projects\Projects\0_TCP_server"
9. confirm for files : ls
10. run python server.py
11. output : server up and listening
12. open another one Terminal 2 : repeat same
13. run python client.py
14. output : Type your message for the server here: testing purposes
Sending message to 127.0.0.1 port 65432
Message received from the server:  b'testing purposes'
15. seeing output cause it is echo server.
16. wont be seeing anything on server but it still listening until you terminate

17. to see output on server side run python script in vscode and check

