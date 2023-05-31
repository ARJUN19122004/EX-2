# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

DATE:16-03-2023

AIM :
    To write a python program to perform stop and wait protocol
ALGORITHM :

1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it
will send NACKsignal to client.
6. Stop the program

PROGRAM :

CLIENT PROGRAM:

import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 continue
 else:
 c.close()
 break
 
SERVER PROGRAM:

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())

OUTPUT :

CLIENT OUTPUT:
file:///home/sec/Pictures/Screenshots/Screenshot%20from%202023-05-30%2011-35-34.png![image](https://github.com/ARJUN19122004/EX-2/assets/119429483/8ba0ab9a-19cf-4e18-91a7-793738635ce9)


SERVER OUTPUT:
file:///home/sec/Pictures/Screenshots/Screenshot%20from%202023-05-30%2011-35-54.png![image](https://github.com/ARJUN19122004/EX-2/assets/119429483/24541677-affe-4abe-b6bb-f8e7ab1a4047)


RESULT :
Thus, python program to perform stop and wait protocol was successfully executed.

