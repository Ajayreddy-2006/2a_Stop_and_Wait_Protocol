# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

## Client
```
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
```
## Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT

## Client

![Screenshot 2024-05-07 160248](https://github.com/Ajayreddy-2006/2a_Stop_and_Wait_Protocol/assets/145742508/3f780c92-ca6f-4968-8ae8-5d0e9d926ca6)

## Server

![Screenshot 2024-05-07 160237](https://github.com/Ajayreddy-2006/2a_Stop_and_Wait_Protocol/assets/145742508/de144a32-473b-458a-85e5-4b05325a5615)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
